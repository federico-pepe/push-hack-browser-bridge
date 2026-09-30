# CLAUDE.md

Guidance for Claude Code in this repository.

## Push family context

Shared facts for all Push repos (repo map, git identity, `core/` pinning, cross-repo hardware facts):

@~/.claude/push-family.md

## Project

`browser-bridge` — Ableton Live MIDI Remote Script (`PushHackBrowser`, in
`remote-script/`) that loads `.adv`/`.adg` presets through Live's browser
API. push-manager's `live_bridge.go` talks to it over TCP `127.0.0.1:7704`
(fixed port, inside the framework's reserved 7701–7710 block). A catalog hack
for [ableton-push-hack](https://github.com/federico-pepe/ableton-push-hack).
Full description and on-device activation: [README.md](README.md).

## Rules

- No Go code and no `core` dependency. The wire protocol with push-manager
  (`load:<root>:<name>`, play/stop/tempo/beat queries) must stay in sync with
  `ableton-push-hack/hacks/push-manager/src/live_bridge.go`.
- Needs a one-time manual activation in Live's Control Surface settings.
- Restart Live after changing the Remote Script.
- Release: bump `hack.json` `version`, push a matching `vX.Y.Z` tag;
  `.github/workflows/release.yml` packages it and writes `release.json`.
