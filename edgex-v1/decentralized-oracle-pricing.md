# Decentralized Oracle Pricing

**Oracle Price**

edgeX's Oracle Price is sourced from the independent provider [Stork](https://www.stork.network/) and is used to calculate margin requirements and liquidation prices. The estimated liquidation price is influenced by the user’s leverage and margin. If the Oracle Price reaches this liquidation threshold, the position will undergo forced liquidation. Oracle Prices are crucial for maintaining the integrity of the trading platform by providing reliable price data that is resistant to manipulation.



**The Importance of Oracle Prices and How Decentralized Oracles Prevent Price Manipulations**

In the cryptocurrency market, centralized exchanges (CEXs) have historically played a significant role. However, concerns about potential price manipulation and malicious flash crashes on some centralized platforms have garnered widespread attention. These incidents can lead to unwarranted liquidations and substantial financial losses for traders. In this context, decentralized oracles are emerging as a promising solution to enhance market integrity.

The Challenge of Malicious Flash Crashes on Centralized Exchanges

A malicious flash crash refers to sudden, abnormal surges or drops in asset prices on trading charts. These abrupt movements can trigger traders’ stop-loss orders unexpectedly, leading to forced liquidations and financial losses. Causes may include market manipulation, insufficient liquidity, algorithmic trading errors, or technical glitches within the exchange. Given that CEXs have full control over their platforms, it becomes challenging for external parties and traders to verify the true origins of these anomalies.

In contrast, decentralized exchanges like edgeX can integrate decentralized oracles into their platforms.

Decentralized oracles are systems that collect and verify data through distributed networks, aiming to provide trustworthy and manipulation-resistant external information to decentralized applications. Unlike traditional centralized oracles, these decentralized counterparts rely on multiple independent data sources and validation nodes to ensure data accuracy and reliability.



**How Decentralized Oracles Prevent Malicious Price Manipulations**

1: Decentralized Data Sources&#x20;

By aggregating price information from multiple mainstream exchanges and markets, decentralized oracles reduce the risk of relying on a single, potentially compromised data source. Even if one exchange experiences abnormal volatility, the oracle can provide accurate pricing by referencing alternative sources. This diversification enhances the robustness of the price data and mitigates the impact of localized anomalies.

2. Consensus Mechanism Verification

Nodes within the oracle network use consensus algorithms to validate collected data, filtering out anomalous or outlier price points. This process ensures that the final price feed is both accurate and trustworthy. By requiring agreement among multiple nodes, the oracle network minimizes the risk of false data being introduced into the system.

3. Transparency and Auditability

All data collection and verification steps are recorded, offering complete transparency. This auditability enhances the system’s credibility and minimizes the possibility of undetected manipulation. Traders and external parties can verify the integrity of the data, fostering trust in the platform.

edgeX Uses Stork, the Most Battle-Proven Decentralized Oracle Provider for Perp DEX

Stork is an oracle that offers unprecedented speed and pricing expertise to the world of leveraged derivatives trading. Stork serves as the backbone for over 35 perpetual decentralized exchanges (Perp DEX), supporting over 2,000 assets and securing over $300 billion in trading volume.



**Technical Architecture**

Stork is built on robust architecture designed for speed, reliability, and flexibility:

**Decentralized Publisher Network:** The network of data providers supplies proprietary market data, signed in a chain-compatible format.&#x20;

**High-Frequency Oracle:** Redundant, geo-distributed infrastructure powers low-latency WebSockets for access to all price feeds.&#x20;

**Off-Chain Component:** Decentralized applications (dApps) integrate with a WebSocket to determine which updates should be sent on-chain.&#x20;

**On-Chain Contract:** Utilizes Stork’s On-Chain Verifier to ensure only approved publisher prices are considered.&#x20;

**Stork On-Chain Verifier:** Verifies the validity, source, and calculation method of published prices on-chain.&#x20;

For more details about Stork, visit the [Stork documentation](https://docs.stork.network/).



**edgeX’s Commitment to Promoting Fair Competition for All Traders**

edgeX utilizes the decentralized oracle Stork to obtain independent and precise price data, ensuring accurate pricing and mitigating liquidation risks stemming from malicious price swings. By minimizing opportunities for price manipulation, decentralized oracle integration contributes to a fairer trading environment for all traders.
