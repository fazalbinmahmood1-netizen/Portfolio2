# Areeba Fatima — Portfolio2

A complete, portable personal portfolio with pre-rendered HTML, CSS and vanilla JavaScript. No application accounts, proprietary runtime, paid API or database is required. The source can be deployed to any static host. The temporary review host is separate from the future custom domain.

## Run

Node.js 20+ is sufficient. There are no npm dependencies.

```sh
npm run build
npm test
# Serve dist/ with your preferred local static server.
```

## Contents

19 pages including home, about, three interest detail pages, marketing, writing, notebook, six complete original essays, contact, printable profile, privacy and 404.

- `content/site.json`: profile, degree, expected graduation, email, social links, image slots, licensed-font paths and launch settings.
- `content/articles.json`: editable articles, categories, introductions and sections.
- `scripts/build.mjs`: HTML generation, shared navigation/footer, metadata and sitemap.
- `public/styles.css`: reference palette, typography scale, responsive layouts and reduced-motion styles.
- `public/app.js`: scroll-driven ribbon and horizontal sequence, menu, native dialog, filtering, carousel and enquiry draft handling.
- `scripts/check.mjs`: page structure, link/asset targets, schema and launch checks.
- `dist/`: deployable output.

## Reference and typography

The reference was inspected at https://www.ericaboothby.com/ on 14 November 2026. Observed colours: #DFE4DF, #D8DFD8, #CBD4CB, #4F0A19, #5C3C43 and #103210. The implementation uses independently written layout and animation code and original content. It does not copy the reference person's biography, photographs, research or endorsements.

Observed reference fonts: Agatho Regular (large name), Spline Sans (headings), BT Beau (navigation), Helvetica light/medium (body), Bricolage Grotesk (footer). Spline Sans is self-hosted under the included SIL OFL licence. Proprietary/reference font files are not copied from the original site. Current serif/body/navigation/footer fallbacks mean this version is **not an exact font/pixel clone**.

To install properly licensed matching webfonts, put files in `public/fonts/` and set the matching `/fonts/file.woff2` paths in `content/site.json` under `fonts.agatho`, `fonts.btBeau`, `fonts.helvetica`. These are picked up automatically during build. Footer font can be set in CSS after adding a licensed/local font face. Do not upload restricted font binaries to a public repository if their licence prohibits redistribution.

## Motion

The desktop education journey pins for 310vh. Scroll progress draws the left burgundy line, the central loop and the right line, and brings labels into view in sequence. It reverses naturally when scrolling upward. Mobile uses a vertical ribbon and shorter sequence. Desktop interests translate horizontally during vertical scrolling; mobile uses native horizontal swipe/scroll snap. No third-party animation library or scroll hijacking is needed. Reduced motion shows the complete ribbon without the pinned sequence and preserves ordinary navigation.

## Content accuracy

Only supplied personal facts are used: Areeba Fatima, B.Sc. Psychology in progress at University of Manitoba, expected graduation 2027, marketing experience with 20+ companies in the US and Canada, and interest in pursuing I/O Psychology. No degree is represented as completed; no clinical qualification, fabricated client, testimonial, employer, research publication or result is added. Review the new first-person copy with Areeba before public launch.

## Images

Every photograph is currently a blank, accessible placeholder. Supply local image paths under `images` in site.json after adding files to public/. The original site's portraits and pictures are not reused.

## Contact

No email address was supplied. The form validates entries and downloads a clearly labelled enquiry draft locally. It does not claim to send or store messages. Adding `email` to site.json switches it to an honest mailto workflow, where the visitor reviews and sends in their own email application. A direct delivery backend is not implemented. LinkedIn is omitted until the correct personal URL is supplied.

## Domain and launch

`areebafatima.com` is reserved in configuration only; DNS has not been changed. `launchReady: false` sets noindex metadata and a robots disallow rule for the review build. Before public launch: add photographs, authorised fonts and verified contact/social details; review personal copy; connect the domain with the chosen host; set launchReady true; rebuild and publish. Canonical URLs and sitemap then switch to the custom domain. Do not set launchReady true until that domain actually serves the site.

The `.openai/hosting.json` file identifies the private review deployment only. It is not required for other static hosts. No GitHub/source link is displayed in the public-facing footer.
