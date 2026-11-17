# AnkQuant — Public Architecture Overview

This document intentionally provides only a high-level technical overview suitable for a public portfolio.

## Application tiers

1. **Browser interface:** HTML, CSS and vanilla JavaScript surfaces for scanning, dashboards and journals.
2. **Backend:** Node.js and Express API endpoints, access control, and live data delivery.
3. **Analysis services:** Independent intraday and swing scheduling, market-data collection and technical evaluation.
4. **Persistence:** PostgreSQL/Supabase for applicable journal records, positions and application state.
5. **Notifications:** Telegram alert delivery.
6. **Operations:** Docker-based packaging, deployment configuration and automated testing.

## Design considerations

- Keep market-data credentials and application secrets server-side.
- Separate intraday and swing evaluation to preserve different lifecycle requirements.
- Design failure handling so unexpected market-data conditions do not disrupt all analysis.
- Use durable persistence for information that must survive restarts.
- Provide controlled client-facing API responses rather than shipping proprietary calculation code to the browser.

## What this showcase does not disclose

Internal strategy parameters, full database schemas, account configuration, access credentials, operational runbooks and implementation source code.

**Live demo:** https://ankquant.in
