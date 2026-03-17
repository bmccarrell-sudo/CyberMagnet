# CyberMagnet — Complete Website Package
## cybermagnet.net

---

## FOLDER STRUCTURE

```
cybermagnet/
├── index.html                  # Homepage
├── services.html               # Services page
├── ai-receptionist.html        # AI Receptionist & Automation page
├── portfolio.html              # Portfolio / Case Studies
├── about.html                  # About / Founder Story
├── contact.html                # Contact / Funnel Entry
├── landing-seo-guide.html      # Landing Page: Free SEO Guide
├── landing-ai-demo.html        # Landing Page: AI Receptionist Demo
├── landing-workshop.html       # Landing Page: Free Workshop
├── css/
│   └── style.css               # Global stylesheet
├── js/
│   └── script.js               # Global JavaScript
├── images/                     # (Create this folder — see placeholder guide below)
└── README.md                   # This file
```

---

## STYLE GUIDE

### Colors

| Token          | Hex       | Usage                                    |
|----------------|-----------|------------------------------------------|
| Deep Blue      | `#0a2540` | Primary headers, hero backgrounds        |
| Navy           | `#1b3b6f` | Gradient partner, section backgrounds    |
| Electric Blue  | `#007bff` | Accent, links, CTAs, highlights          |
| Orange         | `#ff7a00` | Secondary accent, special CTAs           |
| Black          | `#000000` | Text, structural elements                |
| White          | `#ffffff` | Backgrounds, text on dark                |
| Soft Gray      | `#f5f7fa` | Alternate section backgrounds            |
| Mid Gray       | `#e2e8f0` | Borders, dividers                        |
| Text Gray      | `#64748b` | Body text                                |
| Text Dark      | `#1e293b` | Headings, strong text                    |

### Typography

- **Display / Headings:** Poppins (600, 700, 800)
- **Body / UI:** Inter (400, 500, 600, 700)
- **Scale:** Fluid clamp() sizing from mobile to desktop
- **Letter spacing:** Negative for headings (-0.02em to -0.03em)

### Spacing Scale

| Token    | Value   |
|----------|---------|
| `--sp-xs`  | 0.5rem  |
| `--sp-sm`  | 1rem    |
| `--sp-md`  | 1.5rem  |
| `--sp-lg`  | 3rem    |
| `--sp-xl`  | 5rem    |
| `--sp-2xl` | 8rem    |

### Border Radius

| Token         | Value  |
|---------------|--------|
| `--radius-sm`   | 6px    |
| `--radius-md`   | 12px   |
| `--radius-lg`   | 20px   |

### Components

- **Buttons:** `.btn`, `.btn-primary`, `.btn-orange`, `.btn-outline`, `.btn-outline-dark`, `.btn-sm`, `.btn-lg`
- **Cards:** `.card`, `.card-dark` (for dark backgrounds)
- **Badges:** `.badge`, `.badge-orange`
- **Forms:** `.form-group`, `.form-input`, `.form-textarea`, `.form-dark`
- **Animations:** `.animate-fade`, `.animate-fade-left`, `.animate-fade-right`, `.delay-1` through `.delay-4`

---

## PLACEHOLDER IMAGES — REPLACEMENT GUIDE

Create an `images/` folder and add the following images. Recommended sizes:

| Placeholder Location              | Suggested File         | Size          |
|-----------------------------------|------------------------|---------------|
| SEO Dashboard (services.html)     | `seo-dashboard.jpg`   | 600×400px     |
| Brand Identity (services.html)    | `brand-identity.jpg`  | 600×400px     |
| Web Design (services.html)        | `web-design.jpg`      | 600×400px     |
| Funnel Architecture (services.html)| `funnel-arch.jpg`    | 600×400px     |
| AI Workflow Diagram (ai-receptionist)| `ai-workflow.png`  | 900×320px     |
| Founder Photo (about.html)        | `founder.jpg`         | 500×500px     |
| Portfolio thumbnails (portfolio)   | `case-*.jpg` (×8)    | 700×440px     |

To replace a placeholder:
1. Find the element with text like "SEO Dashboard Visual"
2. Replace the entire `<div>` with: `<img src="images/your-file.jpg" alt="Description" style="border-radius:var(--radius-lg);width:100%;height:auto;">`

