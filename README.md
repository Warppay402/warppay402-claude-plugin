# WarpPay402 Claude Code Plugin

> Ultra-low-cost pay-per-use Web3 developer tools for web extraction, analytics, DeFi execution, and smart contract deployment, monetized via x402 USDC micropayments.

## Overview

The WarpPay402 plugin provides a curated set of developer tools served through the MCP gateway at `https://api.warppay402.com/mcp`. Tool access is gated by the x402 payment flow and supports Base, Arc, Arbitrum, and Solana mainnet endpoints.

## Features

- Multi-chain support across Base, Arc, Arbitrum, and Solana
- 21 tool endpoints covering scraping, extraction, analytics, DeFi, and deployment
- x402-based USDC payment challenges using HTTP 402 flows
- Public telemetry and attestation data feeds
- Remote gateway execution with non-custodial payment verification

## Quickstart

### Option 1: Load the plugin locally in Claude Code

The Claude plugin manifest lives in `.claude-plugin/plugin.json`, so point the CLI at that folder directly:

```bash
claude --plugin-dir ~/projects/warppay402-claude-plugin/.claude-plugin
```

### Option 2: Add the MCP gateway to your workspace

Create or update `.mcp.json` with the server definition below:

```json
{
  "mcpServers": {
    "warppay402": {
      "url": "https://api.warppay402.com/mcp",
      "type": "http"
    }
  }
}
```

This repository already includes the configured server manifest in `.mcp.json`.

## Supported x402 payment networks

- Base Mainnet (`eip155:8453`): native USDC at `0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913`
- Arc Mainnet (`eip155:5042`): native USDC at `0x0000000000000000000000000000000000000000`
- Arbitrum One (`eip155:42161`): USDC at `0xaf88d065e77c8cC2239327C5EDb3A432268e5831`
- Solana Mainnet (`solana:5eykt4UsFv8P8NJdTREpY1vzqKqZKvdp`): SPL USDC at `EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v`

## Tool catalog

| Tool name | Price (USDC) | Category | Description |
| --- | ---: | --- | --- |
| `x402_telemetry_feed` | Free | Telemetry | Public x402 transaction volume, uptime, and settlement evidence |
| `public_data_feed` | $0.0001 | Data Feed | Signed public attestation records in JSON format |
| `data_feeds` | $0.001 | Data Feed | Pre-scraped AI data, market, and yield feeds |
| `web_scraper` | $0.001 | Extraction | Converts public webpages into clean Markdown |
| `browser_scraper` | $0.005 | Extraction | Dynamic JS rendering through headless browser workers |
| `pdf_extractor` | $0.005 | Extraction | Extracts text from public PDF URLs |
| `render_screenshot` | $0.010 | Extraction | Captures rendered webpage screenshots |
| `extract_json` | $0.010 | Extraction | Extracts structured JSON data from HTML pages |
| `arc_analytics` | $0.001 | Analytics | Live Arc block height, gas prices, and RPC latency |
| `arc_dex_oracle` | $0.001 | Analytics | Real-time ETH/USDC price and DEX liquidity oracle |
| `arc_network_oracle_query` | $0.100 | Analytics | Pre-flight Arc telemetry: gas, latency, merchant balance, and nonce |
| `base_analytics` | $0.002 | Analytics | Fetches ETH balance and nonce for Base addresses |
| `smart_contract_verifier` | $0.020 | Verification | Source code analysis, ABI fetch, and proxy validation |
| `get_aerodrome_yields` | $0.003 | DeFi | Fetches top Aerodrome yield pools, APYs, and TVL |
| `aerodrome_swap` | $0.010 | DeFi | Executes low-slippage swaps on Aerodrome |
| `aerodrome_clamm` | $0.010 | DeFi | Manages concentrated liquidity ranges and collections |
| `aerodrome_veaero` | $0.010 | Governance | Locks AERO, votes on gauge epochs, and claims bribes |
| `arc_cctp_bridge` | $0.250 | Cross-chain | Bridges USDC from Arc to Base, Arbitrum, Ethereum, or Solana |
| `deploy_contract` | $5.000 | Deployment | Deploys escrow, bounty, subscription, and Pendle contracts to Base |
| `deploy_solana_contract` | $5.000 | Deployment | Deploys SPL escrow, cNFT badge, and Raydium vault contracts |
| `deploy_arc_contract` | $5.000 | Deployment | Deploys escrow, bounty, and subscription contracts to Arc |

## Security and isolation

This plugin separates tool execution from direct local shell or filesystem access:

- Local filesystem reads or shell execution are constrained by Claude Code permission settings.
- Remote execution routes through HTTPS gateway endpoints on `https://api.warppay402.com`.
- All protected tool calls require valid x402 payment authorization before execution.

## 📜 Discovery & Specification Endpoints

### 🤖 AI Agent & MCP Specs
* **LLMs.txt Context Map:** `https://api.warppay402.com/llms.txt`
* **MCP Gateway Endpoint:** `https://api.warppay402.com/mcp`
* **MCP Server Manifest:** `https://api.warppay402.com/.well-known/mcp.json`
* **x402 Commerce Manifest:** `https://api.warppay402.com/.well-known/x402-manifest.json`
* **Agent Card Manifest (A2A Standard):** `https://api.warppay402.com/.well-known/agent.json`
* **Agent Offers Catalog:** `https://api.warppay402.com/agent-offers.json`
* **OpenAPI 3.1 Spec:** `https://api.warppay402.com/openapi.json`
* **Glama MCP Connector:** `https://api.warppay402.com/.well-known/glama.json`

### ⛽ ERC-4337 / ERC-7677 Paymaster Services
* **Paymaster Quote Endpoint (v0.8):** `https://api.warppay402.com/api/v1/paymaster/quote`
* **Paymaster RPC Relay (ERC-7677):** `https://api.warppay402.com/api/v1/paymaster/rpc`

### 📊 Verification, Feeds & Wallet Utilities
* **Live Settlement Telemetry:** `https://api.warppay402.com/api/v1/telemetry/settlements`
* **Attestation Feed Index:** `https://api.warppay402.com/api/v1/feeds/index`
* **Fiat-to-USDC Onramp:** `https://api.warppay402.com/onramp`

## Repository metadata

- Plugin manifest: `.claude-plugin/plugin.json`
- MCP workspace config: `.mcp.json`
- Plugin name: `warppay402-gateway`
- Author: WarpPay402 Studio
- Homepage: `https://www.warppay402.com`
- Repository: `https://github.com/Warppay402/warppay402-claude-plugin`

## Notes

- The x402 flow returns an HTTP 402 challenge when a request is unauthenticated.
- The repository includes both the Claude plugin metadata and the workspace MCP manifest for immediate local wiring.
- The tool catalog is based on the current plugin and skill documentation in this workspace.