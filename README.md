
# Auto V3 - Aerodrome Slipstream Liquidity Manager <img width="801" height="111" alt="image" src="https://github.com/user-attachments/assets/ccb89ad1-33a4-446e-963b-80b03f11ace8" />


## Overview
<img width="1262" height="893" alt="image" src="https://github.com/user-attachments/assets/071b4bd0-f98e-4715-b54f-4ca958af7c5a" />

Auto V3 is a decentralized, client-side application engineered for automated liquidity management, auto-compounding, and dynamic rebalancing of Aerodrome Finance V3 (Slipstream) pools on the Base network. 

The tool runs entirely in the browser, eliminating the need for centralized backend servers or custodial risk, while providing advanced automation capabilities typically reserved for institutional market makers.

## Core Features

### Automated V3 Rebalancing
When the market price of an asset exits your defined lower or upper bounds, the system automatically detects the out-of-range state. It withdraws the inactive liquidity, calculates the exact 50/50 token ratio required for the current market price, routes the necessary swaps via the Odos API, and remints a new, perfectly centered concentrated liquidity position.

### Auto-Compounding
The application continuously monitors pending AERO rewards. Once rewards exceed your configured minimum threshold, the system executes an automated workflow: it claims the AERO, swaps it for the pool's underlying asset pair, and reinvests it directly into your principal liquidity position to maximize APY through continuous compounding.

### Dynamic Recentering (Shift Percentage)
To maintain high capital efficiency, users can set a proactive Shift Percentage trigger. If the market price deviates from your position's exact center by this specific percentage, the system will execute a rebalance. This ensures capital remains deeply concentrated around the active trading price, even if it has not yet breached the hard outer bounds.

### Gas Jar System
Continuous smart contract automation requires network gas. When the Gas Jar is enabled, the system automatically diverts 2% of your harvested compound rewards and swaps them into ETH. This creates a self-sustaining loop, continuously replenishing the wallet's gas reserves to allow the automation to run indefinitely without manual intervention.

### Bot Mode (Unattended Execution)
For true background automation, users can supply a burner wallet private key. This key is held strictly in temporary browser RAM and is permanently destroyed upon closing or refreshing the tab. It allows the application to sign transactions silently in the background, executing rebalances and compounds without requiring manual MetaMask approvals. 

### Integrated Swap Aggregator & Background Monitor
Includes a built-in routing system powered by the Odos API for low-slippage direct token swaps. The interface runs a continuous background polling loop every 30 seconds, fetching live tick data, updating visualizer graphs, and instantly triggering queued automation events based on precise on-chain conditions.

## Architecture & Security
*   **Network**: Base (Chain ID: 8453)
*   **Dependencies**: Ethers.js v6, Odos Swap API, DexScreener API.
*   **Execution**: 100% client-side. No user data, private keys, or wallet addresses are ever transmitted to external servers. 
*   **Security Notice**: When utilizing Bot Mode, users are strongly advised to use a dedicated burner wallet containing only the exact funds required for the active liquidity strategy.

## Getting Started
To prevent browser CORS (Cross-Origin Resource Sharing) restrictions when interacting with Web3 wallets and APIs, it is highly recommended to serve the application through a local web server.

1. Clone the repository to your local machine.
2. Open a terminal and navigate to the project directory.
3. Start a local server using one of the following methods:

   **Using Python (3.x):**
   ```bash
   python -m http.server 8000
   ```
   
   **Using Node.js:**
   ```bash
   npx serve
   ```

4. Open `http://localhost:8000` (or the port provided by your server) in any modern web browser.
5. Connect your Web3 wallet (ensure you are on the Base network).
6. Navigate to the V3 Rebalancer tab, add your desired Aerodrome Slipstream pool address, configure your boundary parameters, and enable the monitor.

## Community & Support
For technical support, bug reports, feature requests, or to discuss liquidity strategies, join the official community Discord:
https://discord.gg/SGgnvyjFn5

## Author & Availability
Developed by vm10k. 

**I am currently open for hiring and new opportunities.** If your team is looking for a web3 developer, protocol automation engineer, or frontend architecture specialist, please reach out. You can contact me directly via the community Discord or through my GitHub profile.

## Support the Project
This software is provided as a 100% free public good. If you find this tool useful and it has helped you optimize your yield, please consider sending a tip to support ongoing development:

**Donation Address (EVM / Base):**
`0x22f9790175ef4f549092c91123e0f7c339cc7d3d`

 **Testing was done on this wallet (EVM / Base):**
`0x6979abc98f09779a29a67db6c2778d608c69b274`

## Disclaimer
Automated smart contract interactions carry inherent risks, including impermanent loss, API routing failures, and network congestion. Use this tool at your own risk. Always test parameters with small amounts before deploying significant capital.  

## Screenshots
<img width="1280" height="892" alt="image" src="https://github.com/user-attachments/assets/1db30192-d095-48a3-8136-23812f6608aa" />
<img width="1257" height="893" alt="image" src="https://github.com/user-attachments/assets/55a40d4a-334b-46f4-be1f-786741da5d11" />

