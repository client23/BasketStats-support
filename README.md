# BasketStats Support Site

This folder contains the static public support website for BasketStats.

Contents:

- `index.html`
- `support.html`
- `privacy-policy.html`
- `terms.html`
- `404.html`
- `styles.css`
- `.well-known/apple-app-site-association.sample.json`

Purpose:

- App Store support URL
- App Store privacy policy URL
- public legal and support contact pages

Public App Store URL:

- `https://apps.apple.com/app/basketstats-pro/id6757268387`

Deployment:

- local/manual deployment uses `zsh Scripts/deploy_support_site.sh`
- CI deployment is wired through `.github/workflows/ios-build.yml`
- CI syncs this folder into the dedicated support repository:
  - `git@github.com:client23/BasketStats-support.git`

Required GitHub secret for CI:

- `SUPPORT_REPO_SSH_KEY`

That secret should contain an SSH private key with push access to the support repository.

Local preview:

```sh
cd SupportSite
python3 -m http.server 8000
```

Then open:

- `http://localhost:8000`

Notes:

- `404.html` keeps GitHub Pages fallback behavior clean
- `.well-known/apple-app-site-association.sample.json` is a placeholder template only; it is not active until renamed and populated with real app identifiers
