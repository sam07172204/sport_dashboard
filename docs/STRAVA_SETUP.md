# Strava OAuth setup

1. Configure STRAVA_CLIENT_ID and STRAVA_CLIENT_SECRET in Vercel encrypted environment variables.
2. Set Strava authorization callback domain to the deployed hostname (without https:// or a path).
3. The connect endpoint sets a short-lived HTTP-only OAuth state cookie and redirects to Strava.
4. The callback currently validates state and intentionally DOES NOT exchange the code until a private authenticated token vault is ready. This prevents accidental exposure or unsafe multi-user token storage.
5. Next: add Supabase Auth, per-user encrypted token storage and exchange, refresh, activity sync, and UI connection state.
