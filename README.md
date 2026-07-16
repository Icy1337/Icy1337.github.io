# Talkimals site (GitHub Pages) — setup

This folder holds the public Talkimals mini-site whose ONLY hard job is serving
`app-ads.txt` at the **domain root** for AdMob.

## ⚠️ The one rule that matters

`app-ads.txt` must be reachable at `https://<domain>/app-ads.txt` — the ROOT.
A normal GitHub repo publishes at `https://<username>.github.io/<repo>/…`
(a subfolder), which **does not work**.

→ The repo must be your **user site** repo, named **exactly** `<username>.github.io`
   (e.g. github username `ariepinto` → repo name `ariepinto.github.io`).
   That repo publishes at `https://<username>.github.io/` — the root.

## Steps

1. On GitHub: create a **public** repo named `<username>.github.io`.
2. Put the contents of this folder in it (`index.html`, `app-ads.txt`, this README)
   and push to `main`.
3. Repo → Settings → Pages → Source: **Deploy from a branch**, Branch: `main` / `/ (root)`.
4. Wait a minute, then verify in a browser:
   - `https://<username>.github.io/` → the Talkimals page
   - `https://<username>.github.io/app-ads.txt` → shows exactly:
     `google.com, pub-5183733004398945, DIRECT, f08c47fec0942fa0`
5. App Store Connect → your app → **App Information** → set
   **Marketing URL** = `https://<username>.github.io`
   (AdMob discovers app-ads.txt through the developer/marketing URL on the
   App Store listing — this is required.)
6. After the app is live on the App Store: AdMob → Apps → Talkimals →
   **app-ads.txt** tab → *Check for updates*. Crawling can take up to 24 h
   (AdMob only crawls once the store listing is public).

## Notes

- `index.html` has a `TODO` placeholder for the real App Store link.
- If you later buy a custom domain (e.g. talkimals.com), point it at Pages and
  move `app-ads.txt` with it — then update the ASC Marketing URL to match.
- You will also need a **privacy policy URL** in App Store Connect for a kids
  app — a `privacy.html` can live in this same repo when ready.
