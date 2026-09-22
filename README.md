<p align="center">
  <img src="assets/logo-text-light-1024.png" alt="CeylonCharts" width="100%">
</p>

[![CeylonCharts - Colombo Stocks Exchange (CSE) data for AI Agents MCP connector – tool definition quality and endpoint health on Glama](https://glama.ai/mcp/connectors/com.ceyloncharts.mcp/ceylon-charts/badges/score.svg)](https://glama.ai/mcp/connectors/com.ceyloncharts.mcp/ceylon-charts)

# CeylonCharts MCP Server

Colombo Stock Exchange (CSE) market data — symbols, OHLC price history (with
corporate-action adjustments), live price quotes, candlestick chart images,
full financial statements, foreign-shareholding percentage, top-20
shareholders, corporate announcements, a corporate-actions calendar,
market/sector indices, pre-computed technicals, a market screener, market
summaries, and macroeconomic indicators — available as:

- A **REST API** (`https://mcp.ceyloncharts.com/api`)
- An **MCP server** (`https://mcp.ceyloncharts.com/mcp/`) for AI agents and assistants
  such as Claude

This repository documents how to connect to the hosted server and how to call its
endpoints. It does not contain the server's source code.

## Contents

- [Getting Started](docs/getting-started.md) — connect from Claude Web, ChatGPT, Antigravity, Claude Desktop, or plain HTTP
- [MCP Tools Reference](docs/mcp-tools.md) — the seventeen tools exposed over MCP
- [REST API Reference](docs/rest-api.md) — endpoints, params, response shapes
- [Authentication](docs/authentication.md) — API keys and OAuth
- [Rate Limits](docs/rate-limits.md) — plan tiers and limits
- [Examples](examples/) — runnable curl, Python, and Node snippets
- [AGENTS.md](AGENTS.md) / [SKILL.md](SKILL.md) — condensed reference for coding agents (base URLs, auth, gotchas, endpoint table)
- [SECURITY.md](SECURITY.md) — how to report a vulnerability
- [Changelog](CHANGELOG.md) — notable changes to the hosted service
- [Security Acknowledgments](docs/acknowledgments.md) — researchers who've helped us, credited with permission

## Available MCP Tools

| Tool | Description |
|------|-------------|
| `get_symbols` | List/search CSE-listed companies |
| `get_ohlc_data` | Daily/weekly/monthly OHLC price history |
| `get_financial_statement` | Full income statement, balance sheet, or cash flow statement detail |
| `get_announcements` | General CSE disclosures (board changes, AGM/EGM, suspensions, etc.) |
| `get_corporate_actions` | Corporate-actions calendar: dividends, rights issues, share splits |
| `get_foreign_holdings` | Daily foreign-shareholding percentage series for a symbol |
| `get_top20_shareholders` | Top-20 ranked shareholder list for a company, by quarter |
| `get_macro_series` | List available macroeconomic series |
| `get_macro_data` | Macroeconomic indicator data |
| `get_indices` | List CSE market/sector indices (ASPI, S&P SL20, industry sub-indices) |
| `get_index_data` | Historical data for a market/sector index |
| `get_technicals` | Pre-computed daily technicals (moving averages, RS rating, 52-week range) for a stock or index |
| `screen_stocks` | Screen CSE stocks by technical criteria (trend, RS rating, 52-week range, volume) |
| `screen_indices` | Screen sector/headline indices by trend and RS rating |
| `get_market_summary` | Daily/weekly/monthly market overview: top gainers/losers, activity leaders, index/sector performance |
| `get_quotes` | Live price snapshot for one or more CSE stocks, or every CSE stock at once |
| `get_chart` | Candlestick + volume chart image (PNG) for a CSE symbol |

> `get_financials` (compact multi-quarter revenue/income/EPS trend) is
> currently disabled as an MCP tool in favor of `get_financial_statement` —
> the underlying `GET /v1/financials/:symbol` REST endpoint is still live,
> see [docs/rest-api.md](docs/rest-api.md#financial-statements).

See [docs/mcp-tools.md](docs/mcp-tools.md) for full input/output shapes.

## Quick Example

```bash
curl -H "X-User-Id: <your-user-id>" \
     -H "X-Api-Key: <your-api-key>" \
     https://mcp.ceyloncharts.com/api/v1/symbols
```

## Getting Access

API keys are self-service from your CeylonCharts account — see
[docs/authentication.md](docs/authentication.md) for how to generate one.

## For Coding Agents

[AGENTS.md](AGENTS.md) and [SKILL.md](SKILL.md) hold the same condensed
reference (base URLs, auth, common gotchas, an endpoint/tool table) in two
formats — `AGENTS.md` for the general cross-tool convention, `SKILL.md` with
Claude Skill frontmatter. If you're working in Claude Code and want it
auto-discovered as a skill in your own project, copy `SKILL.md` to
`.claude/skills/ceyloncharts-mcp/SKILL.md` there.

## License

- Code samples in [examples/](examples/) are licensed under [MIT](LICENSE).
- Documentation in [docs/](docs/) is licensed under [CC BY 4.0](LICENSE-DOCS).
