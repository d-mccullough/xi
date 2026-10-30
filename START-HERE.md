# Your website + visual admin editor

The website keeps its existing design. TinaCMS adds a private editing interface at `/admin/index.html`. You can edit existing headings, paragraphs, service descriptions, sports copy, business email, and photos. You can also upload your original logo. The page layout, animation code, and styling are protected from everyday content edits.

## 1. Upload the project to GitHub

Extract the ZIP first. Upload the contents of `first-x-and-xi-admin` to the root of your website repository, replacing the earlier version. `package.json`, `index.html`, `tina/`, `content/`, and `public/` should all be at the repository root. This version has a build step; do not use the old static-site deployment settings.

## 2. Connect Tina

1. Create an account at https://app.tina.io/ and create a project.
2. Connect the GitHub repository containing this project. Allow Tina access to that repository.
3. Select the branch you publish, usually `main`.
4. Copy the project's **Client ID** and a **read-only content token** from its settings.
5. Invite any additional editors through Tina's project user management. Each editor signs in with their own authorized account. Do not share GitHub or Vercel passwords.

Tina's current setup reference: https://tina.io/docs/tina-cloud/overview

## 3. Set up Vercel

Import that repository into Vercel, or update the existing project:

- Framework preset: **Vite**
- Install command: `npm ci`
- Build command: `npm run build`
- Output directory: `dist`
- Node.js: **22.x**

Add these environment variables in Vercel → Project Settings → Environment Variables:

| Name | Value |
| --- | --- |
| `TINA_CLIENT_ID` | Client ID from your Tina project |
| `TINA_TOKEN` | Read-only content token from Tina |
| `TINA_BRANCH` | Your GitHub publishing branch, usually `main` |

Add them to Production. For preview deployments, configure them for the branch you intend to edit. A preview connected to `main` edits `main`, so don't use production-connected previews as a draft sandbox.

Redeploy after adding variables. In Tina's project configuration, set the deployed site URL and any permitted origins to your Vercel URL (and your custom domain if used). Make sure Tina has indexed the selected GitHub branch.

The credentials are used by the build to read content. Do not paste a GitHub token or Tina write token into HTML, browser JavaScript, or a public repository. `.env.example` contains placeholders only.

## 4. Edit your site

1. Visit `https://YOUR-SITE.vercel.app/admin/index.html`.
2. Sign in through Tina.
3. Open **Website content → home**.
4. The site appears beside the editing panel. Click editable text or use the section groups in the panel.
5. Change the text or choose/upload an image. The preview updates before saving.
6. Click **Save**. Tina writes the content change to GitHub; Vercel builds and publishes it. Wait for the successful Vercel deployment before checking the public site.

Use the **Contact details & logo** group to change the business email, Instagram account, or original logo. All inquiry drafts use that email address. Use HTTPS image URLs or upload images through Tina. To undo a published edit, restore the earlier content in Tina or revert the content commit in GitHub.

## Preview without setup

Open `OPEN-PREVIEW.html` directly in your browser. It bundles the styling, fonts, and interactions into one file, so it cannot lose its CSS when opened separately. This is a snapshot for viewing, not the admin editor. Stock photography still needs Internet access.

## What this does not add

This is a content editor for the existing site, not a new athlete database or arbitrary page builder. Existing athlete/team/insights section text is editable; adding new profile-card layouts requires development. Inquiry forms still prepare email drafts rather than collecting or sending submissions on a server.

Your site is not deployed and no Tina/GitHub accounts have been linked by this package. Hosted authentication, GitHub commits, and Vercel deployments can only be tested after you connect the accounts. Tina service limits and pricing depend on your selected plan.

## Developer commands

`npm ci` installs the locked dependencies. `npm run dev` starts Tina locally plus Vite; local mode edits files on disk without cloud sign-in and should only run on a trusted development computer. `npm run build:local` validates a complete local build. `npm run build` performs the real cloud-backed deployment build. `npm run preview` serves the built site.

`content/pages/home.json` stores editable content. `template.html` holds the protected page structure. `tina/config.ts` and `tina/fields.json` define editor fields. `scripts/render.ts` fetches Tina data and pre-renders text for search engines; the small React bridge enables live visual editing. `styles.css` and `script.js` retain the original design and behavior.
