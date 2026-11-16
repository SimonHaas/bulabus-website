# BulaBus website

Static landing page and app-store handoff page for [bulabus.org.fj](https://bulabus.org.fj), published with GitHub Pages.

## Publish with GitHub Pages

1. Create a GitHub repository named `bulabus-website` and push this repository to its `main` branch.
2. In **Settings → Pages**, set **Source** to **GitHub Actions**.
3. In **Settings → Pages → Custom domain**, enter `bulabus.org.fj` and save. The `public/CNAME` file is included as a record of the intended domain; the custom domain must also be set in the repository settings for an Actions deployment.
4. At your DNS provider, point the apex domain `bulabus.org.fj` to GitHub Pages using the A/AAAA records listed in [GitHub's custom-domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site). Add a `www` CNAME to `<your-github-username>.github.io` only if you want that hostname too.
5. Push to `main`; the workflow deploys the files in `public/`.

## App-store URLs

Edit the `STORE_URLS` object in `public/app/index.html` when the store listings are available. The page detects iOS and Android phones and redirects only after its platform URL has been replaced with a real listing. Until then, it shows a clear “coming soon” message. Desktop visitors see both store options.

## Local preview

Serve `public/` with any static file server, for example:

```sh
python3 -m http.server 8080 --directory public
```

Then open `http://localhost:8080` or `http://localhost:8080/app/`.
