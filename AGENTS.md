# AGENTS.md: design studio website template

One-page website for a design, brand or digital agency. One file, `index.html`, with inline CSS and scripts (GSAP, ScrollTrigger, Lenis from jsDelivr); no build step, and none is needed for copy, colour or photo edits.

## Files
Edit these files, not a page fetched by URL (that arrives as a summary).
```bash
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/index.html
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/AGENTS.md
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/LICENSE
curl -LO https://raw.githubusercontent.com/8bsite/design-studio-website-template/main/CREDITS.md
```
Upload `index.html`, LICENSE and CREDITS.md; not this file, README.md or `previews/`.

## Keep
- Every `id`, `data-8b-section`, `data-8b-motion` and `data-8b-part` (`section:<id>` styles, `scene:<id>` animation).
- Selectors the scripts use:
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
- `hero` directly above `statement`, `work` directly above `again`: the animation crosses that border and stops if they are split.
- `style="--len:N"` = characters in that display line, spaces included: `Hello` is 5, `Let's talk` is 10, `Bye` is 3.
- Section headings (and Open roles) end in a violet dot (`<span class="m-dot">`), not a typed full stop: keep the span when you change one. Hello and Bye use a round photo instead; case, partner, service, step and story titles have no dot.
- "Hello" in the hero is sized by its `style="--len:N"` on phones only (wide screens use a fixed size), and "Let's talk" in contact by its own --len; "Bye" in the footer has a fixed size whatever its --len says. Keep Hello and Bye to one short word.
- Colours and fonts are variables in `:root` (`data-8b-part="tokens"`): `--color-1` #0d0c11 (near-black bands and text), `--color-2` #ffffff (white bands, text on black), `--color-3` #6c3cff (violet dots, buttons, process ring, contact section), `--color-4` #efeef4 (pale cards for services and the form), `--color-5` #aaa7b4 (muted text on black), `--color-6` #5d5a67 (secondary text on white), `--color-7` #1f1d26 (dark base under photos); body text needs 4.5:1 contrast.
- With reduced motion the page must read in full.
- Keep the header comment and `<meta name="generator">`. Keep the "Design: 8B" footer link unless the site owner asks to remove it.

## Replace
- `data-8b-placeholder` (og-image, favicon, email, phone, form, social): real value in, attribute out; no value, remove the row (no image: drop `og:image`, set `twitter:card` to `summary`).
- Instagram, LinkedIn and Vimeo links in the footer: now the networks' home pages; owner's target: your studio's profiles, or remove them.
- Case cards in work and stories in journal: now nothing (they are not links); owner's target: your case-study and article pages, by wrapping each card or story in a link.
- The form in `#contact` (fields `name`, `email`, `company`, `topic`, `message`) sends nothing; `section-script:contact` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The form in `#footer` (fields `email`) sends nothing; `section-script:footer` validates it and shows the thank-you text. Formspree: `action="https://formspree.io/f/<id>"` and `fetch` POST `new FormData(form)` first. Netlify: `data-netlify="true"` and a hidden `form-name`. Or delete it and the script.
- The name Onda (any letter case); the favicon letter and colours in `<link rel="icon">`.
- Photos (26, Unsplash: hero 1, footer 1, work 5, again 6, capabilities 5, studio 5, journal 4): `src`, no `srcset`/`sizes`, `width`/`height` to the ratio, `alt`, CREDITS.md.
- `<title>`, meta description, og tags.

## Ask the owner for
All demo text, never to be invented:
- Offices and cities: "Lisbon and Brooklyn" (meta description, phone menu, studio, FAQ "Where are you based?", contact, footer "Made in Lisbon and Brooklyn"); the two addresses (replaced with example streets) and the two phone numbers and two emails (replaced) in contact and footer.
- Clients and results in work: Northwind Bikes ("launched in eleven cities in a single spring"), Halden Bank ("a 120-year-old bank"), Copper & Oat bakery, Atlas Museum, Sola Sound ("sold out its first run in nine days"), and the lead "Five launches from the last two years. Every one of them is still growing."
- Long-term clients in again: Vela Air (Year 9), Kiln Coffee (Year 4), Larch Outdoor (Year 6), Tessera Games (Year 7), Civic Lab (Year 8), Marrow Health (Year 5, "across three hospital systems"), and "Most of our partners have been with us for more than five years".
- Team: "Ninety people", "keep Friday afternoons for our own experiments" (studio); open roles Senior product designer (Lisbon), Creative technologist (Brooklyn), Strategy director (Remote, Europe) and the careers email (studio, footer).
- Process and terms: a two-week listening sprint (method "Listen", FAQ "How does a project usually start?"), clients of "between fifty and five thousand people, plus a few public bodies", fixed fees per phase then a monthly team, "open about our rates on the first call", remote people "across Europe and the US east coast" (FAQ).
- Journal: four dated stories (1 October, 18 September, 30 August, 4 August 2026, with read times of 2, 6, 8 and 5 minutes), the event "Open Studio Night returns to Lisbon on 14 November" in "the old print hall", "three hundred nurses" and "six weeks of field research", a "forty-metre billboard" (journal).
- Service promises: "A real person reads every message and replies within two working days" (contact text and the form's success text); newsletter "once a month", "No spam, one email a month" (footer).
- "© 2026 Onda Studio" (footer).

## Known limits
- The contact form and the newsletter field send nothing; they check the fields in the browser and show a status text.
- Without JavaScript the phone menu button cannot open the overlay; the footer still links Work, Services, Approach, Studio and Journal.
- During the hero → statement handoff the travelling round photo briefly crosses the statement lines before it lands; on phones, during the work → again handoff, the rising wheel briefly overlaps the right side of the again lead. Both clear before the transition ends.

## Check
375 and 1440 px, reduced motion on, console clean; `data-8b-placeholder` and Onda left only in class names.
