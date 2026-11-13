# Merlyn Garcia — Personal Portfolio

**Live site:** https://prodigy181.github.io/portfolio/

---

## Milestone 3: Accessibility Fixes

The following changes were made to pass WAVE with zero errors and meet WCAG 2.1 AA.

| File | Fix |
|------|-----|
| `about.html` | Added a skip-to-main-content link before `<header>` so keyboard users can bypass navigation. |
| `projects.html` | Added the same skip-to-main-content link before `<header>`. |
| `about.html` | Added `id="main-content"` to `<main>` so the skip link has a valid jump target. |
| `projects.html` | Added `id="main-content"` to `<main>` for the same reason. |
| `about.html` | Added `aria-current="page"` to the About &amp; Contact nav link so screen readers announce the active page. |
| `projects.html` | Added `aria-current="page"` to the Projects nav link for the same reason. |
| `about.html` | Replaced the contact placeholder with a fully accessible form: `<fieldset>`/`<legend>`, `<label for="…">` on every field, `aria-required="true"`, and `aria-describedby` pointing to inline error messages with `role="alert"`. |
| `style.css` | Added visible error-state styles (`border-color: #e53935` on `aria-invalid="true"` inputs) and `[hidden]` override for error messages. |

### Color contrast (WCAG AA — minimum 4.5:1 for normal text)

| Foreground | Background | Ratio | Pass? |
|-----------|-----------|-------|-------|
| `#f5f5f5` | `#0b1f3a` | ≈ 13.7 : 1 | ✅ |
| `#00c853` | `#0b1f3a` | ≈ 6.9 : 1 | ✅ |
| `#f5f5f5` | `#12294a` | ≈ 11.7 : 1 | ✅ |
| `#0b1f3a` | `#00c853` | ≈ 6.9 : 1 | ✅ (button text) |

No color changes were needed; the existing palette already passes AA on every combination.

---

## Gestalt Principles Applied

### 1. Proximity
Every project card and skill card groups its heading, body text, and any sub-elements inside a single `.card` container with consistent internal padding (24 px). The gap *between* cards (16 px) is intentionally larger than the gap *within* a card, so each card reads as one coherent unit of information rather than a loose list of text.

**Where it appears:** `.card-grid` on `projects.html` (three project cards) and `about.html` (cybersecurity cards).

### 2. Similarity
All cards share the same visual treatment: `background-color: #12294a`, 8 px border radius, 24 px padding, and a 4 px left accent border in `#e53935`. This uniform appearance signals to the reader that the cards belong to the same content category and should be scanned as a group.

**Where it appears:** Every `.card` element across all three pages.

---

## File structure

```
portfolio/
├── index.html      # Home page
├── projects.html   # Projects listing
├── about.html      # About me + contact form
├── style.css       # All styles (mobile-first, responsive)
├── photo.png       # Hero illustration
└── README.md       # This file
```
