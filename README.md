# Alisan Project Cost Tracking System (PWA)

Frontend = static PWA on **GitHub Pages**. Backend = **Google Apps Script** + your Google Sheet (unchanged data model and login system).

## Files
| File | Where it goes |
|---|---|
| `Code.gs` | Apps Script project (backend) |
| `index.html`, `styles.css`, `app.js`, `config.js`, `manifest.json`, `sw.js`, `icons/`, `.nojekyll` | GitHub repo root |

## 1. Backend (Apps Script)
1. Open your Google Sheet > Extensions > Apps Script.
2. Replace the contents of `Code.gs` with the `Code.gs` in this folder. **Delete the old `Index.html` file** from the Apps Script project (no longer used).
3. Deploy > New deployment > type **Web app** > Execute as **Me** > Who has access **Anyone** > Deploy. Authorise when asked.
4. Copy the **Web app URL** (ends in `/exec`).
5. Whenever you later edit `Code.gs`: Deploy > Manage deployments > pencil icon > Version: **New version** > Deploy (the URL stays the same).

## 2. Frontend (GitHub Pages)
1. Open `config.js` and paste the `/exec` URL between the quotes.
2. Create a GitHub repository and upload everything except `Code.gs` and `README.md` (they are harmless if uploaded, but `Code.gs` is not needed there).
3. Repo > Settings > Pages > Source: **Deploy from a branch** > Branch `main`, folder `/ (root)` > Save.
4. Your app is live at `https://<username>.github.io/<repo>/` in a minute or two.

## 3. Install
- Android/Chrome: menu > Install app.
- iPhone/Safari: Share > Add to Home Screen.
- Desktop Chrome/Edge: install icon in the address bar.

## Notes
- The first account registered becomes Administrator; later accounts need approval in the Users page.
- The app needs internet; only the app shell is cached for fast opening.
- After updating the frontend, bump `CACHE` in `sw.js` (e.g. `alisan-shell-v2`) so phones pick up the change.
- Keep the Google Sheet private; staff only use the app login.
