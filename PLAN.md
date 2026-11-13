# Portfolio site plan

My personal portfolio: one page, plain HTML and CSS (a little JavaScript later), hosted on GitHub Pages.

This file holds the design decisions and the build checklist. The design was sketched in Claude first, so the values below are the starting point. I can change anything as I build.

---

## The page at a glance

One scrolling page, top to bottom:

1. **Header**: "LG" on the left, links on the right (Projects, About, Resume, Contact).
2. **Hero**: big name, tagline, one line about me and my availability, two buttons.
3. **Built & building**: my projects as three cards.
4. **The fade**: the light page background fades into my Ten Peaks photo.
5. **About me**: a card floating on the photo.
6. **Gap**: open space so the peaks show between About and Contact.
7. **Looking for my next crew**: a dark, slightly see-through contact block on the photo.
8. **Footer**: a small strip on the photo with the copyright and photo credit.

The nav links scroll to sections on the same page (`#projects`, `#about`, `#contact`). "Resume" links straight to a PDF.

---

## Design values

### Colours

| Use | Value |
|---|---|
| Page background (Cool cloud) | `#F1F4F7` |
| Main text | `#1D2A2B` |
| Muted text | `#4E5D5E` |
| Body text in cards | `#3C4A4B` |
| Teal accent (buttons, links, "In progress") | `#2F6B6E` |
| Dark teal (link text, hover) | `#1F4A4C` |
| Light teal tint | `#DCEAE8` |
| Amber dot ("Planned") | `#D69E2E` |
| Amber text ("Planned") | `#8A5A12` |
| Light amber tint | `#FBEFD9` |
| Paper card background | `#FBFCFD` |
| Card border and hard shadow | `#1D2A2B` |
| Light divider lines | `#E8ECEF` |

Contact block (on the photo):

| Use | Value |
|---|---|
| Background (see-through, no blur) | `rgba(16, 26, 28, 0.74)` |
| Border | `1px solid rgba(241, 244, 247, 0.28)` |
| Hard shadow | `8px 8px 0 rgba(8, 14, 16, 0.55)` |
| Heading text | `#F1F4F7` |
| Paragraph text | `#D3DBDC` |
| Email button | background `#8FC7C9`, text `#14201F` |
| Outline buttons | text `#F1F4F7`, 1.5px border `rgba(241, 244, 247, 0.6)` |

All text colours above were checked for readable contrast against their backgrounds.

### Fonts (Google Fonts)

- **Fraunces**, weight 700: the name, section headings, "LG".
- **Inter**, weights 400, 500, 600: everything else.
- The **&** in "Built & building" is Inter 600 in teal, inside a `<span>`.

### Shapes and shadows

- Paper cards (projects, About): `3px` corners, `1px solid #1D2A2B` border.
- Project card hard shadow: `6px 6px 0 rgba(29, 42, 43, 0.85)`.
- About card hard shadow: `8px 8px 0 rgba(29, 42, 43, 0.85)`.
- Buttons: `6px` corners.
- Content width: max `1160px`, centred, with `24px` side padding.

---

## Sections in detail

### 1. Header
- "LG" in Fraunces 700, about 24px, links to the top of the page. Give it `aria-label="Lance Gomez, home"`.
- Links: Projects, About, Resume, Contact, in Inter 500, 15px.
- Keep it plain. "Contact" is a plain link, not a filled button, so nothing competes with my name.
- Later, optional: make it sticky so it stays at the top when scrolling.

### 2. Hero
- Name: "Lance Gomez", Fraunces 700, very large: `clamp(80px, 12.5vw, 176px)`, `line-height: 0.92`, `letter-spacing: -0.03em`.
- Tagline: "Part code, part wandering, mostly curiosity." Inter 500, 26px.
- Sub-line: "BCIS student at Mount Royal University in Calgary, looking for a Spring or Summer 2027 internship." Inter, 18px, muted.
- Buttons: "See my work" (filled teal, white text) and "Resume" (white with a thin outline).
- Lots of space above and below (about 130–140px).

### 3. Built & building
- Heading: "Built **&** building", with the & in teal Inter.
- Three cards in a responsive grid: `repeat(auto-fit, minmax(260px, 1fr))`, 20px gap.
- Each card, top to bottom: status, project name, one-line description, tech stack (small, muted), and a row of links at the bottom.
- **Status as a dot plus text**, not a pill:
  - In progress: 8px teal dot with a 3px light-teal ring, text in dark teal.
  - Planned: 8px amber dot with a 3px light-amber ring, text in amber.
- Links: "View code ↗", "Live demo ↗", or plain "Coming soon" when there's nothing to link yet.

| Project | Status | Links |
|---|---|---|
| This website | In progress | View code |
| Baskemtball | Planned | Coming soon |
| [Web 2 project] | In progress | View code, Live demo |

### 4. The fade and the photo
- One wrapper holds About, the gap, Contact and the footer, with my photo as its background:
  - `background-image: url("images/rockies-ten-peaks.jpg")`
  - `background-size: cover; background-position: center 70%;`
