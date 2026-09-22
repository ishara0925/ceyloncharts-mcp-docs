# Security Policy

CeylonCharts takes security reports on the hosted service seriously and
credits researchers who report in good faith.

## Scope

This repository holds documentation only — it has no source code of its own.
The service it documents is in scope:

- `https://mcp.ceyloncharts.com` (REST API and MCP server)
- `https://oauth.ceyloncharts.com` (OAuth authorization server)
- `https://www.ceyloncharts.com` (web app)

## Reporting a Vulnerability

Email **support@creonsolutions.com** with a subject line starting
`[SECURITY]`. Please include:

- A description of the issue and its potential impact
- Steps to reproduce, or a proof-of-concept request/response log
- Any affected endpoint(s) or account(s) you tested against (use your own
  account, not a real customer's, wherever possible)

Please don't run automated scanners against the production service, and
don't access, modify, or delete data beyond what's needed to demonstrate the
issue. If you accidentally see other users' data while investigating, stop,
don't retain it, and mention it in your report.

We aim to acknowledge new reports within 3 business days and to keep you
updated as we investigate and fix. We ask that you give us a reasonable
window to fix a confirmed issue before any public disclosure, and we'll work
with you on timing.

## Safe Harbor

We won't pursue legal action against, or refer to law enforcement, anyone
who makes a good-faith effort to follow this policy: testing only your own
account or data, reporting privately before disclosing publicly, and not
exploiting a finding beyond what's needed to demonstrate it. This safe
harbor doesn't apply to third-party systems, only to CeylonCharts' own.

## Acknowledgments

Researchers who've helped us are credited in
[docs/acknowledgments.md](docs/acknowledgments.md), with their permission.
