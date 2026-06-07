# VietAccent — Landing Page

Marketing site for **VietAccent**, a free Android app for learning Vietnamese pronunciation with AI-powered accent scoring. Built as a capstone project at VinUniversity, Hanoi.

**Live site:** https://vietaccent.vercel.app

**Stack:** Astro 6.x · Tailwind CSS v4 · MDX · Vercel

## APK Distribution

The latest release APK is hosted as a GitHub Release asset on this repo. The `/apk` route in `vercel.json` redirects to the latest download. When cutting a new release:

1. Upload the new `app-release.apk` to a GitHub Release on this repo
2. Update `sha256`, `version`, and `releaseDate` props in `src/pages/index.astro` and `src/pages/download.astro`

Get the SHA-256 hash with:
```bash
certutil -hashfile app-release.apk SHA256
```

## Development

```bash
npm install
npm run dev        # http://localhost:4321
npm run build
npm run preview    # preview production build locally
```

## Project structure

```
src/
  layouts/
    BaseLayout.astro        # HTML shell, SEO meta, OG tags, JSON-LD
    ContentLayout.astro     # MDX page wrapper (Nav + Footer + prose styles)
  components/               # One component per landing section (11 total)
  pages/
    index.astro             # Single-page landing
    download.astro          # /download
    privacy.mdx             # /privacy
    terms.mdx               # /terms
    changelog.mdx           # /changelog
public/
  assets/                   # App icon, screenshots, hero mockup
vercel.json                 # /apk redirect → GitHub Releases
LICENSE                     # Proprietary — all rights reserved
```

## Deploy

Auto-deploys to Vercel on push to `main`.

## Before going live

- [ ] Replace placeholder screenshots in `ScreenshotGallery.astro` with real WebP device frames
- [ ] Update the YouTube video ID in `src/components/VideoEmbed.astro`
- [ ] Re-export `hero-mockup.png` from shots.so with transparent background
- [ ] Replace `appicon.jpg` OG image with a proper 1200×630 landscape banner
- [ ] Set `site` in `astro.config.mjs` to the final custom domain once assigned
