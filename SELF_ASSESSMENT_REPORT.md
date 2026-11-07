# Self-Assessment Report (SELF_ASSESSMENT_REPORT.md)

## Team Information
- **Course:** CSC13008 — Web Application Development (24KTPM1)
- **Milestone:** PA#2 — Responsive Prototype (ClubFlow)
- **Team Members:**
  - Lai Phạm Như Phúc — `24127106`
  - Nguyễn Thục Nghi — `24127207`
  - Trần Văn Nam — `24127459`
- **Self-Assessed Total Score:** **96 / 100**

---

## Rubric Criteria Breakdown

| # | Criterion | Max Points | Claimed Points | Evidence (Files, Screenshots, Validator Results, Commits) |
| :-: | :--- | :-: | :-: | :--- |
| 1 | **Three linked screens that trace back to the ClubFlow brief** | 20 | **20** | - **Files:** `index.html` (Create Recruitment Campaign), `review.html` (Application Review), `interview.html` (Interview Scheduling), documented in `PROTOTYPE.md` (Sections 3–5).<br>- **Main-flow links:** Relative `<a href>` links in `<nav>` and `.flow-nav`, plus `<form action="review.html" method="get">` on `index.html`; zero `#` dead links.<br>- **Fix these list resolved:** Unified timeline (`15/10/2026–30/10/2026` -> interview `05/11/2026`), proper `Duyệt hồ sơ ứng tuyển` title on `review.html`, readable side-by-side/accordion drawer (`#a01[open]`), exact Screen 3 count match (`2 Proposed + 2 Conflict + 1 Unassigned = 5 Shortlisted`), genuine overlap on `A01` & `A02` at `09:00–09:20`, disjoint applicant/interviewer names, no "Verified" text, and no template footer. |
| 2 | **Responsive at 360, 768 and 1280 px** | 25 | **24** | - **Screenshots:** 9 full-page screenshots with JS off in `screenshots/` (`index-360.png`, `index-768.png`, `index-1280.png`, `review-360.png`, `review-768.png`, `review-1280.png`, `interview-360.png`, `interview-768.png`, `interview-1280.png`).<br>- **Zero horizontal scroll:** Verified at 360, 768, and 1280 px in `checks/responsive-browser-check.txt` (`scrollWidth > clientWidth` is `false` on all 9 runs; wide tables scroll inside `.table-scroll` wrappers).<br>- **Tap targets & long items:** All standalone buttons/links have `min-height: 44px` in `styles.css`; long Vietnamese strings (`Phát triển website quản lý hoạt động và hệ thống thông tin câu lạc bộ`, `Nguyễn Hoàng Phương Thảo Như Quỳnh`) wrap cleanly.<br>- **Adaptive layout:** 1 column at `360px`, 2–4 columns at `768px`, and 3-column position cards / 2-column review workspace at `1280px`. |
| 3 | **Semantic, valid HTML** | 20 | **20** | - **W3C Nu Html Checker:** 0 errors on all three pages (`checks/validator-index.png`, `checks/validator-review.png`, `checks/validator-interview.png`).<br>- **Semantics:** Every page has `<header>`, `<nav>`, `<main id="main">`, and `<footer>`, exactly one `<h1>`, sequential `<h2>`/`<h3>` headings, `<fieldset>`/`<legend>` for position groups, and explicit visible `<label for="...">` elements on all 25+ form inputs/selects/textareas. |
| 4 | **Design you can check** | 10 | **9** | - **Spacing scale:** Defined in `styles.css` (`:root` variables `--space-1: 4px` to `--space-10: 40px`) and used consistently across all rules.<br>- **Typography & Contrast:** Base font size `16px` (`html { font-size: 16px }`), body ink `#1e293b` on `#f6f8fc`/`#ffffff` (>12:1), primary button `#ffffff` on `#4338ca` (8.6:1), muted text `#475569` (>7:1), disabled buttons `#334155` on `#f1f5f9` (>7.5:1).<br>- **CSS hygiene:** Plain CSS only; `0` occurrences of `!important`. |
| 5 | **The brief and the rules file** | 10 | **9** | - **Files:** `AGENTS.md` and `brief.md` at the repository root.<br>- **Evidence:** `AGENTS.md` records the static HTML/CSS stack, `--space-*` scale, mobile-first breakpoints (`360px`, `768px`, `1280px`), semantic rules, and the complete "Never list". `brief.md` contains the chronological prompts given to the assistant with all constraints and verification steps. |
| 6 | **AI-LOG.md** | 10 | **9** | - **File:** `AI-LOG.md` at the repository root.<br>- **Evidence:** 4 task entries documenting Tool, Request, Changed, and Rejected. Specifically logs issues caught by our checks (magic spacing numbers in CSS, collapsed `<details>` drawers when JS is off, missing `Conflict` overlap/action column on Screen 3, and `360px` table overflow) and how we prompted the assistant to fix them. |
| 7 | **Commit history** | 5 | **5** | - **Evidence:** `.git/` folder included in the zip archive. Commit history starts with the rules file (`AGENTS.md`), followed by separate commits for `index.html`, `review.html`, `interview.html`, the responsive/spacing pass, and final documentation/validation evidence, authored under each team member's name and student email. |
| **Total** | | **100** | **96** | |

---

## What We Did Not Manage
- Because we chose static HTML and plain CSS (with JavaScript disabled for grading), interactive filtering on `review.html`, dynamic modal previews on `index.html`, and interactive conflict resolution modal forms on `interview.html` are represented as static states and disabled prototype buttons (`disabled` with descriptive `title` tooltips) to be wired up with React state in PA#3.