# Project Rules & AI Assistant Constraints (ClubFlow — PA#2)

## 1. Tech Stack & Architecture
- **Stack:** Static HTML5 (`index.html`, `review.html`, `interview.html`) and plain CSS (`styles.css`).
- **No JavaScript Dependency:** All pages are graded with JavaScript disabled (`Disable JavaScript` in DevTools) and offline. Every piece of content, including application review details/drawers, must be visible and readable without JavaScript.
- **No External Dependencies:** Do not load external CSS frameworks, web fonts, or icon libraries from CDNs.

## 2. Spacing Scale & Typography System
- **Spacing Scale (Custom Properties in `:root`):**
  - `--space-1`: `4px`
  - `--space-2`: `8px`
  - `--space-3`: `12px`
  - `--space-4`: `16px`
  - `--space-5`: `20px`
  - `--space-6`: `24px`
  - `--space-8`: `32px`
  - `--space-10`: `40px`
- **Typography:** Base body font size must be `16px` (`1rem`) with `1.55` line-height.
- **Color Contrast:** All text and interactive controls must pass WCAG AA `4.5:1` contrast ratio.

## 3. Responsive & Mobile-First Rules
- **Target Widths:** Must work seamlessly at `360px`, `768px`, and `1280px` with zero horizontal page scroll (`document.documentElement.scrollWidth > document.documentElement.clientWidth` must be `false`).
- **Breakpoints:**
  - Base (`0px–767px`): Single-column mobile-first layout (`360px` target).
  - Tablet (`@media (min-width: 768px)`): 2-column form grids, 4-column stat cards, 3-column summaries.
  - Desktop (`@media (min-width: 1024px)`): 3-column position cards on `index.html`, side-by-side 2-column table + drawer workspace on `review.html` (`1280px` target).
- **Tap Targets:** All standalone `<button>`, `<a class="btn">`, `<summary>`, and navigation links must have `min-height: 44px`.

## 4. Semantic HTML & Validation Rules
- **Landmarks:** Every page must include `<header>`, `<nav>`, `<main id="main">`, and `<footer>`.
- **Headings:** Exactly one `<h1>` per page. Heading levels (`<h1>` -> `<h2>` -> `<h3>`) must never skip a level.
- **Forms & Controls:** Every `<input>`, `<select>`, and `<textarea>` must have an explicit, visible `<label for="...">`.
- **Links vs. Buttons:** Navigating between pages in the main flow (`index.html` -> `review.html` -> `interview.html`) must use relative `<a href="...">` links or `<form action="...">` submit buttons. In-page actions use `<button type="button">`.
- **Validation:** 0 errors in the W3C Nu Html Checker (`validator.w3.org/nu`).

## 5. Never List (Strictly Forbidden)
- **NEVER** use `!important` in `styles.css`.
- **NEVER** use arbitrary spacing magic numbers outside the defined `--space-*` scale.
- **NEVER** use `overflow-x: hidden` on `html`, `body`, or main page wrappers to mask horizontal overflow (use `.table-scroll` with `overflow-x: auto` around wide data tables only).
- **NEVER** use fixed pixel widths (`width: 500px`) that exceed `360px`.
- **NEVER** use `<div>` or `<span>` as interactive buttons or links.
- **NEVER** include any problem from the ClubFlow "Fix these" list:
  - No mismatched dates across screens (use Oct 15 – Oct 30, 2026 for applications, and Nov 5, 2026 for interviews everywhere).
  - No wrong page titles on Screen 2.
  - No overlapping people between Applicants and Interviewers.
  - No mismatch between summary/footer counts and table rows on Screen 3.
  - No fake conflict on Screen 3 (conflict rows must genuinely overlap in time/person/room).
  - No "Verified" / "Verified Student" / "100% verified" badges or text.
  - No template footer links ("© 2025 ClubFlow", "Privacy Policy", "Terms of Service", "Support Center").