# Free HTML design studio website template with GSAP scroll animations — Onda

**One-page website for a design, brand or digital agency: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/design-studio-website-template/)** · **[Use this template](https://github.com/new?template_name=design-studio-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/design-studio-website-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/desktop.png" alt="Onda, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/phone.png" alt="Onda, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/scroll.gif" alt="Onda, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for an invented brand, product and AI studio with offices in two cities: work, long-term clients, services, process, team, news and contact. Black, white and one violet; every heading ends in a violet dot, and the giant full stop after "Hello" is a round photo that travels into the next heading, while the case studies slide on a track that bends into a rotating wheel.

Good for: design, brand or digital agency; product or UX studio; creative or marketing agency with case studies; consultancy that shows clients, services and process on one page. Free for personal and commercial use (MIT), made by [8B](https://8b.com/).

## Quick start

Pick one:

- **With an AI coding agent** (Claude Code, Codex, Cursor, Windsurf…). Download the files into your project (in Windows PowerShell type `curl.exe`):
  ```bash
  curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/index.html
  curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/AGENTS.md
  curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/LICENSE
  curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/CREDITS.md
  ```
  Then give your agent this prompt:
  ```text
  Read AGENTS.md, then edit index.html. Use this template as the base for a studio or agency site for <your business: what you make, for whom, where you are, your clients and services, how to get in touch>. Keep the layout, the motion and the single-file format; replace the brand name, copy, photos, client names, results, dates, addresses and contacts, and recolour it through the CSS variables if needed.
  ```
  Give the agent the downloaded file, not a link: an agent reads a link as a summary and would rebuild a different page.
- **No code.** Download the ZIP, unzip it, replace the contacts and texts in `index.html`, put `index.html` into an empty folder and drag that folder onto [Netlify Drop](https://app.netlify.com/drop). The page is online in a minute.
- **On GitHub.** Click **[Use this template](https://github.com/new?template_name=design-studio-website-template&template_owner=8bsite)** to get your own copy, then **Settings → Pages → Deploy from a branch → main**. Your site appears at `https://<you>.github.io/<repo>/`.

## What's on the page

- **Navigation** — fixed top bar: wordmark, section links, Start a project button; phone menu overlay
- **Hello** — first screen: a one-word greeting whose full stop is a giant round photo (demo: "Hello")
- **We make the things people come back to** — two-line statement of what the studio does, a lead paragraph and an index of links into the page
- **Selected work** — case studies: five large cards on a horizontal track (demo: five client launches)
- **Never a one-off** — long-term clients: six cards on a wheel that turns with scroll (demo: years of partnership)
- **What we do** — services: five cards that stack as you scroll, each with deliverable badges and a photo
- **How we work** — process: four steps beside a ring the scroll draws round (demo: Listen, Make, Measure, Again)
- **Inside the studio** — team and careers: photo collage that deals out from a pile, with open roles
- **Ideas and news** — news and articles: four stories beside a sticky photo frame
- **Fair questions** — questions and answers (native &lt;details&gt;)
- **Let's talk** — violet contact field: big "Let's talk", email, two offices with phones, and a form (placeholders)
- **Footer** — closing greeting "Bye" with the round photo full stop, link columns, newsletter, copyright and the Design: 8B credit

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, email, phone, form, social) and the invented demo facts — prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The contact form does not send anything yet: connect it to a form service (Formspree, Netlify Forms) or remove it; [AGENTS.md](AGENTS.md) shows both.

## Customize

- **Colours and fonts**: CSS variables in the `:root` block at the top of `<head>`.
- **Text**: edit it in place. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.
- **Photos**: replace `src`, delete `srcset` and `sizes` (they list Unsplash sizes) and update the `alt` texts.
- **Animations**: each section's animation is one `<script data-8b-part="scene:<id>">` block at the end of the file. For native scroll, delete the Lenis block in `page-init`.

## For developers

- **Stack.** HTML and CSS (custom properties, cascade layers) with GSAP 3.13.0, ScrollTrigger, Lenis 1.3.4 from jsDelivr. No build step, no framework, no npm. 135 KB.
- **Layout of the file.** `<head>`: CSS variables, shared classes, then one style block per section. Then the markup, one element per section with a one-line comment above it. End of `<body>`: small behaviour scripts, the libraries, smooth scroll (`page-init`), the effects, one animation script per section.
- **Browsers.** Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), cascade layers, small/dynamic viewport units).
- **Accessibility.** Motion runs only when the visitor's system allows it; with "reduce motion" the page is complete and still. FAQ answers use native `<details>` and open without JavaScript. Every photo has alt text.
- **External requests.** fonts.gstatic.com, images.unsplash.com, cdn.jsdelivr.net. No analytics, no cookies. To self-host everything (offline use, or Google Fonts and GDPR in the EU), download those files and change the URLs.
- **Licences of the parts.** GSAP is free, commercial use included, under its own standard licence (not MIT); Lenis is MIT; fonts are SIL OFL; photos are under the Unsplash License. See [CREDITS.md](CREDITS.md).

## FAQ

**Can I use it for a client or a commercial site?** Yes. The code is MIT: use it, change it, sell the site you build with it.

**Do I have to keep the "Design: 8B" link?** No. It is welcome, not required.

**Can I use it in React, Next.js, Astro or Vue?** Yes. Move each section's markup and style block into a component and run its animation script in `useGSAP()` (React) or `onMounted` (Vue); start Lenis once. Or keep it as a separate static landing page next to your app (`example.com` for the landing, `app.example.com` for the app).

**Why doesn't the contact form send?** It is a demo. Connect it to Formspree, Netlify Forms or your backend; AGENTS.md has the steps.

**Where are the photos from?** Unsplash; they load from Unsplash's servers. Replace them with your own when you can.

## More free templates

[More 8B templates on GitHub](https://github.com/8bsite) · [8b.com](https://8b.com/)

## License

The template code is MIT licensed — see [LICENSE](LICENSE). Photos, fonts and libraries keep their own licences — see [CREDITS.md](CREDITS.md).
