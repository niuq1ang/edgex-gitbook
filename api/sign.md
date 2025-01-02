# Sign

## How To GET Your L2 Private Key

<figure><img src="../../.gitbook/assets/20250102-134437.png" alt=""><figcaption><p><strong>How To GET Your L2 Private Key</strong></p></figcaption></figure>

## Signature Algorithm

**Ecdsa**


> [Python Signature Demo](https://github.com/starkware-libs/starkex-resources/blob/master/crypto/starkware/crypto/signature/signature_test.py#L62)

> [Java Script Signature Demo](https://www.npmjs.com/package/@starkware-industries/starkware-crypto-utils#signing-a-starkex-order)
 
### Java Implement Demo

``` java
import java.math.BigInteger;

import org.web3j.abi.TypeEncoder;
import org.web3j.abi.datatypes.Utf8String;
import org.web3j.abi.datatypes.generated.Uint256;
import org.web3j.crypto.Hash;
import org.web3j.utils.Numeric;

    public static final BigInteger K_MODULUS = Numeric
            .toBigInt("0x0800000000000010ffffffffffffffffb781126dcae7b2321e66a241adc64d2f");

    public static void main(String[] args) {
        String privateKeyHex = "0463ac809cc7d7c1baf*********************baff9fc6e3d8e5b160ea3fc";

        // Ensure that the private key is a hexadecimal string without the "0x" prefix.
        if (privateKeyHex.startsWith("0x")) {
            privateKeyHex = privateKeyHex.substring(2);
        }

        BigInteger mySecretKey = new BigInteger(privateKeyHex, 16);
        PrivateKey privateKey = PrivateKey.create(mySecretKey);

        String message = "1735542383256GET/api/v1/private/account/getPositionTransactionPageaccountId=543429922991899150&filterTypeList=SETTLE_FUNDING_FEE&size=10";
        String msg = TypeEncoder.encodePacked(new Utf8String(message));

        BigInteger msgHash = Numeric.toBigInt(Hash.sha3(Numeric.hexStringToByteArray(msg)));

        msgHash = msgHash.mod(K_MODULUS);

        Signature signature = Ecdsa.sign(msgHash, privateKey);

        String starkSignature = TypeEncoder.encodePacked(new Uint256(signature.r)) +
                TypeEncoder.encodePacked(new Uint256(signature.s)) +
                TypeEncoder.encodePacked(new Uint256(privateKey.publicKey().point.y));

        System.out.println(starkSignature);

    }

    public static Signature sign(BigInteger msgHash, PrivateKey privateKey) {
        Curve curve = privateKey.curve;
        BigInteger randNum = new BigInteger(curve.N.toByteArray().length * 8 - 1, new SecureRandom()).abs().add(BigInteger.ONE);
        Point randomSignPoint = EcMath.multiply(curve.G, randNum, curve.N, curve.A, curve.P);
        BigInteger r = randomSignPoint.x.mod(curve.N);
        BigInteger s = ((msgHash.add(r.multiply(privateKey.secret))).multiply(EcMath.inv(randNum, curve.N))).mod(curve.N);
        return Signature.create(r, s);
    }
```

## Withdraw signature 

```text
position_id <==> user account_id
asset_id_collateral <==> meta_data.coinList.starkExAssetId
```

[WithdrawalToAddress](https://docs.starkware.co/starkex/api/perpetual/transactions.html#services.perpetual.api.gateway.transactions.WithdrawalToAddress)

###  Code Example

``` 
String getWithdrawalToAddressMsg({
  required String assetIdCollateral,
  required String positionId,
  required String ethAddress,
  required String nonce,
  required String expirationTimestamp,
  required String amount,
}) {
  var w1 = assetIdCollateral;
  var w5 = BigInt.from(withdrawalToAddress);
  w5 = (w5 << 64) + _toBigInt(positionId);
  w5 = (w5 << 32) + _toBigInt(nonce);
  w5 = (w5 << 64) + _toBigInt(amount);
  w5 = (w5 << 32) + _toBigInt(expirationTimestamp);
  w5 = w5 << 49;
  return pedersen([
    pedersen([w1, ethAddress]),
    w5.toRadixString(16)
  ]);
}
```


## Limit Order signature

```text
asset_id_synthetic <==> meta_data.contractList.starkExSyntheticAssetId
asset_id_collateral <==> meta_data.coinList.starkExAssetId
asset_id_fee <==> meta_data.coinList.starkExAssetId
```

[Limit order with fees](https://docs.starkware.co/starkex/perpetual/signature_construction_perpetual.html#limit_order_with_fees)

###  Code Example

```code
/// https://docs.starkware.co/starkex-v4/starkex-deep-dive/message-encodings/in-perpetual
String getLimitOrderMsg({
  required String assetIdSynthetic,
  required String assetIdCollateral,
  required bool isBuyingSynthetic,
  required String assetIdFee,
  required String amountSynthetic,
  required String amountCollateral,
  required String maxAmountFee,
  required String nonce,
  required String positionId,
  required String expirationTimestamp,
}) {
  final String assetIdSell;
  final String assetIdBuy;
  final String amountSell;
  final String amountBuy;
  if (isBuyingSynthetic) {
    assetIdSell = assetIdCollateral;
    assetIdBuy = assetIdSynthetic;
    amountSell = amountCollateral;
    amountBuy = amountSynthetic;
  } else {
    assetIdSell = assetIdSynthetic;
    assetIdBuy = assetIdCollateral;
    amountSell = amountSynthetic;
    amountBuy = amountCollateral;
  }
  final w1 = assetIdSell;
  final w2 = assetIdBuy;
  final w3 = assetIdFee;
  var msg = pedersen([w1, w2]);
  msg = pedersen([msg, w3]);
  var w4 = _toBigInt(amountSell);
  w4 = (w4 << 64) + _toBigInt(amountBuy);
  w4 = (w4 << 64) + _toBigInt(maxAmountFee);
  w4 = (w4 << 32) + _toBigInt(nonce);
  msg = pedersen([msg, w4.toRadixString(16)]);
  var w5 = BigInt.from(limitOrderWithFees);
  w5 = (w5 << 64) + _toBigInt(positionId);
  w5 = (w5 << 64) + _toBigInt(positionId);
  w5 = (w5 << 64) + _toBigInt(positionId);
  w5 = (w5 << 32) + _toBigInt(expirationTimestamp);
  w5 = w5 << 17;
  return pedersen([msg, w5.toRadixString(16)]);
}
```

## Transfer signature

[Transfer](https://docs.starkware.co/starkex/perpetual/signature_construction_perpetual.html#transfer_with_fees)

###  Code Example

```code
String getTransferMsg({
  required String assetId,
  required String receiverPublicKey,
  required String senderPositionId,
  required String receiverPositionId,
  required String srcFeePositionId,
  required String nonce,
  required String amount,
  required String expirationTimestamp,
  String assetIdFee = '0',
  String maxAmountFee = '0',
}) {
  final w1 = assetId;
  final w2 = assetIdFee;
  final w3 = receiverPublicKey;
  var w4 = _toBigInt(senderPositionId);
  w4 = (w4 << 64) + _toBigInt(receiverPositionId);
  w4 = (w4 << 64) + _toBigInt(srcFeePositionId);
  w4 = (w4 << 32) + _toBigInt(nonce);
  var w5 = BigInt.from(transfer);
  w5 = (w5 << 64) + _toBigInt(amount);
  w5 = (w5 << 64) + _toBigInt(maxAmountFee);
  w5 = (w5 << 32) + _toBigInt(expirationTimestamp);
  w5 = w5 << 81;
  var msg = pedersen([w1, w2]);
  msg = pedersen([msg, w3]);
  msg = pedersen([msg, w4.toRadixString(16)]);
  msg = pedersen([msg, w5.toRadixString(16)]);
  return msg;
}
```