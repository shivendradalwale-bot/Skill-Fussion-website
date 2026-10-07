# SkillFusion — Academy | Digital

Marketing website for SkillFusion, covering its two divisions:
- **SkillFusion Academy** — programming education (C, C++, Java, Python, Linux, with AI/ML and Full Stack Development on the roadmap)
- **SkillFusion Digital** — website development and digital services for businesses

## Tech stack

Single self-contained static HTML file — no build step, no framework, no dependencies to install.

- Plain HTML/CSS/JS
- [Three.js](https://threejs.org/) r128 + [GSAP](https://gsap.com/) 3.12.2 / ScrollTrigger, loaded via CDN (cdnjs), for the hero/section 3D layer and scroll-tied animation
- Google Fonts (Fraunces, Manrope)

## File structure

```
.
├── index.html      # the entire site (markup, CSS, and JS all in one file)
├── robots.txt      # crawler access + sitemap pointer
├── sitemap.xml     # single-page sitemap (site has one real URL today)
└── vercel.json     # security headers + Content-Security-Policy for deployment
```

## Before going live — TODOs

These are flagged inline in the code too (search for `TODO` in `index.html`):

- [ ] Replace every `https://your-domain.com/` placeholder (appears in `index.html`'s canonical/OG/Twitter/JSON-LD tags, plus once each in `robots.txt` and `sitemap.xml`) with the real production domain — it's the same exact string everywhere, so one find-and-replace across all three files covers it.
- [ ] Replace the generated placeholder favicon with a real exported icon set (favicon.ico, 16/32px PNGs, apple-touch-icon) from the actual logo artwork.
- [ ] Create a real Open Graph image (1200×630) — the meta tag currently points to `/og-image.jpg`, which doesn't exist yet.
- [ ] Wire the enquiry form up to a real backend (Formspree, Netlify Forms, EmailJS, etc.). It currently falls back to opening a pre-filled `mailto:`, which works but depends on the visitor having a configured email client.
- [ ] Generate real Subresource Integrity (SRI) hashes for the three CDN scripts if desired (e.g. via `openssl dgst -sha384 -binary file.js | openssl base64 -A`, or srihash.org).

## Deployment (Vercel)

1. Push this repo to GitHub (or connect it directly).
2. In [Vercel](https://vercel.com), "Add New Project" → import this repo → deploy (no build settings needed, it's a static file).
3. `vercel.json` is picked up automatically and applies the security headers/CSP.
4. Add your custom domain under Project Settings → Domains, point your registrar's DNS as instructed, and Vercel auto-provisions HTTPS.
5. Submit `sitemap.xml` to Google Search Console once the domain is live.

## Contact

- SkillFusion Digital: 6361435651
- SkillFusion Academy: 9860706062
- info@skillfusionacademy.com / skillfusioncoaching@gmail.com
