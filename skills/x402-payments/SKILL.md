---
name: x402-payments
description: Complete catalog and execution guide for WarpPay402 monetized Web3 AI developer tools with automatic HTTP 402 USDC micropayment challenges.
---

# WarpPay402 x402 Payment & Tool Execution Playbook

When invoking `warppay402` MCP tools via `https://api.warppay402.com/mcp`, requests return an HTTP 402 challenge when unauthenticated.
Supported networks for x402 USDC micropayments:
- **Base Mainnet (`eip155:8453`)**: Native USDC (`0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913`)
- **Arc Mainnet (`eip155:5042`)**: Native USDC (`0x0000000000000000000000000000000000000000`)
- **Arbitrum One (`eip155:42161`)**: USDC (`0xaf88d065e77c8cC2239327C5EDb3A432268e5831`)
- **Solana Mainnet (`solana:5eykt4UsFv8P8NJdTREpY1vzqKqZKvdp`)**: SPL USDC (`EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v`)

---

## Complete 21 Tool Catalog

### 1. Web & Document Extraction Intelligence
- `web_scraper` ($0.001 USDC): Scrapes public webpages into clean Markdown.
- `browser_scraper` ($0.005 USDC): Headless Chromium browser rendering via proxy workers for dynamic JS pages.
- `pdf_extractor` ($0.005 USDC): Extracts plain text previews from public PDF document URLs.
- `render_screenshot` ($0.010 USDC): Captures full-page rendered screenshot images.
- `extract_json` ($0.010 USDC): Extracts structured JSON data from web HTML using custom schemas.

### 2. Attestation & Data Feeds
- `public_data_feed` ($0.0001 USDC): Fetches signed public attestation JSON records.
- `data_feeds` ($0.0010 USDC): Retrieves pre-scraped AI data feeds, market trends, and yield reports.
- `x402_telemetry_feed` (Free / $0.0000): Fetches public x402 transaction volume, uptime, and on-chain settlement proofs.

### 3. Base Mainnet Analytics & Aerodrome DeFi
- `base_analytics` ($0.0020 USDC): Fetches ETH balance and account nonce for any 0x address on Base.
- `smart_contract_verifier` ($0.0200 USDC): Source code analysis, ABI fetching, and proxy validation on Basescan.
- `get_aerodrome_yields` ($0.0030 USDC): Fetches top live Aerodrome DEX yield pools, APYs, and TVL on Base.
- `aerodrome_swap` ($0.0100 USDC): Programmatic low-slippage token swaps via Aerodrome Base Router.
- `aerodrome_clamm` ($0.0100 USDC): Concentrated liquidity management (mint, adjust, collect) on Aerodrome Slipstream.
- `aerodrome_veaero` ($0.0100 USDC): Automates$AERO locking, epoch gauge voting, and bribe reward harvesting.

### 4. Arc Mainnet Telemetry & Cross-Chain Infrastructure
- `arc_analytics` ($0.0010 USDC): Live block height, gas prices, and RPC latency from Arc Mainnet.
- `arc_network_oracle_query` ($0.1000 USDC): Pre-flight telemetry: RPC latency (ms), gas fees (Gwei), merchant USDC balance, and nonce.
- `arc_dex_oracle` ($0.0010 USDC): Real-time ETH/USDC spot price resolver and DEX liquidity oracle for Arc.
- `arc_cctp_bridge` ($0.2500 USDC): Bridges USDC cross-chain from Arc Mainnet to Solana, Base, Arbitrum, or Ethereum via Circle CCTP V2.

### 5. Smart Contract Deployment Factories ($5.00 USDC)
- `deploy_contract`: Deploys custom Escrow, Bounty, Subscription, or Pendle Yield contracts to Base Mainnet.
- `deploy_solana_contract`: Initializes SPL Escrows, cNFT Badge Issuers, or Raydium Vaults on Solana.
- `deploy_arc_contract`: Deploys custom Escrow, Bounty, or Subscription contracts to Arc Mainnet.
