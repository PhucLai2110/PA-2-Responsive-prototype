# ClubFlow Responsive Prototype (PROTOTYPE.md)

## 1. Team
| Full Name | Student ID | Role / Primary Screen |
| :--- | :--- | :--- |
| Lai Phạm Như Phúc | 24127106 | Screen 1 (`index.html`), CSS system & W3C verification |
| [Họ và Tên Thành viên 2] | [MSSV 2] | Screen 2 (`review.html`) & Responsive layout |
| [Họ và Tên Thành viên 3] | [MSSV 3] | Screen 3 (`interview.html`) & Schedule conflict logic |

## 2. How to Open It
- **How to open:** Open `index.html` directly in any browser from the repository folder (double-click or `file://`).
- **Network connection:** **Not required.** All styles are in the local `styles.css` file using system fonts; no CDN scripts, external stylesheets, or web fonts are loaded.
- **JavaScript:** **Not required.** All three pages are static HTML and render 100% of their content with JavaScript disabled.

## 3. Screens
| File | ClubFlow Brief Screen | What the User (Executive) Does There | Links & Navigation Targets |
| :--- | :--- | :--- | :--- |
| `index.html` | **Screen 1: Create Recruitment Campaign** | Configures campaign name, host club (`CLB Công nghệ thông tin`), opening/closing dates (`15/10/2026 – 30/10/2026`), description, candidate instructions, and 3 departments/positions (total quota: 7). Reviews summary and publishes/proceeds to review. | Header logo -> `index.html`<br>Nav "Chiến dịch" -> `index.html`<br>Nav "Duyệt hồ sơ" -> `review.html`<br>Nav "Lịch phỏng vấn" -> `interview.html`<br>Form submit button ("Xuất bản & Duyệt hồ sơ →") -> `review.html` |
| `review.html` | **Screen 2: Application Review** | Views campaign application statistics (`8` applications from `7` applicants: `5` Shortlisted, `2` Pending, `1` Rejected), searches/filters by name, status, position, and sort order, inspects the 8-row list (`A01`–`A08`), and reviews applicant CVs, motivation statements, internal notes, and `Shortlist Candidate` / `Reject` actions inside the Application Drawer. | Header logo -> `index.html`<br>Nav links -> `index.html`, `review.html`, `interview.html`<br>Table "Xem hồ sơ" links -> `#a01` through `#a08` (in-page drawer anchors)<br>"← Quay lại chiến dịch" -> `index.html`<br>"Tiếp tục: Lịch phỏng vấn →" -> `interview.html` |
| `interview.html` | **Screen 3: Interview Scheduling** | Sets interview parameters (`05/11/2026`, `09:00–12:00`, `20 phút` slots), inspects available interviewers and rooms, reviews the 5 shortlisted applications (`2 Proposed`, `2 Conflict`, `1 Unassigned`), identifies the `09:00–09:20` overlap for `Nguyễn Minh Anh` (`A01` & `A02`) and the unassigned reason for `A05`, and sees why final schedule confirmation is blocked. | Header logo -> `index.html`<br>Nav links -> `index.html`, `review.html`, `interview.html`<br>"← Quay lại duyệt hồ sơ" -> `review.html`<br>"Về chiến dịch" -> `index.html` |

## 4. Your Design Choices
1. **Top Navigation Bar Instead of Left Sidebar:** We replaced the brief's persistent left sidebar with a responsive top header (`<header class="site-header">`) so that at `360px` and `768px` the full viewport width is dedicated to forms, tables, and drawers without requiring a JavaScript hamburger toggle.
2. **Side-by-Side Workspace & Native `<details>` Drawer on Screen 2:** Instead of a floating overlay drawer that obscures the application table (one of the brief's *Fix these* problems), we placed the application table and the Application Drawer inside a responsive 2-column grid (`.review-workspace`) at `1280px` and stacked them cleanly on smaller screens. Using native `<details class="app-detail">` with `#a01` open by default ensures the drawer works and is fully visible with JavaScript turned off.
3. **End-to-End Conflict Demonstration on Screen 3:** We modeled the exact end-to-end conflict scenario from Section 3.4 of the ClubFlow brief: applicant `Nguyễn Minh Anh` is shortlisted for two positions (`A01` - Ban Truyền thông and `A02` - Ban Kỹ thuật) and both draft interviews are placed at `09:00–09:20` on `05/11/2026`. Both rows are flagged as `Conflict`, and the summary counts (`2 Proposed + 2 Conflict + 1 Unassigned = 5 Shortlisted`) match the table rows 100%.
4. **All "Fix these" Issues Eliminated:**
   - **Unified Timeline:** Applications open `15/10/2026`, close `30/10/2026` (Screens 1 & 2), and interviews take place on `05/11/2026` (Screen 3).
   - **Correct Screen 2 Title:** Screen 2 is titled `Duyệt hồ sơ ứng tuyển | ClubFlow` with no leftover "Create Recruitment Campaign DRAFT MODE" banner.
   - **Disjoint People:** Applicants (`Nguyễn Minh Anh`, `Lê Thu Hà`, `Phạm Quốc Bảo`, `Đỗ Đức Thắng`, `Võ Mai Linh`, `Bùi Quang Huy`, `Nguyễn Hoàng Phương Thảo Như Quỳnh`) and Interviewers (`Trần Thanh Tùng`, `Phan Minh Đức`, `Ngô Ngọc Yến`) do not overlap.
   - **No "Verified" Badges or Template Footer:** Removed all university verification claims and replaced the template footer with a single internal prototype status line.

## 5. Not Wired Yet
Because PA#2 is a static HTML/CSS prototype graded with JavaScript off, stateful actions are rendered as semantic `<button type="button" disabled>` controls with explanatory `title` attributes for later milestones:
- **Screen 1 (`index.html`):** `+ Thêm vị trí (mô phỏng)`, `Lưu nháp (mô phỏng)`, `Xem trước (mô phỏng)`.
- **Screen 2 (`review.html`):** `Áp dụng lọc (mô phỏng)`, `Xuất CSV (mô phỏng)`, and per-application `Shortlist Candidate (mô phỏng)` / `Reject (mô phỏng)` buttons.
- **Screen 3 (`interview.html`):** `Regenerate Schedule (mô phỏng)`, `Export Timetable (mô phỏng)`, per-row `Resolve` / `Edit` / `+ Assign Slot` buttons, `Save Changes (mô phỏng)`, and `Approve & Confirm Schedule (bị khóa)`.

## 6. CSS
- **Framework:** Plain CSS (`styles.css`), no external CSS framework.
- **Spacing Scale (`:root` custom properties):**
  - `--space-1`: `4px`
  - `--space-2`: `8px`
  - `--space-3`: `12px`
  - `--space-4`: `16px`
  - `--space-5`: `20px`
  - `--space-6`: `24px`
  - `--space-8`: `32px`
  - `--space-10`: `40px`
- **Breakpoints (Mobile-First):**
  - Base (`0px–767px`): Single-column layout designed for `360px` phones.
  - `@media (min-width: 768px)`: 2-column form/detail/resource grids, 3-column summary cards, 4-column stat cards for tablets (`768px`).
  - `@media (min-width: 1024px)`: Expanded shell padding (`32px`), 3-column position cards on `index.html`, and 2-column side-by-side table + drawer workspace on `review.html` for laptops (`1280px`).