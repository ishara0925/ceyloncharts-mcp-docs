# Changelog

Notable changes to the hosted CeylonCharts MCP/REST service. This repo holds
docs only — see [SECURITY.md](SECURITY.md) for the security reporting
process and [docs/acknowledgments.md](docs/acknowledgments.md) for
researcher credits.

## 2026-09-22

- **Security:** hardened OAuth dynamic client registration — self-registered
  clients are now flagged unverified until reviewed, verification is checked
  per redirect origin rather than per client, refresh tokens now expire, and
  registration is rate-limited. Reported by
  [MD Rabbi Hossain](https://x.com/csrrabbi) through responsible disclosure —
  see [docs/acknowledgments.md](docs/acknowledgments.md).
