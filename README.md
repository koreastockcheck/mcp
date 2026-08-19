# KoreaStockCheck MCP Server

**Background checks for Korean stocks — inside your AI assistant.**

KoreaStockCheck is a remote [MCP](https://modelcontextprotocol.io) (Model Context Protocol) server that lets Claude and other MCP-capable AI assistants look up the public regulatory filing history of any company listed on the Korea Exchange (KOSPI / KOSDAQ) — in English.

Ask your assistant *"What has Samsung Electronics actually filed?"* or *"Show me this KOSDAQ company's dilution history"* and it answers from ten years of official filings, with every claim linked to the original government document.

## What the data is

All data comes from **DART** (dart.fss.or.kr), the Korean government's official corporate disclosure system — the Korean equivalent of the SEC's EDGAR. The server covers **all ~3,400 listed companies** with ten years of filing history, updated every Korean business day:

- Rights offerings, convertible bonds, bonds with warrants (dilution history)
- Capital reductions and treasury-share actions
- Audit opinions and auditor changes
- Exchange sanctions, trading suspensions, delisting records
- Embezzlement / breach-of-trust disclosures

**What it is not:** no buy/sell recommendations, no price targets, no forecasts, no investment advice. Facts from filings only — every response links to the source document. The risk scoring methodology is validated against official KRX delisting outcomes and [published openly](https://koreastockcheck.com/method.html).

## Connect to Claude

1. Get your personal access key at [koreastockcheck.com](https://koreastockcheck.com) ($9/month, cancel anytime — key arrives by email).
2. In Claude: **Settings → Connectors → Add custom connector**, and paste your personal server URL:

```
https://mcp.koreastockcheck.com/mcp/<your-key>
```

3. Ask about any Korean stock by name or 6-digit ticker. Example prompts:

```
List 삼성전자 (005930)'s capital raises from the last five years.
Summarize the filing history of Celltrion.
Which filings preceded this company's trading suspension?
```

The server speaks streamable-HTTP MCP and works with any MCP client that supports remote servers with URL-embedded auth.

## Fair use

Personal subscriptions include 300 checks per month (up to 30/day) across web reports and AI calls. Bulk extraction, redistribution, and building competing datasets are not permitted — see [Terms](https://koreastockcheck.com/terms.html). Need the dataset or a team license? support@koreastockcheck.com

## Links

- Website: https://koreastockcheck.com
- Sample reports: https://koreastockcheck.com/samples.html
- Methodology & validation: https://koreastockcheck.com/method.html
- Support: support@koreastockcheck.com

---

*Facts from public DART filings. Not investment advice. © KoreaStockCheck*
