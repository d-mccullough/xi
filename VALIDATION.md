# Validation

- Installed dependencies with Node 22 and generated a package lock.
- Passed Tina local indexing, GraphQL content fetching, production-style admin compilation, and Vite production build (`npm run build:local`).
- Opened the local admin in Chromium, entered local edit mode, and verified all section groups appeared.
- Changed a headline, verified the live website iframe updated, clicked Save, and verified the content JSON changed on disk. Restored the original content.
- Browser-tested the built public site: sport category filtering, theme persistence, inquiry prefill, privacy dialog, mobile navigation/Escape, no horizontal overflow at 320/390/768/1440px, no uncaught JavaScript errors.

Not verified: Tina Cloud authentication, GitHub commits, Vercel deployment, or external stock image availability. Those require connected accounts or external access. No cloud credentials are included.

Latest content update: phone removed, business email replaced, MMA added, and editable ticker message added. Tina/Vite build passed. Browser checks covered MMA filtering and inquiry prefill, new mailto draft recipient, ticker text, absence of phone links, and mobile width in both the built site and standalone preview.
