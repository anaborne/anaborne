# Immanuel Anaborne

I build trading infrastructure for prediction markets and run pre-registered studies that test whether those markets are priced correctly. Every study below lost to the market or came back null.

Education: University of Pennsylvania, B.A. Computer Science and English, December 2026 conferral, available now.

Location: New York, NY

Languages: Python, C++20, TypeScript, SQL

Contact: immanuel.anaborne@gmail.com | [anaborne.github.io](https://anaborne.github.io) | [Resume (PDF)](https://anaborne.github.io/resume.pdf)

## Trading infrastructure

- Prediction Market Infra: [github.com/anaborne/prediction-market-infra](https://github.com/anaborne/prediction-market-infra), a two-process Kalshi and Polymarket trading system where a poller decides what to trade and a pre-warmed executor submits it over a Unix domain socket; 395 offline tests.
- Executor Hot Path in C++: [github.com/anaborne/executor-hotpath-cpp](https://github.com/anaborne/executor-hotpath-cpp), the same executor rewritten in C++20 and driven by the unmodified Python poller across 4,400 frames; wake_recv 2.8x lower at p50 under uvloop, an upper bound because the two configurations differ in process topology; 92 tests.
- Settlement Reconciliation: [github.com/anaborne/settlement-reconciliation](https://github.com/anaborne/settlement-reconciliation), dbt models reconciling a 281-decision trade ledger against a 263-row Kalshi settlement feed at a 93.59% match rate; 82 data tests, and 15 of 15 controls proven to fail when their fault is injected.

## Market studies

- Kalshi Prop Calibration: [github.com/anaborne/kalshi-prop-calibration](https://github.com/anaborne/kalshi-prop-calibration), NFL and NBA player props against free public data. The headline is a null; the finding is that the midpoint convention stops being a probability when one side of the book is absent, which happens on 16.0% of 102,860 scored observations.
- NFL Pricing Model: [github.com/anaborne/nfl-pricing-model](https://github.com/anaborne/nfl-pricing-model), a walk-forward Elo over 272 games graded against the de-vigged market moneyline; Brier 0.224 against the market's 0.212.
- Cross-Venue: [github.com/anaborne/cross-venue](https://github.com/anaborne/cross-venue), whether Kalshi and Polymarket US game moneylines are the same contract; 0 of 74 matched pairs were settlement-identical, and the study stopped at its first gate.

## Tools

- MCP servers: [gdrive-write-mcp](https://github.com/anaborne/gdrive-write-mcp) (in-place Google Drive writes guarded by revision tokens) and [gmail-multi-mcp](https://github.com/anaborne/gmail-multi-mcp) (several Gmail accounts open at once, sending off by default); MIT, CI on Node 18, 20 and 22.
- Freshli: [github.com/anaborne/freshli](https://github.com/anaborne/freshli), a Next.js 15 food-inventory app whose refactor into tested pure functions turned up five live defects; 40 tests run across four timezones.

## Experience

- Wharton Accounting Department, Data Engineering Research Assistant, June 2025 to June 2026: built a RAG pipeline over the OpenAI API that cut manual disclosure-classification effort by 50 percent, and an async ingestion service that parsed more than 60,000 corporate filings.
- GoodRun, Software Engineer Intern, May 2024 to August 2024: shipped an in-house React feedback tool that replaced a paid vendor, and cut production deployment failures 15% by hardening CI/CD in GitHub Actions.
