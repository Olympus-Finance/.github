# 🏛️ Olympus Finance
### The Autonomous Leveraged Yield Protocol

![Olympus Finance Banner](Banner.png)

Welcome to the official home of **Olympus Finance**, a decentralized leveraged yield protocol built for the **Polkadot Hub TestNet**. Olympus Finance pioneers the next generation of DeFi by integrating institutional-grade risk management with agentic AI intelligence and seamless cross-chain accessibility.

---

## 🌟 The Olympus Edge (Key Features)

Olympus Finance addresses the critical challenges of modern liquidity provisioning—**Loss-Versus-Rebalancing (LVR)** and capital inefficiency—through a multi-layered autonomous architecture:

*   **📈 High-Performance Yield Engine**: 2x leveraged vaults for `WETH`, `WBTC`, and `DOT` that utilize **Credit Delegation** via `OlympusLend` to maximize capital efficiency while maintaining delta-neutral exposure.
*   **⚔️ Active LVR Protection**: Real-time protection via **Uniswap V4 Hooks**. Our "Defender" role monitors market volatility and swap divergence to dynamically adjust fees, protecting Liquidity Providers from toxic arbitrage.
*   **📊 Institutional Risk Suite**: Beyond static data, Olympus provides **Value at Risk (VaR)** scores with 95% confidence and a **Hybrid NAV** system that combines off-chain analytics with on-chain verification.
*   **🧠 Agentic AI Copilot**: A built-in protocol "Brain" powered by **Google Gemini** and the **Polkadot Agent Kit**. It provides context-aware guidance and executes Substrate-native actions directly from the dashboard.
*   **🌉 Hyperbridge Auto-Zap**: A secure cross-chain architecture that enables users on **Base Sepolia** to teleport assets into Olympus vaults on **Polkadot Hub** with a single click, featuring fully subsidized relayer fees.
*   **🛡️ Autonomous Guardians**: A fleet of 7 specialized backend roles that monitor protocol health 24/7, executing rebalances, fee updates, and emergency circuit breakers autonomously.

---

## 🏗️ The Modular Ecosystem

The Olympus Finance protocol is split into four specialized layers, each serving a critical role in our autonomous architecture:

### 🔗 [olympus-sc](https://github.com/OlympusFinance/olympus-sc) (The Execution Layer)
The decentralized heart of the protocol, managing assets, leverage, and cross-chain reception.
*   **OlympusVault.sol**: Hybrid ERC4626 leveraged vaults managing 2x exposure and autonomous rebalancing logic.
*   **OlympusFactory.sol**: Central registry and factory for deploying and tracking authorized leveraged vault markets.
*   **OlympusRouter.sol**: User-facing entry point for native ETH wrapping and local-chain vault interactions.
*   **LVRHook.sol**: A Uniswap V4-compatible hook that mitigates LVR by injecting dynamic swap fees based on real-time volatility.
*   **OlympusDataCache.sol & DataFeedsCache.sol**: High-speed on-chain caches storing backend-published metrics (NAV, VaR, Health).
*   **OlympusBaseBridge.sol**: The entry point on Base Sepolia for teleporting `USD.h` with encoded vault deposit instructions.
*   **OlympusPolkadotReceiver.sol**: A `HyperApp` on Polkadot Hub that decodes bridge messages and performs "Proxy Liquidity" auto-deposits.
*   **OlympusWeth/Wbtc/DotOracle.sol**: AggregatorV3-style oracles providing dedicated spot price feeds for the protocol.
*   **OlympusLend.sol & OlympusSwap.sol**: Mock lending and AMM primitives used for credit delegation and liquidity provisioning demos.

### ⚙️ [olympus-be](https://github.com/OlympusFinance/olympus-be) (The Guardian Layer)
The autonomous control plane that monitors market conditions and manages protocol risk through 7 specialized roles:
*   **🛡️ The Defender**: Mitigates LVR by adjusting dynamic swap fees based on Pyth-to-Spot price divergence.
*   **📈 The Strategist**: Monitors Vault Health Factors and triggers on-chain rebalancing to maintain the 2x leverage target.
*   **⚖️ The Accountant**: Synthesizes vault balances and LP positions to publish hyper-accurate Net Asset Value (NAV).
*   **🧮 The VaR Calculator**: Executes historical simulations to compute 95% confidence Value at Risk metrics.
*   **🔍 The Auditor**: Persistent solvency monitor that triggers emergency circuit breakers if health factors drop.
*   **🌉 The Bridge Manager**: Orchestrates cross-chain logistics and monitors Hyperbridge arrival events.
*   **📢 The Reporter**: Uses **Gemini AI** to translate technical events into human-readable **Guardian Logs**.

### 🤖 [olympus-agent](https://github.com/OlympusFinance/olympus-agent) (The Reasoning Layer)
The intelligent interface between user intent and the Polkadot ecosystem using Polkadot Agent Kit.
*   **🧠 Gemini Planner**: Transforms free-text queries into structured action plans with recommended tools and risk notes.
*   **⚙️ Polkadot Runtime**: Initializes and manages Substrate chain APIs for Hydration, Asset Hub, and Paseo.
*   **🔗 Olympus Context Client**: Bridges real-time protocol state, prices, and guardian logs into the AI's reasoning loop.
*   **🛠️ Tool Catalog**: Exposes standard Polkadot actions (balance, swap) and custom Olympus diagnostics to the AI.

### 🏛️ [olympus-fe](https://github.com/OlympusFinance/olympus-fe) (The Command Center)
A professional Next.js dashboard providing a unified view of the protocol features:
*   **💰 My Balances**: Unified view of wallet balances, active vault shares (afTokens), and quick-access testnet faucets.
*   **📈 Earn**: Core vault management interface featuring high-yield 2x strategies, APY tracking, and Hybrid NAV charts.
*   **🌊 DEX Pools**: Transparency dashboard for OlympusSwap reserves, spot pricing, and LVR divergence tracking.
*   **💳 Credit Line**: Lending health monitor showing protocol-wide USDC debt, utilization, and statistical risk briefs.
*   **🌉 Hyperbridge**: Cross-chain portal for secure Base-to-Polkadot teleportation with "Auto-Zap" vault entry.
*   **🤖 AI Copilot**: Context-aware drawer for AI-driven guidance, tool execution, and natural language protocol updates.

---

## 🛠️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Blockchain** | Solidity 0.8.20+, Foundry, Polkadot Hub TestNet, Base Sepolia |
| **Interoperability** | Hyperbridge (ITokenGateway), Cross-Chain Auto-Zap |
| **Oracles** | Pyth Hermes, AggregatorV3 (Custom), OlympusDataCache |
| **Artificial Intelligence** | Google Gemini 2.0 Flash, Polkadot Agent Kit |
| **Liquidity & Lending** | Uniswap V4 (Hooks), OlympusLend (Credit Delegation) |
| **Frontend** | Next.js 14, Wagmi, Viem, Tailwind CSS, Shadcn UI |

---

## 🚀 Join the Mission

Olympus Finance is more than a yield protocol; it's a showcase of how **Agentic AI** and **Autonomous Infrastructure** can create a safer, more efficient, and truly human-readable financial future on Polkadot.

*Built with 🔥 for the Polkadot Hackathon to make DeFi smarter, safer, and autonomous.*
