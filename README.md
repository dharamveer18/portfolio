# Dharamveer Singh Tanwar — Portfolio

A one-page portfolio. Dark and modern by default (warm ink, copper accent, card
sections, scroll animation) with a light mode that follows the visitor's system
setting. Plain HTML, CSS and JavaScript — no build step, no dependencies.

```
index.html          all page content
css/style.css       tokens, layout, components, motion
js/main.js          theme, menu, scroll reveal, form validation
assets/favicon.svg  copper "DT" mark
.claude/launch.json dev-server config for the preview pane
```

## Run it

```bash
python3 -m http.server 4173
```

Open http://localhost:4173. To deploy, copy the folder onto any host.

## About the copy — read this before publishing

The site is written to be accurate for where you are now: **three years of
professional engineering experience, delivered inside a company for its clients,
now opening up to direct freelance work.** It deliberately does **not** claim
freelance client counts, testimonials, revenue figures or retention rates.

That's the pitch, not a limitation. "Three years of production code, most of it
ERP and internal tools businesses use daily" is stronger and safer than an
invented number a client could ask you to back up on a call.

Two places carry the framing, and both are honest as written:

- The work section says these were built inside a team for the company's clients,
  which is why there are no logos or screenshots. Clients read that as
  professional discretion, not inexperience.
- The facts row claims only: three years writing production code, end-to-end
  capability, a reply within a day. The last one is a promise you control.

The three work entries are your real projects:

1. **Inventory and purchase ERP for a clothing brand** — Python / Django. Unnamed
   under NDA, illustrated with an abstract data-table graphic rather than a screen.
2. **Village in India** — named, linked and live at villageinindia.com, with a
   clickable tile.
3. **Site, admin panel and table-ordering app for a hotel and restaurant chain** —
   Python + React Native. Unnamed under NDA, illustrated with a phone-and-QR graphic.
4. **Students Organizer** — UI/UX in Figma, with the design file and the case study
   both linked. The card copy currently describes only what is visible in the file
   (wireframes, colour system, UI kit, task states, progress views, prototype,
   iPhone 14 Plus frames). **Paste the case-study text and this card should be
   rewritten around it** — the problem, who it is for, what the research showed and
   what the design changed. Figma renders on a canvas, so the case-study text cannot
   be read from the link; export that frame as PNG or PDF, or paste the text.

The two NDA cards carry an "under NDA" tag and use drawn graphics, not fake
screenshots. That reads as professional discretion and keeps you on the right side
of the agreement. If a client later agrees to be named, swap the tag for their
name and add a real screen.

## Placeholders to replace

| Where | What |
| --- | --- |
| Contact section | `hello@example.com`, `+91 00000 00000`, the three social links |
| `js/main.js`, end of the form handler | the same `hello@example.com` in the `mailto:` |
| Hero | "the last three years" — update as this changes |
| Photo caption | "India · working remotely" — add your city if you want local clients |
| `.photo__slot` in `index.html` | swap the `DT` block for `<img src="assets/you.jpg" alt="Dharamveer Singh Tanwar" />` |
| `assets/work-village.svg` | optional: drop your own screenshot in as `assets/work-village.png` and change the `src` on the Village in India card |

A real photo matters more than anything else on this page. A plain, well-lit
photo of you does more for trust than any amount of design.

## What to add once you have it

- Client names or logos, once one says yes to being named.
- A real screenshot of the hotel site and the ordering app, if that client clears it.
- One real testimonial. Ask after a project goes well; most people say yes.
- A case-study page per project, with before/after numbers you can actually show.

Don't add any of these before they're true — a client who catches one invented
detail stops believing the rest of the page.

## Contact form

No backend, so submitting opens the visitor's mail client with the message
pre-filled. For real submissions, point the form at Formspree / Web3Forms or your
own endpoint and replace the `mailto:` block in `js/main.js` with a `fetch()` POST.

## Design system

All in the `:root` block of `css/style.css`:

- **Colour** — a warm dark ink ramp (not blue-black) plus one copper accent,
  `--accent`. Change it in both the `:root` and `[data-theme="light"]` blocks to
  rebrand the whole site.
- **Type** — Space Grotesk for headings, Inter for text, and Fraunces italic used
  sparingly for the hand-set details: the word "actually" in the headline, the
  card numbers, the step numbers, the pull quote.
- **Spacing** — `--s-1` (4px) to `--s-10` (128px); every gap and pad uses one.
- **Depth** — one shadow, three radii, a single hairline border colour.

Small deliberate imperfections keep it from looking template-generated: the logo
mark and photo sit at a slight angle, the headline underline is a hand-drawn SVG
stroke that draws itself in, and the floating chips bob out of sync.

## Behaviour

- Theme follows the OS on first visit, then remembers the visitor's choice.
- Scroll reveals, the underline stroke, the ticker and the bobbing chips all run
  through `IntersectionObserver` / CSS and are disabled under
  `prefers-reduced-motion: reduce`.
- Keyboard accessible throughout: skip link, visible focus rings, semantic
  landmarks, labelled form fields with inline errors.
