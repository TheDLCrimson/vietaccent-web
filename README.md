# VietAccent — Landing Page

Marketing site for [VietAccent](https://github.com/Thanh-WuTan/vietaccent), a Flutter Vietnamese-learning mobile app with AI-powered pronunciation scoring.

**Stack:** Astro 6.x · Tailwind CSS v4 · MDX · Vercel

## Development

```bash
npm install
npm run dev        # http://localhost:4321
```

## Production build

```bash
npm run build
npm run preview    # preview the production build locally
```

## Deploy

Auto-deploys to Vercel on push to `main`. PR preview deploys are enabled.

The `/apk` route is a Vercel redirect to the latest GitHub Release APK asset — update `vercel.json` when a new release is cut.

## Project structure

```
src/
  layouts/BaseLayout.astro    # SEO meta, OG tags, JSON-LD
  components/                 # One component per landing section
  pages/
    index.astro               # Single-page landing
    download.astro            # /download
    privacy.mdx               # /privacy
    terms.mdx                 # /terms
    changelog.mdx             # /changelog
public/
  robots.txt
  og-image.png                # 1200×630 OG share card
vercel.json                   # /apk redirect
```

## Before going live

- [ ] Replace placeholder screenshots in `src/assets/images/` with real device-framed WebP exports
- [ ] Update the YouTube video ID in `src/components/VideoEmbed.astro`
- [ ] Set `site` in `astro.config.mjs` to the final custom domain once assigned
- [ ] Update `SHA-256`, `version`, and `releaseDate` props on `DownloadSection` after each release
