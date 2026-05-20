# Trigu Italia — Static Site

Static HTML/CSS/JS version of triguitalia.com, ready to develop and deploy freely.

## Structure

```
triguitalia-static/
├── index.html          # Homepage
├── about.html          # About page
├── tours.html          # Artisan Tours 2026
├── catalog.html        # Product catalog
├── newsletter.html     # Newsletter signup
├── shop.html           # Shop (placeholder)
├── css/
│   └── style.css       # All styles
├── js/
│   └── main.js         # Mobile nav + interactions
└── images/             # Add local images here
```

## Getting started locally

Just open `index.html` in a browser — no build step needed.

For a proper local dev server (fixes font loading etc.):

```bash
# Python
python3 -m http.server 8080

# Node (if you have npx)
npx serve .

# VS Code: install "Live Server" extension, right-click index.html → Open with Live Server
```

Then visit `http://localhost:8080`

## Pushing to GitHub

```bash
cd triguitalia-static
git init
git add .
git commit -m "Initial static site"

# Create a new repo on github.com/new, then:
git remote add origin https://github.com/YOUR_USERNAME/triguitalia.git
git push -u origin main
```

## Deploying (free options)

### GitHub Pages (simplest — free)
1. Push to GitHub
2. Go to repo Settings → Pages
3. Source: Deploy from branch → `main` / `/ (root)`
4. Your site will be live at `https://YOUR_USERNAME.github.io/triguitalia`
5. Add a custom domain (triguitalia.com) in the Pages settings

### Netlify (recommended — drag and drop)
1. Go to netlify.com → "Add new site" → "Deploy manually"
2. Drag the entire `triguitalia-static` folder onto the page
3. Done — live in ~30 seconds
4. Add custom domain in site settings

### Vercel
```bash
npm i -g vercel
vercel
```

## Connecting your domain (triguitalia.com)

Once deployed, point your domain's DNS to the new host:
- **GitHub Pages**: Add a CNAME record pointing to `YOUR_USERNAME.github.io`
- **Netlify**: Follow their custom domain wizard (handles SSL automatically)
- **Vercel**: Same — automatic SSL

## Images

The site currently hotlinks images from the existing triguitalia.com WordPress install.
To make it fully independent:
1. Download images from triguitalia.com/wp-content/uploads/
2. Put them in the `images/` folder
3. Update the `background-image` URLs in `css/style.css` and `index.html`

Key images to download:
- `img-cheese-home-02.jpg` (hero + tours background)
- Any product images from the catalog

## What's different from the WordPress site

- No WooCommerce shop (shop.html has a placeholder + contact link)
- Newsletter form is a frontend-only placeholder (wire up to Mailchimp, ConvertKit, etc.)
- No cookie consent banner (add one if needed for GDPR)
- All content is editable directly in HTML — no CMS login required

## Notes

- Fonts load from Google Fonts (Playfair Display + Lato)
- No JavaScript framework — plain HTML/CSS/JS only
- Mobile responsive with hamburger nav
- Banner + nav pills link to thecentenerian.com and golfinsardinia.com
