---
name: tanstack-table
description: 'Use when building or reviewing owned TanStack Table React components, typed columns, row IDs, sorting, filtering, cursor pagination, selection, controlled state, or v8-to-v9 migration in MIEZ. Covers headless table behavior composed with existing Radix primitives.'
metadata:
  library: '@tanstack/react-table'
  reviewed-version: '9.2.6'
  reviewed-date: '2026-10-06'
---

# TanStack Table in MIEZ

## Resolve current guidance

1. Check the owning workspace's exact React Table and Table Core versions.
   Table v9 differs from common v8 examples; the reviewed version is not a pin.
2. Prefer the installed release's bundled static skills. The reviewed 9.2.6
   packages include React `skills/getting-started/SKILL.md` and
   `skills/table-state/SKILL.md`; Core includes `skills/core/SKILL.md`,
   `skills/table-state/SKILL.md` and `skills/table-features/SKILL.md`.
   Load the task-relevant skill, its declared prerequisites and needed references.
   Use `skills/migrate-v8-to-v9/SKILL.md` only for an actual migration.
3. If Context7 is available, resolve TanStack Table for the installed major,
   request the relevant React/core API, and verify the version/source. Otherwise
   use matching official docs and local declarations. Do not mix v8/v9 APIs.
4. Do not copy every upstream skill or install a package simply to retrieve
  documentation.

## Apply the owned boundary

- Build table markup/compositions in `ui` with existing Button, Input, Checkbox,
  DropdownMenu, Select, Skeleton, Tooltip and field primitives. Keep Radix,
  Geist, semantic tokens and the exact pastel-blue primary; add no other UI kit.
- Features own row types, column definitions, permissions, selection meaning
  and mutation handlers. Shared tables must not fetch records, own credentials
  or branch on feature names. Use composition rather than a universal grid.
- Use stable resource IDs, explicit state ownership and typed column metadata.
  An internal Table Store dependency is not a new product-wide state store.
- Remote lists use only backend-supported sorting/filtering and manual cursor
  pagination. A page is not the full dataset, global sort or authoritative total.
  Do not invent numbered pages or full-dataset selection from loaded rows.
- Keep semantic headers, sort announcements, accessible icon actions and focus
  when rows change. Define long-cell/mobile overflow and empty/loading/error
  states. Offer keyboard resizing or another non-drag control when resizing exists.
- Keep static Markdown tables read-only and semantic. Add Virtual only after
  measurement, with focus, variable-height and assistive-technology checks.
- Offline canvases may use qualified owned table exports with local data.
  Installing Table does not extend the compiler/module map or grant network access.

## Verify the change

Change reusable UI and its composition stories together. Test sorting,
selection, controlled state, cursor boundaries and removed rows. Check keyboard,
long content, mobile, light/dark and a different reference theme. Run focused
tests, required frontend gates and built-consumer checks, not only source aliases.

## Sources

- [Table overview](https://tanstack.com/table/latest/docs/overview)
- [React table state](https://tanstack.com/table/latest/docs/framework/react/guide/table-state)
- [Reviewed React package and bundled skills](https://registry.npmjs.org/@tanstack%2Freact-table/9.2.6)
- [Reviewed Core package and bundled skills](https://registry.npmjs.org/@tanstack%2Ftable-core/9.2.6)
- [MIEZ table and canvas boundaries](../../../docs/change/frontend-stack.md)
