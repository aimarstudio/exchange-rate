# Currency Converter (minimal)

This is a tiny static project that uses ExchangeRate-API to convert currencies.

Files of interest:

- `index.html` – front-end UI that calls `convertCurrency()` from `app.js`.
- `app.js` – UI logic (already present).
- `currency-api.js` – helper that calls the remote API (already present).
- `config.js` – contains the `API_KEY` constant. Replace `YOUR_API_KEY` with a real key.
- `server.js` – small Node static file server to serve the project locally.

Run locally (requires Node.js >= 12):

1. Open `config.js` and replace the placeholder API key:

```js
const API_KEY = "YOUR_REAL_API_KEY";
```

2. Start the server:

```bash
node server.js
```

3. Open http://localhost:3000 in your browser.

Notes:
- If you don't have an API key, the UI will attempt to call the ExchangeRate API and fail; you can mock `getRates` for testing.
- This project intentionally ships without extra dependencies to keep it simple.

Security note:
- `config.js` currently contains an API key-like string. If this is a real, private key you should rotate it and store it securely; avoid committing real secrets to repositories. The app will use a mock fallback when the key is missing.
