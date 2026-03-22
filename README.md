# luci-app-easymesh

## Package Description

LuCI support for EasyMesh. A LuCI-based configuration interface for Batman-Adv mesh networking with 802.11s support, enabling seamless wireless/wired backhaul mesh networks on OpenWrt.

## Features

- Batman-Adv mesh network configuration
- 802.11s wireless mesh support
- Wired/wireless backhaul support
- AP mode with custom IP configuration
- K/V/R (802.11k/v/r) support for optimized roaming
- Integration with DAWN for dynamic roaming decisions

## Dependencies

- `kmod-cfg80211`
- `kmod-batman-adv`
- `batctl-default`
- `wpad-mesh-openssl`
- `dawn`

## Hardware Requirements

- Wireless card supporting 802.11s mesh (e.g., MediaTek MT76, Qualcomm Atheros, etc.)
- Batman-Adv kernel module loaded

## Normalized Package Path

This is a normalized and fixed version of the original `kenzok8/openwrt-packages` package, following standard OpenWrt LuCI app layout.

## Bugs Fixed

- Syntax errors in CBI model `detect_Node()` function (unbalanced parentheses)
- Global variable leaks in CBI model (Lua globals `v`, `s`, `apRadio`, `enable`)
- Missing `nixio` require in controller
- `nixio.fs.access` call without requiring `nixio.fs` in controller
- Missing `local` declarations in init script shell functions
- Unquoted variables in shell scripts
- Fragile `grep` command parsing replaced with robust `uci show` parsing
- `add_wifi_mesh` function refactored to accept `apall` as parameter instead of relying on global scope
- `uci commit` calls batched appropriately
- `batctl n` command output parsing fixed with proper `io.popen` instead of `util.execi`
- `tail -n +2` consistent with header skipping logic
- `encryption` string comparison fixed from numeric to string
- Duplicate `po/zh-cn` directory removed (consolidated to `po/zh_Hans`)
- `po/zh-cn` directory removed (duplicate of `po/zh_Hans`)
- `IPKG_INSTROOT` check added to uci-defaults script
- Makefile missing `PKG_MAINTAINER` and `PKG_RELEASE` fields added

## Original Author

dz &lt;dingzhong110@gmail.com&gt;
