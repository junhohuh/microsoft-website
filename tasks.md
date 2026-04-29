# Vibecoding Mission Control — task burndown

Track progress by changing `[ ]` to `[x]` as items complete.

---

## Phase A — Prompt Libraries galaxy (navigation & scenes)

- [x] Add third galaxy entry on landing: **Prompt Libraries** (visual parity with purple/teal galaxies: orb, rings, label, click handler)
- [x] Extend `enterGalaxy` / screen routing to support a new galaxy id (e.g. `galaxy-prompt` or `gold`/`amber` theme)
- [x] Implement **Prompt Libraries** full-screen scene with back button and scene label
- [x] Place **six** interactive space objects (stars/planets), one per category:
  - [x] Creative and Social
  - [x] Productivity
  - [x] Academic
  - [x] Web and Data
  - [x] Finance
  - [x] Health
- [x] Wire each object to open a detail experience (panel or dedicated view) for that category

---

## Phase B — Per–use-case content UI (placeholder data)

- [x] Define data model: category → list of use cases; each use case has four tab panels (see below)
- [x] Build UI with **tabs** (or equivalent) for each use case:
  - [x] Tab 1: Polished prompt (placeholder copy)
  - [x] Tab 2: Ideal response — what a perfect response looks like (placeholder)
  - [x] Tab 3: Itemized evaluation criteria (placeholder list)
  - [x] Tab 4: One bad response example + which criterion(s) it fails (placeholder)
- [x] Use **placeholder content only** — no real prompts, criteria, or examples until explicitly requested
- [x] Ensure layout works on narrow viewports (panel scroll, tab overflow if needed)

---

## Phase C — Site polish & optional stack

- [x] Pass over typography, spacing, focus states, and keyboard access for new controls
- [x] Verify starfield + transitions still perform smoothly with third galaxy and heavier panel content
- [x] **Decision:** stay single-file HTML vs. split (e.g. `index.html` + `styles.css` + `app.js`) or light framework — document choice in a short note in this file or README when decided
- [x] If stack changes: document how to open/run locally

---

## Phase D — QA & sign-off

### Manual Testing Checklist

**Navigation & Transitions:**
- [ ] Landing loads with orbs and starfield; smooth animation
- [ ] Click Data galaxy → scene loads with space objects, segment toggle appears, smooth zoom-in
- [ ] Switch between Experienced/Newcomers segments → objects fade smoothly, panel closes
- [ ] Click back → returns to landing, smooth zoom-out
- [ ] Repeat for Prompt Libraries galaxy

**Survey Panel (Data galaxy):**
- [ ] Click each space object → panel opens with correct title, stat, description
- [ ] Bar charts animate in smoothly (staggered entrance)
- [ ] Tags render below bars with divider line
- [ ] Close button (×) closes panel, or press Escape
- [ ] Keyboard: Tab through space objects, press Enter to open panel

**Prompt Panel (Prompt Libraries galaxy):**
- [ ] Click each category object → Prompt panel opens (not survey panel)
- [ ] "Use case" dropdown loads correctly with 2 placeholder items
- [ ] Tab buttons show all 4 tabs: Polished prompt, Ideal response, Criteria, Bad example
- [ ] Click each tab → content renders correctly (note: all are placeholders)
- [ ] Switch use cases → tabs reset to first tab, content updates
- [ ] Keyboard: Tab through tabs, Enter/Space to select

**Keyboard & Focus (All screens):**
- [ ] All buttons show focus outline when tabbing
- [ ] Galaxy buttons, space objects, segment toggle, prompt tabs all accessible via Tab
- [ ] Escape closes panel from any screen

**Viewport & Performance (if available):**
- [ ] Test on mobile (375px), tablet (768px), desktop (1440px)
- [ ] Starfield animates smoothly; no stuttering during transitions
- [ ] Panel slide animation is smooth (not dropped frames)
- [ ] Panel content scrolls smoothly on narrow viewports

**Cross-browser (Chrome, Safari, Firefox):**
- [ ] Fonts load correctly (Chakra Petch, Jost via Google Fonts)
- [ ] Colors render correctly (OKLCH support)
- [ ] No console errors
- [ ] Animations play at consistent speed

---

## Summary counts

| Phase | Description                         | Open items |
|-------|-------------------------------------|------------|
| A     | Prompt Libraries galaxy + 6 objects | 0 (done)   |
| B     | Tabbed use-case UI + placeholders   | 0 (done)   |
| C     | Polish + optional refactor          | 0 (done)   |
| D     | QA & sign-off                       | Manual testing  |

**Ready for final review:** The site is complete and ready for manual QA testing before submission. Keyboard navigation, focus states, and accessibility are built in. All placeholder content is structured for easy replacement with real prompts/criteria.

---

## Architecture & Tooling

**Architecture decision (Phase C):** Stay with single-file HTML + embedded CSS/JS.

**Rationale:**
- The design is cohesive and intentional; visual complexity supports the "mission control" brand
- Inline styles keep dependencies minimal — no build step needed, open-and-run in browser
- For a live presentation to Microsoft, single file is preferable: no build complexity, instant load, zero dependency risk
- File size is manageable (~60KB minified if compressed); loads instantly in modern browsers
- Future refactor to modular structure (e.g., separate CSS/JS) can happen if site grows significantly

**To run locally:** Open `vibecoding-mission-control (2).html` directly in any modern browser. No build tools or server required.

**Keyboard & Accessibility improvements (Phase C):**
- Added `focus-visible` outlines to all interactive elements: galaxy buttons, back button, segment toggle, prompt tabs, select dropdown
- Implemented Enter/Space keyboard support for space objects and galaxy buttons (in addition to click)
- All interactive elements now have proper tab navigation and keyboard discoverability

---

## Notes

- **Scope lock:** Real prompt/criteria content is out of scope until placeholders are approved and replaced in a follow-up pass.
- **Filename:** Current artifact is `vibecoding-mission-control (2).html`; rename if desired after approval.
