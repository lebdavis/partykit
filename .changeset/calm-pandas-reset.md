---
"y-partyserver": minor
---

Add `resetDocument()` for replacing an empty room's in-memory Yjs document
without restarting its Durable Object. Require PartyServer 0.5.4 or newer so
normal client closes complete their WebSocket handshake before the final-peer
boundary is evaluated.