---

## SEO METADATA SUMMARY

| Page                    | Title                                                        |
|-------------------------|--------------------------------------------------------------|
| index.html              | CyberMagnet — Premium Digital Growth & Automation Agency     |
| services.html           | Services — CyberMagnet | SEO, Branding, Funnels & AI        |
| ai-receptionist.html    | AI Receptionist & Automation Systems — CyberMagnet           |
| portfolio.html          | Portfolio — CyberMagnet | Case Studies & Client Results      |
| about.html              | About — CyberMagnet | Our Story, Mission & Values           |
| contact.html            | Contact — CyberMagnet | Book a Strategy Call                |
| landing-seo-guide.html  | Free SEO Guide — The Local Business SEO Playbook             |
| landing-ai-demo.html    | AI Receptionist Demo — See It In Action                      |
| landing-workshop.html   | Free Workshop — Automate Your Business Growth                |

Each page includes: `<title>`, `<meta name="description">`, `<link rel="canonical">`, Open Graph tags (homepage).

---

## CLOUDFLARE PAGES DEPLOYMENT CHECKLIST

### Prerequisites
- A Cloudflare account (free tier works)
- A GitHub, GitLab, or direct upload ready

### Option A: Git Integration (Recommended)

1. **Push to Git** — Push the entire `cybermagnet/` folder to a GitHub or GitLab repository.

2. **Connect to Cloudflare Pages**
   - Log into Cloudflare Dashboard → Pages → Create a project
   - Connect your GitHub/GitLab account
   - Select the repository

3. **Configure Build Settings**
   - Framework preset: `None`
   - Build command: *(leave blank — this is a static site)*
   - Build output directory: `/` (or the root of your repo)

4. **Deploy** — Click "Save and Deploy." Cloudflare will build and deploy automatically.

5. **Custom Domain**
   - Go to your project → Custom domains → Add `cybermagnet.net`
   - Update your domain's DNS nameservers to Cloudflare (or add a CNAME record)
   - Cloudflare will auto-provision an SSL certificate

### Option B: Direct Upload

1. Go to Cloudflare Dashboard → Pages → Create a project → Direct Upload
2. Drag and drop all files from the `cybermagnet/` folder
3. Deploy and configure custom domain as above

### Post-Deployment Checks

- [ ] All pages load without 404 errors
- [ ] Navigation links work across all pages
- [ ] Mobile responsive on phone, tablet, desktop
- [ ] Forms submit (connect to your form handler — see below)
- [ ] Animations trigger on scroll
- [ ] SSL certificate is active (https://)
- [ ] Favicon added (create and add `<link rel="icon" href="/favicon.ico">`)
- [ ] Google Analytics or Plausible tracking added
- [ ] Google Search Console connected & sitemap submitted

### Form Integration

The forms currently use a client-side placeholder handler. To make them functional:

**Option 1: Cloudflare Workers (recommended)**
Create a Worker that receives form POST requests and forwards to email or CRM.

**Option 2: Third-Party Services**
- Formspree (formspree.io) — Add `action="https://formspree.io/f/YOUR_ID"` and `method="POST"` to each `<form>` tag
- Netlify Forms — If migrating to Netlify
- Make.com / Zapier — Webhook-based automation

**Option 3: GoHighLevel / CRM Integration**
Replace form `action` with your CRM's webhook URL for direct lead capture.

### Performance Optimization (Optional)

- Compress images with TinyPNG or Squoosh before uploading
- Add `loading="lazy"` to images below the fold
- Minify CSS and JS for production (use a tool like `cssnano` / `terser`)
- Add a `_headers` file for Cloudflare caching rules:
  ```
  /*
    Cache-Control: public, max-age=31536000
  /css/*
    Cache-Control: public, max-age=31536000
  /js/*
    Cache-Control: public, max-age=31536000
  ```

---

## NOTES

- All code is vanilla HTML, CSS, and JavaScript — no frameworks, no build step required.
- Google Fonts (Inter + Poppins) are loaded from Google's CDN.
- SVG icons are inline for zero external dependencies.
- The site is fully responsive across all screen sizes.
- Animations use IntersectionObserver for performance.
- Counter animations use requestAnimationFrame for smooth rendering.

---

Built by CyberMagnet. Engineered for growth.
