# Withdrawals

**Ethereum Withdrawals:**

There are two types of withdrawals on edgeX via the Ethereum network: Standard Withdrawals and Premium Withdrawals.

Ethereum Standard Withdrawals:

Standard withdrawals involve two steps: the user first requests a standard withdrawal. Once the next Layer 2 block is mined, the user must send a Layer 1 Ethereum transaction to claim their funds. Users need to wait for Layer 2 blocks to be mined before processing. These blocks are mined roughly every 4 hours, although this can vary up to 8 hours depending on blockchain network conditions.

Ethereum Premium Withdrawals:

Premium withdrawals utilize a liquidity provider to send funds immediately, eliminating the need for users to wait for Layer 2 blocks to be mined. Users do not need to send a Layer 1 transaction for a premium withdrawal. The liquidity provider will immediately send a transaction to Ethereum, which, once mined, will transfer the funds to the user.



**Non-Ethereum Withdrawals:**

Users can withdraw assets directly to different EVM-compatible chains on edgeX. When withdrawing assets to an EVM-compatible chain, the asset is first transferred to edgeX's L2 asset pool. Subsequently, edgeX transfers the corresponding amount of assets to the user's address from its asset pool on the respective withdrawal chain.

Please note that the maximum withdrawal amount is limited not only by the total assets available in a user's account but also by the maximum available amount in the chain's asset pool.



**Withdrawal Fees:**

For ETH standard withdrawals, users just need to cover the gas fees themselves.

For ETH Premium withdrawals, the fee is equal to the gas fee paid by the provider  (with a minimum fee of 3 USDT).

For non-ETH withdrawals, the fee is equal to the gas fee paid by the provider (with a minimum fee of 0.5 USDT).



**Quick Guide**

For Wallet Users:

You can select the chain for withdrawal from Ethereum, BNB Chain, or Arbitrum&#x20;

➡️ Enter the withdrawal amount&#x20;

➡️ Click "Withdraw"&#x20;

➡️ Confirm in the approval pop-up page&#x20;

➡️ Complete the withdrawal.



For MPC Account Users:

Withdrawals can only be made via Arbitrum.&#x20;

➡️ Enter the withdrawal amount.

➡️ Input the Arbitrum address for the withdrawal.

➡️ Click "Withdraw."

➡️ Confirm in the pop-up confirmation window.

➡️ Complete the withdrawal.
