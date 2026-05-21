# Quick Maths — legal pages

Static pages for the two URLs App Store Connect **requires**:

- **Privacy Policy URL** → `privacy/index.html`
- **Support URL** → `support/index.html`

`index.html` is an apex landing page that links to both. No domain
purchase needed — host free on GitHub Pages.

## Deploy on GitHub Pages (free, ~5 min)

1. Create a new **public** GitHub repo, e.g. `quickmaths-legal`.
2. Copy the contents of this `legal/` folder into the repo root so the
   structure is:
   ```
   index.html
   privacy/index.html
   support/index.html
   ```
3. Push to the `main` branch.
4. Repo **Settings → Pages** → Source: `Deploy from a branch` →
   Branch: `main` / folder: `/ (root)` → **Save**.
5. Wait ~1 minute. The pages go live at:
   - `https://<your-username>.github.io/quickmaths-legal/`
   - `https://<your-username>.github.io/quickmaths-legal/privacy/`
   - `https://<your-username>.github.io/quickmaths-legal/support/`
6. Verify each URL loads over **HTTPS** in a browser.

## What to paste into App Store Connect

| ASC field | Value |
|---|---|
| Privacy Policy URL | `https://<username>.github.io/quickmaths-legal/privacy/` |
| Support URL | `https://<username>.github.io/quickmaths-legal/support/` |
| Marketing URL (optional) | `https://<username>.github.io/quickmaths-legal/` |

Apple accepts any reachable HTTPS URL — a `github.io` address is fine.

## Updating later

Edit the HTML, push to `main`, GitHub Pages redeploys within a minute.
If you change the Privacy Policy meaningfully, also bump the
"Effective date" line in `privacy/index.html` and mention it in the
app's next release notes.

## If you later buy a domain

Only one feature actually needs a domain: AdMob's `app-ads.txt` (ad-
fraud verification) must sit at a domain root, which you can't do on
`github.io`. It's optional and not a launch blocker. If you buy
`quickmaths.app` / `.io` later, point a CNAME at GitHub Pages and add
`app-ads.txt` then.

## Keeping in sync with the app

The in-app Settings → About and the hosted Privacy Policy should not
contradict each other. Current facts both must reflect:

- No account, no sign-up, no backend server
- All game data stored on-device only (`UserDefaults`)
- Free app, supported by Google AdMob banner ads
- No in-app purchases in v1.0
- ATT prompt on first launch; declining = non-personalised ads
- Online multiplayer is **not** in v1.0 (post-launch feature)
- Heads-Up two-player mode is ad-free for everyone
