---
name: quindici-right-feeling-ui
description: Critical UI/UX design laws, mobile viewport budgets, spacing, anti-patterns, and component hierarchy. MUST be used whenever generating or modifying React/Next.js pages, UI components, Tailwind styles, or empty states.
globs:
  - "app/**/*.{tsx,jsx,css}"
  - "components/**/*.{tsx,jsx,css}"
  - "src/**/*.{tsx,jsx,css}"
---

# UI/UX Philosophy & Interaction Heuristics

Apply these architectural laws when creating or reviewing components, views, and layouts to ensure spatial harmony, intentional hierarchy, and zero cognitive clutter.

---

## 1. Interaction Archetype Alignment

Before generating markup, classify the view into one primary archetype. Never mix patterns:

* **The Visceral Canvas (Consumer, Media, Social, Camera):**
  * *Focus:* Immersion, high visual payoff, thumb-driven interaction.
  * *Rules:* Edge-to-edge media, borderless containers, subtle blur scrims, bottom-weighted primary triggers. Never render data tables, monospace debug text, or nested card borders.
* **The Operational Console (B2B, Dashboards, Internal Tools):**
  * *Focus:* High information density, scannability, multi-item manipulation.
  * *Rules:* Explicit tabular layouts, clear column headers, monospace timestamps, status badges, side/top navigation.
* **The Focused Tunnel (Modals, Onboarding, Checkout, Forms):**
  * *Focus:* Linear task completion with zero escape routes.
  * *Rules:* Single visible primary CTA, minimal metadata overhead, non-competing secondary actions.

---

## 2. Viewport Overhead Budget

Metadata is context; content is the product.

* **Mobile 30% Ceiling:** On mobile viewports (`< 640px`), combined header elements (titles, stats, badges, avatar rows, tabs) must never exceed 30% of the visible viewport height before primary content renders.
* **Inline Consolidation:** When showing $\ge 3$ pieces of metadata, merge them into a single dot-separated flex row (`Title · Subtext · Status`) rather than stacking full-width pills or cards.
* **Scroll-Driven Compression:** If rich headers are necessary, collapse them into a compact sticky bar ($h \le 56\text{px}$) upon scroll.

---

## 3. The Law of the Single Anchor

Every screen must have exactly one visual center of gravity for action and one primary home for any metric.

* **Metric De-duplication:** An item of state (e.g., remaining count, balance, total items) must appear in **one** UI location only. Never echo the same count across top navigation, stats rows, avatar badges, and buttons simultaneously.
* **Zero CTA Competition:** Never render an in-page action button that duplicates a fixed floating action button (FAB) or bottom navigation anchor.
* **Directional Empty States:** When a list is empty, write copy and indicators directing attention toward the persistent primary trigger rather than embedding a duplicate button inside an empty-state card.

---

## 4. Spatial Physics & Dock Clearance

Floating interfaces permanently alter the scroll container. Never float elements unanchored.

* **Safe-Area Scroll Clearance:** Every scroll container positioned beneath a floating button or navigation bar must enforce bottom clearance:
  $$\text{Bottom Padding} = \text{Height of Dock} + \text{Floating Offset} + 24\text{px}$$
* **Background Isolation (Scrims):** Interactive elements floating above dynamic content must sit over a backdrop blur or gradient scrim (`backdrop-blur-md bg-gradient-to-t from-background/90`). Elements must never float directly over raw, unshaded user content.
* **No Orphan Floating Elements:** Do not scatter single-letter or isolated circular buttons near screen edges. Group auxiliary actions into a unified bar, integrate them symmetrically, or move them into contextual menus.

---

## 5. Surface Hygiene & State Coherence

* **De-boxing (Border Fatigue):** Eliminate card-in-a-card nesting. If a container already possesses background contrast or padding, do not wrap child elements in bordered outlines. Use whitespace and typography contrast for separation.
* **Ghost Control Suppression:** If a collection is empty (`items.length === 0`), dynamically disable or omit secondary view controls (e.g., grid/list toggles, sorting dropdowns).
* **Lexicon Locking:** Enforce strict semantic consistency across all labels in a flow. Pick one domain term (e.g., choose between *Shots* vs. *Photos*, *Credits* vs. *Tokens*) and use it identically across headers, counts, buttons, and zero-states.
* **Default-Off Inactive Badges:** Do not render empty, zeroed-out reaction counters or grayed-out action icons on list items. Display content first; reveal secondary counters only when active ($>0$) or focused.

---

## Pre-Flight Generation Checklist

Verify every generated component against this matrix:

1. [ ] **Archetype:** Does this design avoid looking like an administrative dashboard when it should feel consumer/social?
2. [ ] **Density:** Does primary content appear above the fold on mobile?
3. [ ] **Single Metric:** Is any number, counter, or status pill repeated on this screen?
4. [ ] **Anchor Hierarchy:** Does the empty state compete with persistent navigation or floating actions?
5. [ ] **Clearance:** Can the final scrollable item scroll completely past any floating dock or scrim?
6. [ ] **Consistency:** Are domain terms identical across every badge, label, and copy block?