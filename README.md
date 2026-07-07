# Press & Thread — Custom T-Shirt Design Landing Page

A single-file, dependency-free landing page for promoting a custom t-shirt / merch design service on Fiverr. Dark, print-ink themed design with scroll reveals, animated counters, an accordion FAQ, and a mobile-responsive layout.

## Files

- `index.html` — the entire site (HTML + CSS + JS, no build step, no external JS libraries)
- `README.md` — this file

## 1. Set your Fiverr link (do this first)

Open `index.html`, find this near the bottom of the file (inside the `<script>` tag):

```js
const FIVERR_URL = "https://www.fiverr.com/YOUR_USERNAME/YOUR_GIG_SLUG";
```

Replace it with your real gig URL. Every "Order on Fiverr" button, the nav "View Gig" link, and the footer Fiverr icon all pull from this one constant automatically — you only need to change it in this one place.

## 2. Customize content (optional)

Everything is plain HTML, so you can edit directly:

- **Copy**: headline, subheadline, service/testimonial text — just edit the text inside the relevant `<section>` in `index.html`.
- **Colors**: all colors are CSS custom properties at the top of the `<style>` block, under `:root`. Change `--magenta`, `--cyan`, `--yellow`, `--violet` to re-theme the whole site.
- **Stats**: in the "Social Proof" section, update the `data-count` attributes on each `.stat-num` element.
- **Portfolio tiles**: currently gradient placeholders — swap the `background:` value on each `.art` div for a `background-image: url('your-image.jpg')` once you have real design images to show.
- **Meta tags**: update `<title>`, the `og:` and `twitter:` tags, and `og:image` / `twitter:image` near the top of `<head>` with your own URL and preview image.
- **Favicon**: a placeholder inline SVG favicon is included. Replace the `<link rel="icon">` tag with your own `favicon.svg` or `favicon.ico` file if you have a logo.

## 3. Deploy to GitHub

1. Create a new repository on GitHub (e.g. `tshirt-design-landing`).
2. Upload `index.html` and `README.md` to the repository (drag-and-drop via the GitHub web UI works fine, or use git):
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

## 4. Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in (GitHub login works well).
2. Click **Add New → Project**.
3. Select the GitHub repository you just created.
4. Leave all settings at their defaults — this is a static `index.html` file, so **no build command, no output directory, and no environment variables are needed**.
5. Click **Deploy**. Vercel will give you a live URL (e.g. `your-project.vercel.app`) within a minute.

Optional: add a custom domain under **Project → Settings → Domains** once deployed.

## Notes

- No external JavaScript libraries are used — only Google Fonts are loaded from a CDN.
- The page respects `prefers-reduced-motion` and includes visible keyboard focus states for accessibility.
- Fully responsive from mobile up through desktop, with a collapsible mobile nav menu.
