# ippun — marketing & support site

Static site for Apple App Store submission. Hosts the required Support URL and Privacy Policy URL plus a landing page.

## Structure

```
.
├── index.html        # Landing
├── support.html      # Support URL for App Store Connect
├── privacy.html      # Privacy Policy URL for App Store Connect
├── assets/
│   ├── style.css
│   └── mark.svg      # Brand mark / favicon
└── .nojekyll         # Tells GitHub Pages to skip Jekyll processing
```

No build step. Pure HTML/CSS, one Google Fonts link, no JS dependencies.

## On Policy Update

Update the "Last updated" date in `privacy.html` whenever you materially change the policy.

## Deploy to GitHub Pages

1. Push this folder to a GitHub repository (e.g. `ippun-site`).
2. In the repo, go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait ~1 minute. Your site will be live at:
   - `https://<your-username>.github.io/<repo-name>/`

### URLs to paste into App Store Connect

- **Support URL** → `https://<your-username>.github.io/<repo-name>/support.html`
- **Privacy Policy URL** → `https://<your-username>.github.io/<repo-name>/privacy.html`

### Custom domain (optional, later)

When you're ready to move off `github.io`:

1. Add a `CNAME` file at the repo root containing your domain (e.g. `ippun.app`).
2. Point the domain's DNS at GitHub Pages (A records to GitHub's IPs, or a CNAME to `<user>.github.io`).
3. Update the two URLs in App Store Connect. Changes apply at the next metadata submission — no new binary needed.

## Local preview

Any static file server will do:

```sh
python3 -m http.server 8000
# open http://localhost:8000
```

## License

All rights reserved.
