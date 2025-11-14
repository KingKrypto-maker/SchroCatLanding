```markdown
SchroCatLanding.io — README (quickstart)

What this repo contains
- index.html — futuristic landing page (uses images/meme1..meme16)
- shortlink/index.html — /s redirect for your X bio
- optimize-and-zip.sh — image processing + packaging script
- .github/workflows/deploy.yml — GitHub Action to publish to gh-pages
- CNAME — SchroCatLanding.io
- IMAGES_MANIFEST.txt — expected images mapping

Quickstart (deploy flow)
1) Create the repository on GitHub (owner: KingKrypto-maker, repo: SchroCatLanding) OR use an existing repo.
   - Recommended repo name: SchroCatLanding
2) Copy all files in this bundle into the repo root.
3) Add your original images:
   - Place your source images into images/originals/ named:
     original-1.jpg ... original-16.jpg
4) Run the optimizer locally to create webp + jpg fallbacks and social preview:
   chmod +x optimize-and-zip.sh
   ./optimize-and-zip.sh
   -> produces images/meme*-*.webp and images/meme*-*.jpg
   -> produces images/social-preview-1200x630.webp and .jpg
   -> creates schrocat_site.zip
5) Commit & push all files (including generated images):
   git add .
   git commit -m "Initial SchroCat landing + optimized images"
   git push -u origin main
6) GitHub Action will run and deploy the repository to branch gh-pages
7) Configure your custom domain:
   - Add CNAME file (already included) with: SchroCatLanding.io
   - Add the following A records at your DNS provider for apex domain:
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
   - In GitHub repo → Settings → Pages, set custom domain to SchroCatLanding.io and enforce HTTPS once certificate issues complete.

Alternate: Deploy with Vercel (recommended for automatic TLS)
- Import this repo into Vercel and set SchroCatLanding.io as a custom domain there. Vercel will provide DNS instructions and auto-issue TLS.

Replace token address after launch
- Edit index.html: replace YOUR_TOKEN_ADDRESS in the Raydium link with your SPL token mint address.

Notes & safety
- I cannot push or run commands on your behalf from this environment. You must run the optimize script locally because I cannot process your original images here.
- If you want me to open a PR into your repo automatically, create the repository on GitHub and reply with the repository owner/repo and confirm I have permission to create a branch and open a PR; I will push the site files (NOT your images) into a branch and open a PR. You will still need to run the optimizer and commit images or upload optimized images for the final site.
```
