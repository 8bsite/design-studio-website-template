# Onda — notes for AI coding agents

One HTML file: markup, inline CSS and inline scripts; GSAP with ScrollTrigger, Lenis smooth scroll, all from jsDelivr. No build step, no framework.

## Files
Work from the files: a page read through a link comes back as a summary, and a page rebuilt from it would differ.
```bash
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/CREDITS.md
```
In Windows PowerShell type `curl.exe`. Publish `index.html` with LICENSE and CREDITS.md; this file, README.md and `previews/` are not part of the site.

## Do not break
- Keep it one file unless the user asks otherwise; no framework or bundler for copy, colour or photo changes.
- Keep the ids and the `data-8b-section` / `data-8b-motion` attributes. Each section has its styles in `<style data-8b-part="section:<id>">` and its animation, if any, in `<script data-8b-part="scene:<id>">`.
- The scripts find these classes and attributes; when you change a section's markup, keep them or update the script:
  - `section-script:navigation`: `.nav__menu` `.menu` `.menu__close`
  - `scene:hero`: `.statement__dot` `.hero__aperture` `.hero__tint` `.hero__orbit` `.hero__word` `.hero__intro`
  - `scene:statement`: `.statement__line` `.statement__dot` `.statement__index`
  - `scene:work`: `.work__track` `.work__window` `.work__stage` `.work__plate` `.case__img` `.case`
  - `scene:again`: `.again__stage` `.again__head` `.again__swing` `.again__wheel` `.partner`
  - `scene:capabilities`: `.service` `.service__shade`
  - `scene:method`: `.step` `.method__station` `.method__steps` `.method__arc` `.method__arm`
  - `section-script:contact`: `.contact__form` `.contact__status` `data-success` `data-error`
  - `section-script:footer`: `.footer__news` `.footer__note` `data-success` `data-error`
  - `scene:studio`: `.studio__collage` `.shot`
  - `scene:journal`: `.journal__shot` `.story`
  - `scene:contact`: `.contact__voice` `.contact__title` `.m-dot`
  - `scene:footer`: `.footer__aperture` `.footer__period` `.footer__bye` `.footer__tint` `.footer__word`
- Colours, fonts, radii and shadows are CSS variables in the `:root` block (`data-8b-part="tokens"`); change them there and keep body text at 4.5:1 contrast or more.
- Animations run only when the visitor allows motion (`prefers-reduced-motion: no-preference`); the page must stay readable without them.
- A display line with `style="--len:N"` is sized to fill its width: N is its number of characters, spaces included (`Hello` → 5, `Let's talk` → 10).
- These neighbouring sections animate across their border: hero → statement, work → again. Keep each pair next to each other, or that transition switches off.
- Keep the header comment and `<meta name="generator">`; the "Design: 8B" footer link is optional.

## Replace before publishing
- Everything marked `data-8b-placeholder` (og-image, favicon, email, phone, form, social); remove the attribute once the real value is in. With no real value: no preview image — delete the `og:image` tag and set `twitter:card` to `summary`; no phone, email or address — remove that link or row.
- Instagram, LinkedIn and Vimeo links in the footer: link to the networks' home pages now; point them to your studio's profiles, or remove them.
- Case cards in work and stories in journal: link to nothing (they are not links) now; point them to your case-study and article pages, by wrapping each card or story in a link.
- **The forms send nothing.** `section-script:contact` and `section-script:footer` check the fields and show a thank-you message without sending. Pick one:
  - Formspree: set `action="https://formspree.io/f/<id>"` on the form; in the script, before the thank-you message, `await fetch(form.action, { method: 'POST', body: new FormData(form), headers: { Accept: 'application/json' } })` and show it only if the response is ok.
  - Netlify Forms (site on Netlify): add `name="contact" data-netlify="true"` and `<input type="hidden" name="form-name" value="contact">`; send with `fetch('/', { method: 'POST', headers: { 'Content-Type': 'application/x-www-form-urlencoded' }, body: new URLSearchParams(new FormData(form)) })`.
  - No form service: remove the `<form>` together with the script that handles it (it would fail without the form) and keep the email link.
- Invented demo facts (ask the user for the real ones; do not make up prices, dates or addresses):
  - Offices and cities: "Lisbon and Brooklyn" (meta description, phone menu, studio, FAQ "Where are you based?", contact, footer "Made in Lisbon and Brooklyn"); the two addresses (replaced with example streets) and the two phone numbers and two emails (replaced) in contact and footer.
  - Clients and results in work: Northwind Bikes ("launched in eleven cities in a single spring"), Halden Bank ("a 120-year-old bank"), Copper & Oat bakery, Atlas Museum, Sola Sound ("sold out its first run in nine days"), and the lead "Five launches from the last two years. Every one of them is still growing."
  - Long-term clients in again: Vela Air (Year 9), Kiln Coffee (Year 4), Larch Outdoor (Year 6), Tessera Games (Year 7), Civic Lab (Year 8), Marrow Health (Year 5, "across three hospital systems"), and "Most of our partners have been with us for more than five years".
  - Team: "Ninety people", "keep Friday afternoons for our own experiments" (studio); open roles Senior product designer (Lisbon), Creative technologist (Brooklyn), Strategy director (Remote, Europe) and the careers email (studio, footer).
  - Process and terms: a two-week listening sprint (method "Listen", FAQ "How does a project usually start?"), clients of "between fifty and five thousand people, plus a few public bodies", fixed fees per phase then a monthly team, "open about our rates on the first call", remote people "across Europe and the US east coast" (FAQ).
  - Journal: four dated stories (1 October, 18 September, 30 August, 4 August 2026, with read times of 2, 6, 8 and 5 minutes), the event "Open Studio Night returns to Lisbon on 14 November" in "the old print hall", "three hundred nurses" and "six weeks of field research", a "forty-metre billboard" (journal).
  - Service promises: "A real person reads every message and replies within two working days" (contact text and the form's success text); newsletter "once a month", "No spam, one email a month" (footer).
  - "© 2026 Onda Studio" (footer).
- `<title>`, the meta description and the og tags; photos (Unsplash, see CREDITS.md) when the user has their own.

## Notes
- Every heading ends in a violet dot (`<span class="m-dot">`), not a typed full stop: keep the span when you change a heading.
- "Hello" in the hero and "Bye" in the footer are sized by `style="--len:N"` (number of characters) and are meant for one short word.
- The contact form and the newsletter field send nothing; they check the fields in the browser and show a status text.
- Without JavaScript the phone menu button cannot open the overlay; the links stay reachable in the statement index and the footer.
- During the hero → statement handoff the travelling round photo briefly crosses the statement lines before it lands; on phones, during the work → again handoff, the rising wheel briefly overlaps the right side of the again lead. Both clear before the transition ends.

## Common edits
- Rebrand: search the old name (`Onda`) in any letter case and replace every match; change the favicon letter and colours in `<link rel="icon">`.
- Photos: replace `src` and delete `srcset` and `sizes` (they list Unsplash sizes), keep `width`/`height` to the new photo's ratio, update `alt` and CREDITS.md.
- Remove a section: delete its markup, its `section:<id>` and `scene-style:<id>` styles, its `scene:<id>` and `section-script:<id>` scripts, and links to `#<id>`.
- Native scroll instead of smooth scroll: delete the Lenis block in `page-init` and the Lenis `<script>` tag.

## Check and publish
- Open the page at 375 and 1440 px, with reduced motion on, with the console open.
- Search `data-8b-placeholder` and the old name: nothing should be left but class names.
