# FIRST X&XI — Beyond the Game

A responsive sports agency website in plain HTML, CSS, and JavaScript. No framework, dependency installation, or build step. Content is based on the supplied FIRST X&XI LLC brief. The visual direction takes inspiration from the.team without copying its content or code.

## Preview

Open `index.html` directly, or run `python -m http.server 8000` from this folder and visit http://localhost:8000.

## GitHub → Vercel

1. Create a GitHub repository and upload the contents of this folder. Keep `index.html` at the repository root, alongside `styles.css`, `script.js`, `vercel.json`, and `assets/`.
2. In Vercel, choose **Add New → Project** and import the GitHub repository.
3. Select **Other** as the framework preset. Leave the build command empty and use the repository root (`.`) as the output directory. No install command or environment variables are required.
4. Deploy. Optionally add `firstxandxi.com` in the Vercel project's Domains settings and follow its DNS instructions.

The site has not been pushed to GitHub or deployed to Vercel by this delivery.

## Included

- Black, white, and red art direction with bundled typography
- Responsive desktop navigation, dropdown, keyboard-accessible mobile menu
- Theme switching with optional browser-local preference storage
- Scroll reveals, continuous brand ticker, hover states, reduced-motion support
- Eight service divisions in native accessible disclosure elements
- Eight sports divisions with functioning category filters
- Athlete, partnership, team/career, insights, and contact sections
- Context-aware inquiry links that prefill topic and sport
- Validated email-draft form with copy-text fallback
- Privacy dialog, favicon, descriptive metadata, semantic landmarks, focus styles

## Important content and functionality notes

The contact form prepares a `mailto:` draft. It does not send messages automatically, save submissions, or run a database. Visitors must send the draft from their email application. Direct email and phone links are included. A production submission API can be connected later if desired; never place private API keys in browser JavaScript.

Athlete profiles, team biographies, signed partner logos, and news articles were not supplied. Their sections explain forthcoming content rather than showing fictional people, clients, testimonials, or achievements. The site is a complete single-page presentation, not an athlete database or authenticated portal.

The header uses an editable typographic interpretation of the supplied logo. The original embedded logo images were not available as downloadable workspace files. For exact brand fidelity, replace the `.logo` markup with an image of the original transparent logo. The full-width footer wordmark is text.

## Photography and fonts

Stock sports photography is referenced from `images.unsplash.com` in `styles.css`. These are illustrative sports images, not represented athletes. Remote imagery requires Internet access. Image downloads were blocked in the development environment, so photography could not be visually verified there. For a fully self-contained release, obtain suitable licensed images, save optimized files in `assets/`, and change the five image URLs in the CSS. No images from the.team were copied.

Font files for Barlow Condensed and DM Sans are bundled in `assets/`, with their SIL Open Font License files. All text remains usable with system fallbacks.

## Editing

- Content and sections: `index.html`
- Colors, spacing, responsive layouts: `styles.css` (`:root` variables)
- Filters, navigation, theme, inquiry behavior: `script.js`
- Inquiry destination: update the email and phone in HTML and the email address in JS together.
- External photos: search `styles.css` for `images.unsplash.com`.
- Privacy: review the included notice when adding analytics, forms, or integrations.

## Validation

JavaScript syntax was checked with Node. Headless Chromium checked layouts at 320, 390, 768, and 1440px, sport filter counts, saved theme preference, sport inquiry prefilling, privacy dialog open/close, mobile navigation and Escape handling. No horizontal overflow or uncaught JavaScript errors in these checks. The browser's access to external stock photography was unavailable. Deployment and real email delivery were not tested.