- At the very top of that wrapper, a 160px-tall element with `linear-gradient(to bottom, #F1F4F7, transparent)`. That's the fade from the page into the photo.

### 5. About me (paper card on the photo)
- Top row: round photo of me (84px circle, 1px dark border) next to "About me" (Fraunces) and "3rd year BCIS · Calgary, AB" (muted).
- Paragraph about me (I'll write my own).
- **I work with:** SQL · PHP · JavaScript · HTML & CSS · SAP, separated by teal dots.
- **Off the clock:** Above the treeline, Music, Film, Video games, Fantasy basketball, each with a small teal line icon (mountain, music note, film, game controller, basketball). Tabler Icons or simple inline SVGs both work.
- Link: "Full skills & experience on my resume →".
- Small uppercase labels ("I WORK WITH", "OFF THE CLOCK"): 13px, weight 600, letter-spacing 0.06em, muted.
- Below the card: about **380px of empty space** so the peaks in the photo show through.

### 6. Looking for my next crew
- Heading: "Looking for my next crew" with the straw hat (`images/straw-hat.svg`) where the period would be, about 46×28px.
- Paragraph: "Hiring for Spring or Summer 2027, or just want to chat about databases or movie recommendations? My inbox is open." (I'll rewrite this.)
- Buttons: Email (filled light teal), LinkedIn and GitHub (outline).
- Use the contact block values from the colours section. No blur.

### 7. Footer
- Small strip below the contact block in the same dark see-through style.
- Left: "© 2026 Lance Gomez · Calgary, AB". Right: "Photo: Lance Gomez · Valley of the Ten Peaks, Banff National Park".

---

## Placeholder content to replace

- [ ] My own wording for the About paragraph, project descriptions and contact line
- [ ] Web 2 project name, description and tech stack
- [ ] Baskemtball tech stack
- [ ] Email, LinkedIn and GitHub links
- [ ] A photo of me for the About circle (save as `images/lance.jpg`)
- [ ] Resume PDF (save as `resume.pdf`)

---

## Build checklist

Each step is small. Commit after each one.

### Step 0: Set up
- [ ] Create an empty public repo on GitHub (for example `lance-portfolio`), with no README or license.
- [ ] Clone it in VS Code.
- [ ] Copy these starter files into the folder.
- [ ] First commit and push: "Add starter files and plan".

### Step 1: HTML skeleton
- [ ] Boilerplate: doctype, `lang="en"`, meta charset and viewport, title, link to `style.css`.
- [ ] Google Fonts link for Fraunces and Inter.
- [ ] Empty semantic sections: `header`, `main`, `section`s with ids, `footer`.
- Learn: semantic HTML, why `id`s make the nav links work.

### Step 2: CSS foundations
- [ ] CSS variables in `:root` for every colour above.
- [ ] Base styles: body font, background, text colour, `margin: 0`.
- [ ] A reusable container class: max-width 1160px, centred, 24px side padding.
- Learn: CSS custom properties, the box model, `box-sizing`.

### Step 3: Header
- [ ] "LG" and the nav links with flexbox, space-between.
- Learn: flexbox basics, `gap`, `justify-content`.

### Step 4: Hero
- [ ] Name, tagline, sub-line, two buttons.
- [ ] Responsive name size with `clamp()`.
- Learn: `clamp()`, typography spacing, button styling.

### Step 5: Built & building
- [ ] Heading with the teal &.
- [ ] Three project cards in a CSS grid.
- [ ] Status dots, hard shadows, links pinned to the bottom of each card.
- Learn: CSS grid, `auto-fit` with `minmax`, `box-shadow`, `margin-top: auto`.

### Step 6: Photo and fade
- [ ] Wrapper with the background photo.
- [ ] Gradient fade at the top.
- Learn: `background-image`, `background-size: cover`, `linear-gradient`.

### Step 7: About card
- [ ] Paper card with the photo circle, heading row, lists and icons.
- [ ] Space below for the peaks.
- Learn: `border-radius: 50%`, `object-fit: cover`, inline SVG or icon fonts.

### Step 8: Contact and footer
- [ ] Dark see-through block with the straw hat heading and buttons.
- [ ] Footer strip.
- Learn: `rgba()` colours, `mailto:` links, `target="_blank"` with `rel="noopener"`.

### Step 9: Mobile
- [ ] Test at phone width in the browser dev tools.
- [ ] Fix anything that overflows: wrap the nav, stack columns, shrink padding.
- Learn: media queries, mobile-first thinking.

### Step 10: Polish
- [ ] Hover and `:focus-visible` styles for links and buttons.
- [ ] Optional: About card rises in on scroll (CSS `animation-timeline: view()`), turned off for `prefers-reduced-motion`.
- [ ] Alt text on every image.
- Learn: accessibility basics, CSS animations.

### Step 11: Launch
- [ ] Convert the photo to WebP to load faster.
- [ ] Add `resume.pdf`.
- [ ] Turn on GitHub Pages: Settings → Pages → deploy from `main`.
- [ ] Check the live site on my phone.
