# Browser Tools

This skill allows Pi to use sandboxed browser sessions from your local profiles.
It's part of the Screenpipe Zero Setup flow (#2386).

## Capabilities

- **Browser automation**: Use Playwright/Puppeteer with local browser profiles (Chrome, Arc, Brave, etc.)
- **Bypass Auth**: Access websites where you are already logged in locally
- **Sandboxed**: Browser instances are isolated from your primary browsing

## How to Use

Simply set `browser: true` in your skill metadata. Screenpipe will prepare a 
sandboxed profile for Pi.

### Example: Sync Profile

You can trigger a profile sync from settings or via the API:
`POST /skills/browser/sync`

## Notes

- Requires browser profile sync to be enabled in settings
- Works with Chromium-based browsers
- Provides seamless authentication for many web-based skills
