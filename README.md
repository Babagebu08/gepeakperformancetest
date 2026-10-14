# GE Peak Performance website

Static site (HTML, CSS and a little JavaScript, no build step). Performance wear (men, women and modest sets), personal training and football coaching in Birmingham.

## Files

- `index.html`: the whole site
- `404.html`: page shown for broken links
- `img/`: all photos and the logo mark
- `robots.txt`, `.nojekyll`: search and hosting settings
- `.github/workflows/pages.yml`: optional automatic deployment (Route B)

## Launch on GitHub Pages

Free GitHub Pages needs a **public** repository.

### Route A: simplest (no command line)

1. Sign in at github.com and click **New repository**. Name it `gepeakperformance` (or `YOUR-USERNAME.github.io` to serve from the root address). Set it to **Public** and create it.
2. Click **Add file > Upload files**, drag in everything in this folder (including the `img` folder), and commit to `main`.
3. Go to **Settings > Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose `main` and `/ (root)`, then **Save**.
4. After a minute or two the live address appears at the top of the Pages screen.

### Route B: automatic deployments with GitHub Actions

1. Create the repository as above, then in a terminal inside this folder run:

   ```
   git init -b main
   git add .
   git commit -m "Launch GE Peak Performance site"
   git remote add origin https://github.com/YOUR-USERNAME/gepeakperformance.git
   git push -u origin main
   ```

2. Go to **Settings > Pages** and set **Source** to **GitHub Actions**.
3. The workflow in `.github/workflows/pages.yml` runs on every push to `main`. Watch it under the **Actions** tab. It checks that every image exists, then publishes.

Pick one route. If you use Route A, you can delete the `.github` folder.

## Custom domain

1. In **Settings > Pages > Custom domain**, enter your domain and **Save**. Do this before changing DNS.
2. At your domain provider add:
   - For an apex domain (example.com), four `A` records: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`.
   - For `www`, a `CNAME` record pointing to `YOUR-USERNAME.github.io`.
3. When GitHub finishes checking the DNS, tick **Enforce HTTPS**.

## Do these once the site is live

- Add `<link rel="canonical" href="https://YOUR-DOMAIN/">` inside `<head>` in `index.html`.
- Add an `og:image` meta tag with the full address of a share image, e.g. `<meta property="og:image" content="https://YOUR-DOMAIN/img/HERO.jpg">`.
- Create `sitemap.xml` and add a `Sitemap:` line to `robots.txt` (and add the file to the `cp` line in the workflow if you use Route B).
- Add your delivery, returns and terms information before taking real orders. Orders currently go through WhatsApp, and card payment is not connected.
- Submit the site in Google Search Console.

## Editing

- Products, prices and colours are in the `P` list near the bottom of `index.html`. Sizes are in the `S` list.
- WhatsApp number: search for `447407808343`.
- Replace photos by keeping the same file names inside `img/`.
