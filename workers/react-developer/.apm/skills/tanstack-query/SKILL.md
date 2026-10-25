---
name: tanstack-query
description: 'Use when writing or reviewing TanStack Query React integration, query keys, server-state caching, mutations, invalidation, cursor pagination, request cancellation, or OpenAPI query functions in MIEZ. Covers Query, not an AI chat client or agent execution.'
metadata:
  library: '@tanstack/react-query'
  reviewed-version: '5.104.1'
  reviewed-date: '2026-10-06'
---

# TanStack Query in MIEZ

## Resolve current guidance

1. Check the owning workspace manifest and exact resolved lockfile version.
   Approval is not installation; the reviewed version above is not a pin.
2. Inspect that release's static package metadata and any bundled `skills`
   documents. Read only relevant skills and their declared prerequisites.
   The reviewed Query/Query Core 5.104.1 tarballs contain no bundled skills.
3. If Context7 tools are available, resolve TanStack Query and request the
   installed version's React API for the task. Verify the result's version and
   source before using examples. Do not assume Context7 is configured or current.
4. Otherwise read the version-matched official guides and local declarations.
   The `/latest` pages below are discovery links, not proof of version parity.
   Do not install Intent, Context7 or packages merely to load documentation.

## Apply the owned boundary

- Keep Query providers, generated OpenAPI transport, authentication and API
  adapters in the host. Shared UI receives typed data/actions, not credentials
  or an application-wide Query client. Feature-local drafts stay React-owned.
- Scope keys by deployment, authenticated session, resource and effective
  filters. Share query options with Router loaders; do not create another cache.
- Translate non-2xx HTTP results into safe typed failures. A returned `error`
  record does not make Query reject a query. Preserve the request AbortSignal,
  response tokens and approved error codes without exposing provider text.
- Use explicit resource freshness and related mutation invalidation. Use cursor
  pages for bounded APIs; do not infer full counts or global sorting from a page.
- Keep MIEZ SSE observation separate. Reconcile live events and snapshots by
  identity and sequence so a late read cannot erase newer committed output.
- Never enable blind command retries or offline execution queues. Lost
  acknowledgements retain the same command/key; conflicts require fresh state.
- Stop subscriptions and clear private caches on logout/session expiry or a
  deployment change. Do not persist credentials or canonical transcripts by default.

## Verify the change

Test pending/error/empty/success, invalidation, cursor boundaries and cleanup.
For mutations, cover acknowledgement loss, conflict and retained user input.
When live events are involved, test stale snapshot/replay ordering. Run the
owning focused tests and required frontend gates; a build is not type evidence.

## Sources

- [Query overview](https://tanstack.com/query/latest/docs/framework/react/overview)
- [Important defaults](https://tanstack.com/query/latest/docs/framework/react/guides/important-defaults)
- [Query keys](https://tanstack.com/query/latest/docs/framework/react/guides/query-keys)
- [Query cancellation](https://tanstack.com/query/latest/docs/framework/react/guides/query-cancellation)
- [Reviewed package metadata](https://registry.npmjs.org/@tanstack%2Freact-query/5.104.1)
- [MIEZ stack and cache policy](../../../docs/change/frontend-stack.md)
- [Accepted chat-client boundary](../../../docs/snapshot/adr/0004-host-owned-chat-client.md)
