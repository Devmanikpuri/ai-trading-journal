# Trading Journal Tracker

A full-stack, multi-portfolio trading journal focused on **daily profit/loss tracking** and performance review.

## Features
- Multiple trading portfolios/accounts
- Initial capital per portfolio
- One daily P&L entry per date (editing the same date updates it)
- Automatic current balance and cumulative return
- Dashboard metrics: initial capital, current balance, total P&L, total return, winning/losing days
- Daily performance calendar
- Weekly performance calendar with each day's P&L
- Monthly performance summaries
- Responsive frontend for desktop and mobile
- SQLite persistence through an Express REST API
- JSON-friendly API design
- No AI, image upload, broker integration, or API key required

## Stack
- Frontend: HTML, CSS, vanilla JavaScript
- Backend: Node.js + Express
- Database: SQLite via better-sqlite3
- Deployment: Docker / Render configuration

## Run locally
```bash
npm install
npm start
```
Then open `http://localhost:3000`.

## Data model
`portfolios` stores account name, initial capital and currency. `daily_entries` stores one P&L result per portfolio/date plus optional notes. The server calculates balance and return from the initial capital and accumulated daily results.

## Disclaimer
This is a record-keeping and analytics application. It does not provide financial advice or trading recommendations.
