# 🤖 AI Trading Journal

A portfolio-ready full-stack trading journal that combines trade tracking, performance analytics, behavioral insights and optional LLM-powered reviews.

## Stack
- **Frontend:** responsive HTML/CSS/JavaScript dashboard
- **Backend:** Node.js + Express REST API
- **Database:** SQLite with `better-sqlite3`, WAL mode
- **AI:** OpenAI Responses API with a deterministic fallback when no API key is configured
- **Deployment:** Docker + Render blueprint

## Features
- Create, list and delete trades
- Long/Short P&L and R-multiple calculations
- Win rate, profit factor, average win/loss and max drawdown
- Equity curve visualization
- Setup and emotion aggregation
- JSON export
- AI journal review focused on performance, behavior and risk discipline
- API health endpoint
- Secrets kept in environment variables
- Persistent SQLite disk configuration for Render
- Responsive mobile-first interface

## Run locally

Requirements: Node.js 20+

```bash
npm install
cp .env.example .env
npm start
```

Open `http://localhost:3000`.

To enable LLM reviews, put your OpenAI API key in `.env`:

```env
OPENAI_API_KEY=your_key_here
OPENAI_MODEL=gpt-5-mini
```

If the key is absent, `/api/ai/review` uses a local deterministic coach instead of failing.

## API

- `GET /api/health`
- `GET /api/trades`
- `POST /api/trades`
- `DELETE /api/trades/:id`
- `DELETE /api/trades`
- `GET /api/analytics`
- `POST /api/ai/review`

## Deployment

The included `Dockerfile` can run the app on any Docker-compatible host. `render.yaml` provides a Render blueprint with a persistent disk mounted at `/data` so the SQLite database survives deploys/restarts.

Set `OPENAI_API_KEY` as a secret in the deployment provider. Never commit `.env` or API keys.

## Project structure

```text
.
├── index.html
├── server.js
├── package.json
├── .env.example
├── .gitignore
├── Dockerfile
├── render.yaml
└── README.md
```

## Product roadmap

- Authentication and multi-user workspaces
- Cloud PostgreSQL/Supabase option
- Broker CSV/API imports
- Trade screenshots and chart annotations
- Advanced charts and calendar heatmaps
- AI weekly/monthly reports
- Strategy backtesting module
- Automated risk rules and alerts

> **Disclaimer:** This project provides journaling and educational analytics. It does not provide financial advice, guaranteed returns, or automated trading signals.
