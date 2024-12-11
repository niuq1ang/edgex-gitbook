# V1 Technical Architecture

edgeX V1 is a high-performance decentralized exchange (DEX) operating as a central limit order book (CLOB) model. Each trade on edgeX V1 is settled on the Ethereum, leveraging the StarkEx Layer 2 engine for on-chain validation of trading logic, preventing fraudulent or incorrect transactions. This robust validation process is reinforced by third-party committees, which batch trades into the Ethereum blockchain, ensuring transparency and integrity. The publication of zero-knowledge proofs on the Ethereum Layer 1 blockchain adds a layer of security, validating Layer 2 transactions and safeguarding their integrity.

edgeX V1 utilizes independent oracle providers to source mark prices, effectively mitigating the risk of price manipulation and ensuring accurate reflection of asset values. This mechanism protects user positions from price manipulation and liquidation issues prevalent in centralized exchanges.

The high-performance trading engine of edgeX V1 delivers a seamless and exceptionally fast trading experience. When scale up to 10 shards, edgeX achieves an impressive throughput of 20,000 transactions per second (tps) and boasts the lowest match latency in the industry. These performance metrics highlight edgeX's commitment to providing a top-tier trading environment for professional perpetual traders.

edgeX V1's technical architecture balances the security and transparency inherent to decentralization with the speed and efficiency required for high-frequency trading.
