# Open questions

These replace the previous entries in this file, which were about Okiki Ojo's original
content and no longer apply now that the site has been rebranded to Biniam Hailu.

## Assets still needed

0. **Deal Hunter / Tatari AI project links**: `src/pages/index.astro`'s Featured Projects
   list includes "Deal Hunter" (autonomous multi-agent bargain finder) and "Tatari AI" (AI
   academic advisor) alongside RentLink and Safe Bites. Neither has a confirmed public repo
   or live URL yet — no matching repo was found on `github.com/bghailu` — so both cards
   currently link to the GitHub profile (`https://github.com/bghailu`) as a placeholder.
   Tatari AI now has its real screenshot (`cloudinary/tatari`); Deal Hunter still uses the
   blank placeholder image (`image: { blank: true }`) until a screenshot is uploaded to
   Cloudinary. Once real repo/live links exist, update `link` for both entries.

1. **Cloudinary uploads**: The project cards (`src/pages/index.astro`) and hero photo
   (`src/components/HeroBanner.astro`) reference Cloudinary public IDs `rentlink`,
   `safebites`, and `profile`. The source images for the first two are staged at
   `src/assets/cloudinary-uploads/` (copied from the old my-portfolio repo) — upload them to
   your Cloudinary account under those exact public IDs. There is no headshot yet for
   `profile`; upload one whenever you have it (or change the `src` in HeroBanner.astro to
   whatever public ID you use).
2. **Cloudinary cloud name**: `.env.local` currently has a placeholder
   `PUBLIC_CLOUDINARY_CLOUD_NAME=your-cloud-name`. Replace it with your real Cloudinary cloud
   name once you've created an account. `Image.astro` and `HeroBanner.astro` both read this
   env var for their own srcset URL-building, so it's the only place that needs to change in
   code. `vercel.json`'s `/images/*` rewrite also hardcodes `your-cloud-name` as a placeholder
   (static JSON can't read env vars) — update that too if you keep that rewrite.
3. **OG banner image**: `HeadMetadata.astro` currently falls back to
   `/favicon/android-chrome-512x512.png` (a 512×512 square icon) as the social-share image
   because there's no proper banner in my-portfolio. A dedicated 1200×630 image would look
   better when the site is shared on social platforms.

## Licensing

4. **AGPL-3.0 license**: The repo ships with Okiki's original AGPL-3.0-only `LICENSE` file and
   `package.json` license field, left unchanged during the rebrand since that's your call, not
   something to silently swap. Decide whether you want to keep AGPL, switch to something more
   typical for a personal portfolio (e.g. MIT, or no license at all for a private site), or
   remove the license entirely.

## Stale historical files

5. `.agents/baseline.md`, `content-review.md`, `architecture-review.md`, `dependency-audit.md`,
   `ecosystem-research.md`, `implementation-plan.md`, `pr-notes.md`, `validation-report.md`,
   and `.github/prompts/modernize-homepage.prompt.md` are dated audit/review artifacts from a
   past agent session about Okiki's original content (e.g. they reference his Astro maintainer
   status, bundlejs.com, etc.). They weren't touched during this rebrand since they're
   historical reports, not live instructions — but they're now inaccurate for this site and
   worth deleting if they're just clutter.
