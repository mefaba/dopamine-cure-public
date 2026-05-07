## Known Limitations

- Timers depend on Chrome extension alarms and session storage behavior.
- There is no automated test suite yet.
- Removing a domain clears its active session and unregisters its script, but already-open pages may need reload behavior verified.
- The extension currently redirects expired tabs to `chrome://newtab`.
- UI and logic are Chrome-focused; other Chromium browsers may need validation.

## Development

```bash
npm install
npm run build
npm run start:chrome
```

Use `npm run dev` only for the Vite UI development server; extension behavior requires a built `dist/` directory loaded in Chrome.

### Fast Dev Refresh

Run the extension with automatic rebuilds and browser extension reloads:

```bash
npm run dev:extension
```

This performs an initial full build, starts Vite watch builds for the options page, background worker, and content script, then launches Chromium through `web-ext` with `dist/` loaded as the extension. Keep this command running while editing extension code.
