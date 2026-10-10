# Portvan: branded IPFS gateways, ordered by API

Portvan sets up a branded IPFS gateway on your own domain. Orders go through MCP or REST; payment is an exact USDT amount on TRON (TRC20), so no card is needed.

- Website: https://portvan.brandone.ir
- MCP endpoint (Streamable HTTP): `https://portvan.brandone.ir/mcp`
- Discovery files: `https://portvan.brandone.ir/llms.txt`, `https://portvan.brandone.ir/openapi.json`, `https://portvan.brandone.ir/agent/catalog`

## Connect

```
claude mcp add --transport http portvan https://portvan.brandone.ir/mcp
```

```json
{ "mcpServers": { "portvan": { "type": "http", "url": "https://portvan.brandone.ir/mcp" } } }
```

## Tools

| Tool | What it does |
|---|---|
| `portvan_catalog` | Plans, prices and payment rules (free). |
| `portvan_create_order` | Creates an order for a domain and CID; returns the exact USDT amount and the TRON address. |
| `portvan_order_status` | Order status: pending, paid, expired or needs_review. |

## Payment

Send exactly the returned amount of USDT (TRC20) within 15 minutes; the unique amount identifies the order. On-chain payments are irreversible, so check the domain and CID first. Plans start at 15 USD per month.

- Source and issues: https://github.com/parvizrahayan/portvan-mcp-server
