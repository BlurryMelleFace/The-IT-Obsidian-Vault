# Task: Add a “Break Link” button to the Detail View — Text Grid

## Objective
Implement a new **“Break Link”** action button in the **Detail View → Text Grid**, positioned **next to the existing Accept (✔) and Reject (✖) icons** in the **Review** column. This button must appear **only** in the Detail View’s Text Grid (not in other grids or views).

## Context
- Two reference images are provided:  
  1) The full **Details** page, and  
  2) The current **Review** column UI.  
- The project uses **ix-icons**; the new button must use the **`link-break`** icon.

## Requirements
- **Scope:** Add the button **only** to rows rendered in the **Detail View’s Text Grid**. Do **not** affect other grids, views, or shared components.
- **Placement:** In the **Review** column, place the new **Break Link** icon **immediately next to** the Accept and Reject icons, following the current spacing and order conventions.
- **Icon & Labeling:** Use **ix-icons `link-break`**; provide an accessible **aria-label** and tooltip (e.g., “Break link”).
- **Behavior:** Trigger the existing unlink/disassociate flow for the selected row (or create a clearly named handler consistent with existing patterns if none exists).
- **Visual Consistency:** Match current size, padding, hover/focus states, and disabled/active styles of peer icons.
- **Guardrails:** Ensure the button renders **only** when the row is in a state where breaking a link is valid (mirror existing enable/disable logic patterns).

## Repository Alignment
Before making changes, **analyze the repository** (layout, modules, shared UI utilities, state management, event buses, testing setup, lint rules). Then:
- **Follow established patterns** for component structure, state, and event handling.
- **Reuse existing utilities/components** (e.g., icon wrappers, button factories, cell renderers, permission/feature guards) instead of duplicating logic.
- **Name APIs and handlers consistently** (prefixes, suffixes, and folder placement).
- **Keep code style and formatting** compliant with linters/formatters and existing conventions.

## Implementation Notes (concise)
- Add the icon to the **Text Grid’s Review column cell renderer** used **only** in the Detail View.
- Wire the click handler to the **row-scoped unlink/disassociate action** (respecting async/confirm patterns if present).
- Respect **feature flags/permissions** if the repo uses them.
- Ensure **no changes** propagate to other grids (audit shared renderers/selectors before editing).

## Acceptance Criteria
- The **Break Link** icon appears **only** in the Detail View’s **Text Grid → Review** column, next to Accept/Reject.
- Uses **ix-icons `link-break`**, with proper **tooltip** and **aria-label**.
- Correctly triggers the intended unlink/disassociate behavior for the row.
- **No regressions** to Accept/Reject behavior or layout.
- **Tests updated/added** (unit and, if applicable, integration/E2E).
- **Build, lint, and tests pass**; visual diffs acceptable; PR follows template.
- Code is **readable**, **documented** (inline comments where helpful), and aligned with repository conventions.

## Deliverables
- PR with scoped changes (components, handlers, styles, tests).
- Short implementation notes summarizing files touched, rationale, and any follow-ups.

---

**Assets:** Reference images (Details page + Review column).  
**Icon:** `ix-icons` → `link-break`.
