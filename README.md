# Polish Public Tenders MCP Server

Search open and awarded Polish public tenders (national BZP and EU TED notices) and check which companies win public contracts.

Remote MCP server (Streamable HTTP), read-only, hosted by [Compabase](https://compabase.com/public-tenders).

```
https://compabase.com/api/mcp/tenders
```

## Tools

| Tool | What it does |
|---|---|
| `search_tenders` | Open or awarded notices by industry (IT, construction, healthcare or CPV division), region, city, kind and value. |
| `get_company_public_tenders` | BZP contracts won and notices published by one company. |
| `get_company_eu_tenders` | TED (EU-threshold) contracts and notices for one company. |
| `get_company_eu_funds / get_company_public_aid / get_company_eu_grants` | EU funds, state aid and European Commission grants. |
| `search_companies / get_company` | Identify buyers and contractors (KRS, NIP, financials). |

## Example prompts

- Find open IT tenders in Mazowieckie with a deadline in the next two weeks.
- Which public contracts has Budimex won recently?
- Show awarded construction tenders above 10 million PLN.

## Authentication

Sign in with your Compabase account (OAuth) in clients that support it, or send an MCP key: create one at https://compabase.com/integrations?tab=mcp and pass it as `Authorization: Bearer mcpk_…` or append `?apiKey=mcpk_…` to the URL. Queries count toward your Compabase plan.

## Setup

**Claude (claude.ai, Desktop):** Settings → Connectors → Add custom connector → paste the URL above (add `?apiKey=mcpk_…` if you use a key).

**Cursor / VS Code / Windsurf** (`mcp.json`):

```json
{
  "mcpServers": {
    "polish-public-tenders": {
      "url": "https://compabase.com/api/mcp/tenders",
      "headers": { "Authorization": "Bearer mcpk_YOUR_KEY" }
    }
  }
}
```

**ChatGPT:** Settings → Apps → Developer mode → Create → paste the URL.

## About

Part of the [Compabase](https://compabase.com/docs/mcp/) MCP family. Full Compabase MCP (all Polish company data tools): https://compabase.com/api/mcp.

Questions: contact@compabase.com

## Gemini CLI

```bash
gemini extensions install https://github.com/ContentWriterco/Polish-Public-Tenders-MCP
```

Gemini CLI asks for your Compabase MCP key during installation (create one at https://compabase.com/integrations?tab=mcp).

## Setup guides

Step-by-step setup guides for Claude, ChatGPT, Gemini, Grok, Le Chat, Perplexity, Cursor, VS Code and Claude Code: https://compabase.com/docs/mcp/connect/
