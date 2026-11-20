# MerchantMind

Software for small shops: a PostgreSQL/FastAPI backend, a Next.js frontend and a pure-Python analytics
package. Verified merchant accounts, customers and consent, product costs and stock, paid and credit
sales, a credit ledger with a customer acknowledgement portal, reviewed offers, loyalty, consent-based
retention drafts, an encrypted mail outbox, CSV imports, simulated reward campaigns, calculated analytics
with English/Hindi summaries, and customer insights (segments, "not seen recently", a payment-behaviour
guide). MerchantMind records payments received; it does not process payments. Forecasts need explicitly
complete history.

## Quick start

Needs Python 3.12+, Node.js and a local PostgreSQL (Docker is optional). Full steps: [docs/setup.md](docs/setup.md).

```bash
make install
python scripts/create_local_env.py     # private keys in .env (git-ignored)
npm ci --ignore-scripts
# set DATABASE_URL / TEST_DATABASE_URL in .env, then:
make migrate
make run                               # API on :8000
npm run dev                            # frontend on :3000 -> /account
```

Tests wipe every table and only run against a database whose name ends in `_test`.
Verify with `make lint`, `make check-contracts`, `make test`, `npm test`, `npm run build`, `make test-live`.

## Documentation

Start with
[setup](docs/setup.md) · [architecture](docs/architecture.md) · [API contracts](docs/api-contracts.md) ·
[analytics methodology](docs/analytics-methodology.md) · [churn benchmark](docs/churn-benchmark.md) ·
[status and limits](docs/status.md) · [backend learning guide](docs/backend-learning-guide.md).

Public deployment is paused; nothing here has been published or has contacted anyone.
