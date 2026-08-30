# HUNC

The only executor tester that actually tests real functions.

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/CXamigos/HUNC/main/HUNC.lua"))()
```

### Why HUNC is original

Every other tester just checks if a function exists. HUNC checks if it actually works.

- **Real calls, real effects** — 224 checks, each one calls the function and verifies the result. `hookfunction` hooks and restores, `crypt.base64` checks exact vectors and roundtrips, `filesystem` does write/read/delete, `debug` checks real protos. A stub like `function() return nil end` passes other testers but fails HUNC.
- **Unfakeable** — every check requires `iscclosure`/`isexecutorclosure` + correct return value + state restore where needed. You can't fake with `newcclosure` stubs.
- **Executor reality** — tested on live executors, not Studio. No `Source` tricks, no hanging `messagebox` (10s timeout), no false fails.
- **One file, VM protected** — single `HUNC.lua` with randomized VM (per-chunk keys, masked opcodes, checksum). Impossible to dump and rehost as fake.

### What you get

Modern BrewPage report — success rate gauge, searchable function grid, hover docs, executor + type + time taken. Shareable link, Discord embed ready as HUNC Ranking.

Just execute the loader and copy the `brewpage.app/public/...` link.

---
© 2026 CXamigos — HUNC
