# AcrossMedia: static copy

A static copy of https://acrossmedia.vercel.app (18 pages, ~12 MB) with all HTML, Next.js JS/CSS chunks, fonts, images and icons.

## Run locally

```bash
python3 -m http.server 8080
```

Then open http://localhost:8080

## Deploy

This is plain static files, so any static host works (Vercel, Netlify, GitHub Pages). On Vercel, deploy this folder with the framework preset set to "Other" and no build command.

## Changes from the original

- Next.js image optimisation (`/_next/image?...`) was switched to load the original image files directly, because a static host has no image server.
- `?dpl=...` deployment cache-busters were removed from URLs.

## Known limitations

- **Contact form:** it posts to `/api/contact`, which runs on the original server and couldn't be copied. On this copy the form won't send. The email (hello@acrossmedia.in) and WhatsApp links still work.
- **Absolute URLs:** canonical links, social-share images and JSON-LD still point to `https://acrossmedia.vercel.app`. If you host the copy on a new domain, find and replace that URL.
- **Navigation:** clicking between pages does a full page load instead of Next's client-side transition. Pages look and behave the same.
