---
name: tanstack-markdown
description: 'Use when integrating or reviewing TanStack Markdown React rendering, streamed AI reply formatting, incomplete code fences, component overrides, parser options, link/image security, highlighting, or GFM compatibility in MIEZ. Does not require TanStack AI Client.'
metadata:
  library: '@tanstack/markdown'
  reviewed-version: '1.0.0'
  reviewed-date: '2026-10-06'
---

# TanStack Markdown in MIEZ

## Resolve current guidance

1. Check the owning workspace manifest and exact installed Markdown version.
   The reviewed version above is not an installed or approved package pin.
2. Prefer that release's bundled static skills. The reviewed 1.0.0 package
   includes `skills/react-rendering/SKILL.md`, its `render-markdown` prerequisite
   at `skills/render-markdown/SKILL.md`, and
   `skills/production-pipelines/SKILL.md` for trust/compatibility/bundle checks.
   Load only needed references. Do not load Octane or documentation-site skills
   for an ordinary React reply; custom extensions need a demonstrated use case.
3. Use Context7 when available: resolve TanStack Markdown, request the installed
   version's React and streaming API, and check source/version coverage. Otherwise
   use matching official docs and local declarations. `/latest` is not a pin.
4. Keep Markdown independent of the rejected AI client and do not force
  transitive overrides.

## Apply the owned boundary

- Use `@tanstack/markdown/react` and the streaming extension for reply display.
  The host supplies accumulated text; the renderer does not open subscriptions,
  call models, execute code or decide whether a backend run has finished.
- Keep raw HTML disabled, frontmatter disabled and heading IDs disabled for
  streamed replies. Apply the existing owned URL and image policy through
  component overrides; do not enable remote images or executable URL protocols.
- Reuse existing semantic theme, code/table overflow regions and accessible
  controls. Highlighting is independently optional; require escaped source
  before inserting a highlighter's HTML. Do not enable diagrams, math or
  interactive extensions merely because a renderer supports them.
- Preserve exact canonical notebook source and existing saved-content/GFM
  rendering until compatibility passes. The selected package has a narrower
  syntax profile; do not silently drop imported formatting or rewrite content.
- The streaming profile reparses the complete accumulated string per update.
  Batch excessive paints when measured; do not drop committed text or turn a
  replacement message snapshot into an appended delta. Do not assume constant
  token cost or finished content because the network subscription ended.
- Keep library-specific rendering inside the owned Agent feature. Do not add
  TanStack AI Client, provider SDKs or another component kit for Markdown.

## Verify the change

Test every-character boundaries across headings, emphasis, links, lists,
tables and incomplete code fences. Cover malicious HTML/URLs/code, replacement
snapshots, long replies, keyboard overflow and light/dark/mobile rendering.
Compare existing saved GFM fixtures before migrating that path. Change stories
with reusable UI; run focused tests, required frontend gates and built consumption.

## Sources

- [AI streaming guide](https://tanstack.com/markdown/latest/docs/guides/ai-streaming)
- [React rendering](https://tanstack.com/markdown/latest/docs/guides/react)
- [Syntax profile](https://tanstack.com/markdown/latest/docs/core-concepts/syntax-profile)
- [Security](https://tanstack.com/markdown/latest/docs/core-concepts/security)
- [Reviewed package and bundled skills](https://registry.npmjs.org/@tanstack%2Fmarkdown/1.0.0)
- [Accepted independent renderer direction](../../../docs/snapshot/adr/0004-host-owned-chat-client.md)
- [Existing owned renderer](../../../ui/src/agent/markdown.tsx)
