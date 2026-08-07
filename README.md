# Berggrens Elinstallationer AB

Single-page marketing site for Berggrens El, built with [Astro](https://astro.build) and deployed to Azure Static Web Apps.

## Structure

- `src/pages/index.astro` – the page, assembled from section components
- `src/components/` – Header, Hero, Services, About, Contact, Footer
- `src/content/services/*.md` – service cards (title, description, icon, order) — edit these to add/change services without touching code
- `src/styles/global.css` – shared design tokens (colors, type, buttons)
- `src/assets/` – logo files (full lockup + cropped monogram, both auto-generated with a transparent background from the source PNG)

## Commands

| Command           | Action                                   |
| :----------------- | :---------------------------------------- |
| `npm install`       | Install dependencies                      |
| `npm run dev`       | Start local dev server at `localhost:4321`|
| `npm run build`     | Build production site to `./dist/`        |
| `npm run preview`   | Preview the production build locally      |

## Contact form

The contact form posts to [Web3Forms](https://web3forms.com) — a free hosted endpoint that emails submissions directly, no backend required.

**Before going live**, replace the placeholder access key in `src/components/Contact.astro`:

```html
<input type="hidden" name="access_key" value="YOUR_WEB3FORMS_ACCESS_KEY" />
```

Get a free key at https://web3forms.com by entering the destination email address — no account needed.

## Deployment

Pushing to `main` triggers `.github/workflows/azure-static-web-apps-*.yml`, which builds the Astro site and deploys `dist/` to Azure Static Web Apps.
