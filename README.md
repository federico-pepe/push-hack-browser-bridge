# Browser Bridge (retired)

**This hack is retired.** The PushHack Remote Script replaces it. PushHack ships with
[Push Hack](https://github.com/federico-pepe/ableton-push-hack), so you install nothing from the
catalog.

PushHack does everything Browser Bridge did: it loads presets, samples, plugins and URIs, lists
plugins, and reports tempo, scale and the transport. It answers the old text commands on
`127.0.0.1:7704`, so push-manager and any hack that used Browser Bridge keep working.

## What to do if you have Browser Bridge installed

1. Update Push Hack to a release that includes PushHack (Push Manager shows a yellow bar when
   one exists), or run `./scripts/install.sh --hack push-manager` from the Push Hack repo.
2. In Live, choose **PushHack** in a control-surface slot (Input and Output: None). Restart Live.
3. Open the **System** page in Push Manager. The PushHack card lists **PushHackBrowser**. Press
   **Remove**, clear its slot in Live, and restart Live.
4. Uninstall Browser Bridge from the Push Hack Catalog if it is still listed.

Both scripts cannot run together: they use the same port, 7704.

## History

The last version, 0.4.0, is tag `v0.4.0`. It had the script `PushHackBrowser` with these commands:
`load`, `load_uri`, `load_plugin`, `load_sample`, `list_plugins`, `dump`, `get_tempo`,
`get_beat`, `get_playing`, `get_scale`, `get_listen`, `listen_on`, `listen_off`, `play`, `stop`.
The code is now in `remote-script/PushHack/` in the Push Hack repo.
