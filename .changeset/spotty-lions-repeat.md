---
"partyserver": patch
---

docs(partyserver): deprecate the `setName()` name-bootstrap role and the `x-partykit-room` header fallback; document the native `ctx.id.name` availability matrix

`ctx.id.name` has been populated natively inside Durable Objects addressed via `idFromName()`/`getByName()` since 2026-03-15 (https://developers.cloudflare.com/changelog/post/2026-03-15-durable-object-id-name/), so establishing a name via `setName()` for raw-ID DOs (`idFromString()`/`newUniqueId()`) and via the `x-partykit-room` header are both deprecated and will be removed/hardened in a future major version. `setName()` itself stays — it remains the onStart-synchronization + props-delivery channel used by `getServerByName()`. No runtime behavior changes; the `__ps_name` fallback writes and reads are retained.
