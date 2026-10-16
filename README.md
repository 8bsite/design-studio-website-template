# Free HTML design studio website template with GSAP scroll animations — Onda

**One-page website for a design, brand or digital agency: a free HTML template in one file, with GSAP scroll animations, no build step, MIT license. Made by [8B](https://8b.com/), the AI website builder.**

[![License: MIT](https://img.shields.io/badge/license-MIT-blue)](LICENSE) ![one HTML file: no build](https://img.shields.io/badge/one%20HTML%20file-no%20build-orange) ![GSAP: ScrollTrigger](https://img.shields.io/badge/GSAP-ScrollTrigger-88ce02)

**[Live demo](https://8bsite.github.io/design-studio-website-template/)** · **[Use this template](https://github.com/new?template_name=design-studio-website-template&template_owner=8bsite)** · **[Download ZIP](https://github.com/8bsite/design-studio-website-template/archive/refs/heads/main.zip)**

<a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/desktop.png" alt="Onda, a free HTML template: first screen on a desktop" width="76.1%"></a> <a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/phone.png" alt="Onda, a free HTML template: first screen on a phone" width="21.9%"></a>

<p align="center"><a href="https://8bsite.github.io/design-studio-website-template/"><img src="previews/scroll.gif" alt="Onda, a free HTML template: scrolling through the first sections on a desktop" width="40%"></a><br><sub>Scroll animation</sub></p>

A one-page site for an invented brand, product and AI studio with offices in two cities: work, long-term clients, services, process, team, news and contact. Black, white and one violet; every heading ends in a violet dot, and the giant full stop after "Hello" is a round photo that travels into the next heading, while the case studies slide on a track that bends into a rotating wheel.

Good for: design, brand or digital agency; product or UX studio; creative or marketing agency with case studies; consultancy that shows clients, services and process on one page.

## Use it with an AI coding agent

Download the files into your project (in Windows PowerShell type `curl.exe`):

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

Give the agent the downloaded file, not a link: from a link it would rebuild a different page. No agent? Click **[Use this template](https://github.com/new?template_name=design-studio-website-template&template_owner=8bsite)**, edit `index.html` and turn on **Settings → Pages**.

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

## Design

Palette: ![#0d0c11](https://img.shields.io/badge/-%230d0c11-0d0c11?style=flat-square) ![#ffffff](https://img.shields.io/badge/-%23ffffff-ffffff?style=flat-square) ![#6c3cff](https://img.shields.io/badge/-%236c3cff-6c3cff?style=flat-square) ![#efeef4](https://img.shields.io/badge/-%23efeef4-efeef4?style=flat-square) ![#aaa7b4](https://img.shields.io/badge/-%23aaa7b4-aaa7b4?style=flat-square) ![#5d5a67](https://img.shields.io/badge/-%235d5a67-5d5a67?style=flat-square) ![#1f1d26](https://img.shields.io/badge/-%231f1d26-1f1d26?style=flat-square)  
Fonts: Gabarito, Onest (Google Fonts). Change both through the CSS variables in the `:root` block at the top of `<head>`. A big display line with `style="--len:N"` fills its width: set N to its new number of characters.

- Every heading ends in a violet dot (`<span class="m-dot">`), not a typed full stop: keep the span when you change a heading.
- "Hello" in the hero and "Bye" in the footer are sized by `style="--len:N"` (number of characters) and are meant for one short word.

## Before you publish

- Replace everything marked `data-8b-placeholder` (social preview image, favicon, email, phone, form, social) and the invented demo facts: prices, dates, address. [AGENTS.md](AGENTS.md) lists them.
- The form sends nothing yet: connect it to Formspree or Netlify Forms, or remove it.

## Tech

GSAP 3.13.0, ScrollTrigger, Lenis 1.3.4 from jsDelivr, 135 KB, no build step. Chrome and Edge 111+, Safari 16.2+, Firefox 113+ (it uses color-mix(), cascade layers, small/dynamic viewport units). With "reduce motion" on, the page is complete and still.

## License

MIT, see [LICENSE](LICENSE); the "Design: 8B" footer link is welcome, not required. Photos, fonts and libraries keep their own licences: [CREDITS.md](CREDITS.md). More free templates: [github.com/8bsite](https://github.com/8bsite).
