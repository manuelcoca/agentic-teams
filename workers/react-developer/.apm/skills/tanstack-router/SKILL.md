---
name: tanstack-router
description: 'Use when writing or reviewing TanStack Router React routes, search-parameter validation, loaders, preloading, authentication guards, navigation errors, or Query integration in the MIEZ production host. Does not authorize TanStack Start or another backend.'
metadata:
  library: '@tanstack/react-router'
  reviewed-version: '1.170.41'
  reviewed-date: '2026-10-06'
---

# TanStack Router in MIEZ

## Resolve current guidance

1. Check the owning workspace manifest and exact lockfile version. The reviewed
   version above is an observation, not an installed or approved package pin.
2. Inspect that release's static metadata and relevant bundled skills, if any.
   The reviewed React Router/Router Core 1.170.41 tarballs contain no bundled skills.
3. Use Context7 when its tools are available: resolve TanStack Router, request
   the installed version's React documentation, and check the returned source
   and version. Otherwise use official matching guides and local declarations.
   `/latest` is a discovery link, not proof that the installed API matches.
4. Do not install documentation tools, upgrade packages or add a server as a
  lookup side effect.

## Apply the owned boundary

- Put routing, authentication sessions and service adapters in `apps/chat-app`.
  Shared components and Agent features receive data/actions; do not make them
  import the production router or reach into another feature's state.
- Use routes for resource identity and validated shareable filters/tabs. Keep
  credentials, draft prompts, complete messages and unsaved source out of URLs.
- Reuse Query options/cache from loaders and preloading. Do not store a second
  long-lived resource copy in router state or fetch all workspace records at boot.
- Authentication guards guide navigation; Go remains the authorization boundary.
  Handle expired sessions safely, stop observations and clear private caches.
- Restore durable messages/runs from the backend on reload. Navigation detaches
  observation; it must not resubmit a prompt or silently cancel accepted work.
- Preserve accessible links, current-page semantics, focus and loading/error
  states. Keep the approved desktop navigation and mobile Chat/Notebook scope.
- Do not introduce TanStack Start, server functions, SSR or a TypeScript agent
  backend to solve a client-routing task. Keep existing React/Vite/UI conventions.

## Verify the change

Cover deep links, validated search state, back/forward, missing resources,
expired authentication, loader failures and repeated preloading with one cache.
Check keyboard/focus and narrow layouts. Run focused host tests and required
frontend gates; a Storybook fixture does not prove production authentication.

## Sources

- [Router documentation](https://tanstack.com/router/latest)
- [External data loading](https://tanstack.com/router/latest/docs/framework/react/guide/external-data-loading)
- [Search parameters](https://tanstack.com/router/latest/docs/framework/react/guide/search-params)
- [Authenticated routes](https://tanstack.com/router/latest/docs/framework/react/guide/authenticated-routes)
- [Reviewed package metadata](https://registry.npmjs.org/@tanstack%2Freact-router/1.170.41)
- [MIEZ stack and routing ownership](../../../docs/change/frontend-stack.md)
