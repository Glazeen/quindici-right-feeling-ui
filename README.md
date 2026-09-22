# Quindici Right Feeling UI

> Critical UI/UX design laws, mobile viewport budgets, spacing rules, anti-patterns, and component hierarchy for AI coding agents.

[![skills.sh](https://skills.sh/b/alfonsocannavale/quindici-right-feeling-ui)](https://skills.sh/alfonsocannavale/quindici-right-feeling-ui)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Designed for use with modern AI coding agents (**Claude Code**, **Cursor**, **Codex**, **Windsurf**, **GitHub Copilot**, and 30+ others) via [skills.sh](https://www.skills.sh/).

---

## ⚡ Installation

Install into your project or globally across all your projects with one command:

### Quick Install (Project Level)

```bash
npx skills add alfonsocannavale/quindici-right-feeling-ui
```

### Global Install (Available Everywhere)

```bash
npx skills add alfonsocannavale/quindici-right-feeling-ui -g
```

### Target Specific Agents

```bash
# Claude Code
npx skills add alfonsocannavale/quindici-right-feeling-ui -a claude-code

# Cursor
npx skills add alfonsocannavale/quindici-right-feeling-ui -a cursor

# Codex
npx skills add alfonsocannavale/quindici-right-feeling-ui -a codex
```

---

## 🎯 What This Skill Does

AI agents tend to default to generic, cluttered dashboards with nested borders, duplicated counters, and bloated mobile headers. **Quindici Right Feeling UI** injects strict spatial and interaction heuristics directly into the agent's context whenever generating or modifying frontend code (React, Next.js, Tailwind CSS):

### 1. Interaction Archetype Alignment
Forces the agent to classify views into one distinct pattern—never mixing consumer paradigms with enterprise consoles:
* **The Visceral Canvas:** Edge-to-edge media, borderless containers, thumb-driven interaction.
* **The Operational Console:** High information density, scannability, explicit tabular data.
* **The Focused Tunnel:** Single clear primary CTA, zero escape routes.

### 2. Viewport Overhead Budget
* **Mobile 30% Ceiling:** Combined header elements must never consume more than 30% of the mobile viewport (`< 640px`) before primary content renders.
* **Inline Metadata Consolidation:** Merges 3+ metadata items into a single dot-separated row (`Title · Subtext · Status`) rather than stacked pills.
* **Scroll Compression:** Rich headers collapse into compact sticky bars upon scroll.

### 3. The Law of the Single Anchor
* **Metric De-duplication:** Any metric or state count appears in exactly **one** place on screen.
* **Zero CTA Competition:** In-page buttons never duplicate fixed floating actions or navigation docks.
* **Directional Empty States:** Empty states guide attention to primary creation triggers instead of spawning duplicate buttons.

### 4. Spatial Physics & Dock Clearance
* **Safe-Area Scroll Clearance:** Mandates bottom padding so the final scroll item clears floating docks and nav bars:
  $$\text{Bottom Padding} = \text{Height of Dock} + \text{Floating Offset} + 24\text{px}$$
* **Background Isolation (Scrims):** Floating elements always sit over a backdrop blur or gradient scrim—never directly over raw content.
* **No Orphan Floating Buttons:** No isolated floating circles near screen edges.

### 5. Surface Hygiene & State Coherence
* **De-boxing (Border Fatigue):** Eliminates card-in-a-card nesting; relies on whitespace and typographic contrast.
* **Ghost Control Suppression:** Automatically hides or disables filters and sort menus when lists are empty.
* **Lexicon Locking:** Strictly enforces uniform terminology across badges, headers, and buttons.
* **Default-Off Badges:** Inactive reaction counters or zeroed-out indicators are hidden until active.

---

## 📋 Pre-Flight Checklist

The agent verifies its output against this checklist before presenting code:

- [ ] **Archetype:** Does the design avoid looking like a generic dashboard when consumer/social?
- [ ] **Density:** Does primary content appear above the fold on mobile?
- [ ] **Single Metric:** Is any number, counter, or status pill repeated on this screen?
- [ ] **Anchor Hierarchy:** Does the empty state compete with persistent navigation or floating actions?
- [ ] **Clearance:** Can the final scrollable item scroll completely past any floating dock or scrim?
- [ ] **Consistency:** Are domain terms identical across every badge, label, and copy block?

---

## 📄 License

[MIT](LICENSE) © Alfonso Cannavale
