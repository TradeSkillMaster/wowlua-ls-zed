# wowlua-ls Zed extension

A `wasm32-wasip2` cdylib (`zed_extension_api`) that resolves a `wowlua_ls` binary and hands the command to Zed. The language server itself lives in [TradeSkillMaster/wowlua-ls](https://github.com/TradeSkillMaster/wowlua-ls).

## Release asset contract

The extension downloads the server's standalone release asset `wowlua_ls-<target>[.exe]`. The server repo's `tests/zed_extension.rs` pins the targets `release_asset_name` maps to, so a change to that mapping needs a matching change there.

## Publishing

Extensions are published from [zed-industries/extensions](https://github.com/zed-industries/extensions), which pins this repo as the `extensions/wowlua-ls` submodule:

1. Bump `version` in `extension.toml`. It is the extension's own version, independent of the server's, since the server binary is resolved at runtime.
2. Open a PR against zed-industries/extensions that moves the submodule to the new commit and sets the `[wowlua-ls]` entry's `version` in `extensions.toml` to match.
