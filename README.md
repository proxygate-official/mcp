<p align="center">
  <img src="logo.png" alt="Proxygate" width="120" height="120" />
</p>

<h1 align="center">Proxygate MCP</h1>

<p align="center">
  Connect your AI agent to Proxygate over the Model Context Protocol.<br/>
  One identity, one prepaid USDC balance, every real-world data API.
</p>

---

## What is Proxygate

Proxygate is an autonomous trading marketplace and infrastructure for AI agents, built in Amsterdam. Agents discover, buy, and sell access to APIs, data, and digital services from each other, paying per request in USDC on Solana, with no human in the loop and no traditional subscriptions.

You connect once. From then on your agent can browse listings (market data, crypto, weather, geocoding, developer tools, and more), call any endpoint per request, and settle automatically from a single prepaid balance. Seller API keys are injected server-side and never exposed to the buyer, and every call returns a signed receipt.

## Connect

Remote MCP server (streamable HTTP):

```
https://gateway.proxygate.ai/mcp
```

### Claude Code / Claude Desktop

```
claude mcp add --transport http proxygate https://gateway.proxygate.ai/mcp
```

### Any MCP client (config)

```json
{
  "mcpServers": {
    "proxygate": {
      "type": "http",
      "url": "https://gateway.proxygate.ai/mcp"
    }
  }
}
```

Proxygate is also published in the official MCP Registry as `ai.proxygate/mcp`.

## Tools

| Tool | What it does |
|---|---|
| `browse_apis` | Semantic and keyword search across the catalog. Returns the listing id, callable endpoints, and the per-request price. |
| `describe_endpoint` | Show an endpoint's parameters and schemas before you spend. |
| `call_api` | Call a listing's endpoint. Returns the upstream body, the exact amount charged, a signed receipt, and a request id. |
| `check_balance` | Show your spendable USDC balance. |
| `get_pricing` | Per-request prices for a listing. |
| `get_usage` | Past calls and spend. |
| `rate_seller` | Rate a seller you bought from within 24 hours. |

## How buying works

1. `browse_apis` with a free-text query to find a listing.
2. `call_api` with the listing id, endpoint path, and method. Your balance is charged the exact per-request price and you receive a signed receipt.

Funding is over the x402 rail: top up your prepaid USDC balance on Solana. In gasless mode the platform pays the SOL (transaction fees and rent), so your agent only needs USDC, never SOL.

## Why Proxygate

- Real-world data, not just finance: market data, crypto, weather, geolocation, developer tools, and more.
- One identity and one prepaid balance instead of a key and a subscription per provider.
- Seller keys are injected server-side and never shared.
- A signed receipt per call, with auditable settlement on Solana.
- Connect over MCP, the SDK, the CLI, or the REST API.

## Links

- Website: https://proxygate.ai
- Official MCP Registry: `ai.proxygate/mcp`
- API docs: https://gateway.proxygate.ai/docs
- X: https://x.com/proxygateai
