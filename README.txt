AutoFuture — Decision Infrastructure
Landing Page v1 · Production Build
====================================

PROJECT STRUCTURE
-----------------
autofuture/
├── index.html          single-file site (HTML + CSS + JS inline)
├── vercel.json         Vercel config (clean URLs, asset caching, security headers)
├── .gitignore
└── assets/
    ├── narrative.mp4   14s cinematic — the scroll-driven hero spine
    ├── symbol.png      AutoFuture mark (header, loader, resolution, invitation)
    ├── mohsen.jpg      founder image (The Architect moment)
    ├── favicon.png     512×512 favicon
    └── og-image.jpg    1200×630 social preview card

LOCAL PREVIEW
-------------
A local server is REQUIRED (video scrubbing needs HTTP range requests; file:// will not scrub):

    cd autofuture
    python3 -m http.server 8000

Then open http://localhost:8000/


DEPLOY — GitHub + Vercel
------------------------
1. Create a new GitHub repo and push this folder's contents to the root:
       git init
       git add .
       git commit -m "AutoFuture landing v1"
       git branch -M main
       git remote add origin <your-repo-url>
       git push -u origin main

2. In Vercel: New Project → Import the GitHub repo.
   - Framework Preset: Other (it's a static site)
   - Build Command: (leave empty)
   - Output Directory: (leave empty / root)
   - Deploy.

3. Add the custom domain www.autofuture.ai in Vercel → Project → Settings → Domains.
   Set the apex autofuture.ai to redirect to www (or vice-versa per preference).

No build step. No dependencies. Static files only.


PRODUCTION NOTES
----------------
- Fonts load from Google Fonts (DM Sans, JetBrains Mono).
- All other assets are local under /assets.
- The site is one continuous scroll experience (~31 viewports).
- CTAs:
    Book an Executive Strategy Session → https://calendly.com/autofuture-ai/30min
    Request Private Beta Access        → https://rev-flow-command.base44.app
    LinkedIn (footer)                  → https://www.linkedin.com/in/mohsensajjadi-ai/
