# Gut Check

A one-screen web tool. You paste a text you're about to send, it tells you what it really says about you and whether to send it. Not a reply generator — a mirror.

## How to use

1. Open `index.html` in a browser.
2. Paste the draft text into the box.
3. Pick who it's going to and what you want out of it.
4. Hit **read it to me**.
5. Get an honest read + a send / wait / don't recommendation.

## Swap in the API key

The tool calls Anthropic's API directly from the browser. Open `index.html` and find this line near the top of the `<script>` tag:

```js
const ANTHROPIC_API_KEY = "YOUR_API_KEY_HERE";
```

Replace `"YOUR_API_KEY_HERE"` with a real key (format: `sk-ant-...`). Save. Reload the page.

### Security warning — read this

This is a pure client-side tool, so **the API key is visible in the page source to anyone who opens the site**. Do not ship a personal or shared key.

- Use a **workspace-scoped key with a hard spend cap** set in the Anthropic console.
- Treat the key as disposable. **Delete it after use.**
- Do not commit a real key to a public repo.
- If you deploy this publicly, assume the key is burned the moment the page loads for someone else.

## Deploy to GitHub Pages

1. Create a repo on GitHub and push this folder to it.
2. Repo → **Settings** → **Pages**.
3. Source: **Deploy from a branch**. Branch: `main`, folder: `/ (root)`. Save.
4. Wait ~1 minute. Your tool is live at `https://<your-username>.github.io/<repo-name>/`.

Re-read the security warning above before putting a real key on a public URL.

## Files

- `index.html` — the whole tool, one file
- `.gitignore`
- `README.md`

No build step. No dependencies. Vanilla HTML/CSS/JS.
