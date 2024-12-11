# Self-Custody

edgeX, a high-performance decentralized derivatives trading platform, is advancing user asset security and operational transparency by integrating StarkEx’s Layer 2 (L2) scalability solution. Developed by Israeli zero-knowledge proof (ZK) specialist StarkWare, StarkEx employs ZK-Rollup technology to enhance the Ethereum blockchain’s capabilities. This integration ensures that users maintain self-custody over their assets while benefiting from increased transaction speeds and reduced costs.

**Leveraging StarkEx for Scalability and Security**

At the core of edgeX V1’s trading and settlement system is StarkEx’s ZK-Rollup technology, which aggregates multiple transactions off-chain and then verifies them on-chain using zero-knowledge proofs. This approach significantly reduces the computational load on the Ethereum mainnet, enabling higher throughput without compromising security.

Since its deployment in 2020, StarkEx has processed over **$1.3 trillion** in trading volume for more than **200,000 users** worldwide, making it one of the most battle-tested L2 solutions available. By adopting this technology, edgeX ensures that all transactions are securely validated and that the final state of transactions is both transparent and immutable.

<figure><img src="../.gitbook/assets/StarkEx_flow.png" alt=""><figcaption><p><strong>System Operational Flow</strong></p></figcaption></figure>

**Overview**

1. Transaction Execution: Users initiate trades on edgeX, which are executed by the platform and sent to the StarkEx service for processing.
2. Batch Processing and Proof Generation: The StarkEx service batches these transactions and forwards them to the Shared Prover (SHARP) system. SHARP generates zero-knowledge proofs (STARK proofs) to validate the integrity of the batched transactions.
3. On-Chain Verification: The generated proofs are submitted to the on-chain STARK verifier. This verifier ensures that the proofs are valid before any state changes are accepted on the Ethereum blockchain.
4. State Update Submission: Upon successful verification, the StarkEx service submits the updated state to the StarkEx smart contract on the Ethereum mainnet. The contract accepts this new state only if the associated proof has been validated, ensuring the legitimacy of all recorded transactions.

This meticulous process upholds the platform’s security and accuracy, providing users with confidence in the system’s reliability.

Curious to learn more about StarkEx? Visit their comprehensive [documentation](https://docs.starkware.co/starkex/index.html) for detailed insights.



**User Asset Self-Custody: Control at the Forefront**

Unlike centralized exchanges that hold custody of user funds, edgeX utilizes Ethereum smart contracts to store and manage assets transparently via the StarkEx solution. Users deposit their funds directly into these smart contracts on the Ethereum mainnet before engaging in any trading activities on the edgeX platform. Each transaction requires the user’s approval through their Ethereum private key, ensuring that only the account owner can authorize movements of their assets.

This non-custodial approach means that even while assets are managed within the L2 system, users retain full control. Even in black swan scenarios where the L2 operator (edgeX) might experience downtime or fail to process transactions promptly, users can independently close their positions and withdraw their funds using their private keys. This mechanism provides an additional layer of security and autonomy, safeguarding user assets against potential operational risks.

edgeX’s reliance on user signatures for all L2 account operations makes unauthorized transactions virtually impossible. The synchronization of L2 states with Ethereum’s Layer 1 custody contracts further ensures that all asset movements are transparent and verifiable on the blockchain. By design, no entity can construct fraudulent transactions to misappropriate user assets.



**Anti-Censorship Measures and Forced Withdrawals**

edgeX’s architecture includes robust features to protect user assets through anti-censorship mechanisms, ensuring that users can access their funds without interference at any time:

* **Forced Withdrawals**: If, for any reason, edgeX does not process a user’s withdrawal request within a predetermined timeframe, users can initiate a forced withdrawal. This process allows them to interact directly with the smart contract to retrieve their assets, bypassing the operator.

These features ensure that users have uninterrupted access to their assets, even in the face of unforeseen events or platform disruptions.

<figure><img src="../.gitbook/assets/forced-operation.png" alt=""><figcaption></figcaption></figure>



For a step-by-step guide on the forced withdrawal process, please check out the [StarkEx Forced Operations page](https://docs.starkware.co/starkex/perpetual/performing-forced-transactions.html).



**Commitment to Transparency and User Empowerment**

edgeX’s integration of StarkEx technology represents a significant advancement in exchange technology. By prioritizing self-custodial assets and incorporating mechanisms for anti-censorship, edgeX empowers users with unparalleled control over their assets.





