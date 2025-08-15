# Deploying this static build to Vercel

This folder is a static production build (HTML/CSS/JS). The entry page is **bot.html**.

## Option A: Drag-and-drop (no CLI)

1. Go to https://vercel.com/new (Log in or create account).
2. Click **"Import Project"** → **"Drop a folder here"**.
3. Upload the **contents of this folder** (`www.synthetictraders.com/www.synthetictraders.com`), not the parent directory.
4. In "Framework Preset", choose **Other**.
5. In "Root Directory", keep it as the project root you uploaded.
6. No build command is required (it's already built).
7. Click **Deploy**.

The included `vercel.json` rewrites `/` to `/bot.html`, so your homepage works without typing the file name.

## Option B: Vercel CLI

1. Install the CLI:
   ```bash
   npm i -g vercel
   vercel login
   ```
2. From this folder:
   ```bash
   vercel --prod
   ```

That immediately uploads and deploys this folder as a static site.

## Notes
- Entry page is `/bot.html`. The rewrite in `vercel.json` makes `/` → `/bot.html` automatically.
- The **service worker** is at `/service-worker.js`. A header rule is included so it updates properly on new deploys.
- If you plan to use a **custom domain**, add it under your Vercel project's **Settings → Domains**.
- If some assets fail to load, ensure the project root is exactly this directory so relative paths like `/css/...` and `/js/...` resolve correctly.
