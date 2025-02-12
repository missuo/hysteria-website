---
title: Changelog
hide:
  - navigation
---

## 2.2.1

- Added GeoIP & GeoSite auto update (`geoUpdateInterval` field under ACL, default is 1 week)
- Client now shows handshake information after connecting to the server, currently includes UDP forwarding availability & tx rate
- Changed the basis for bandwidth conversion (Kbps/Mbps/Gbps/Tbps) from 1024 to 1000
- Added RISC-V (riscv64) support
- Updated quic-go to v0.40.0

## 2.2.0

- Added GeoSite support to ACL (both GeoIP and GeoSite now use the v2ray "dat" format database)
- Added support for non-English domains (IDN) to ACL (e.g. `v6_only(战狼*.中国)`)
- Added WebSocket support to masquerade proxy mode
- Added secret-based authentication to Traffic Stats API
- Fixed compatibility issues on certain Linux systems

## 2.1.1

> This release contains important fixes and we strongly encourage everyone to upgrade.

- Fixed a bug where a specially crafted UDP message packet could cause the server to crash
- Fixed compatibility issues on FreeBSD
- Windows users can now launch directly by double-clicking the exe file

## 2.1.0

- Fixed a memory leak in BBR
- Minor tweaks to Brutal congestion control
- Added string mode to masquerade
- Added HTTP/HTTPS proxy outbound

## 2.0.4

- Optimized and fixed some issues in Brutal CC
- Fixed problem where BBR could freeze the connection and cause CPU usage to spike under certain conditions
- Fixed two race condition issues
- Added `HYSTERIA_BRUTAL_DEBUG` environment variable. When enabled, it prints information like current RTT, packet loss, MTU, etc.

## 2.0.3

> This release contains important fixes and we strongly encourage everyone to upgrade.

- **[Important]** Fixed the problem where when using BBR (either the client doesn't set bandwidth or the server has `ignoreClientBandwidth` enabled), due to a bug in the BBR implementation, it could not accurately determine the bandwidth and send packets much faster than the limit.
- Fixed the problem where ZeroSSL couldn't acquire certificates due to missing EAB.

## 2.0.2

- Fixed connection issues on some devices due to lack of GSO support
- Added HTTP/HTTPS (TCP) masquerade servers
- Added Android builds

## 2.0.1

- Added TCP redirect mode
- Log HTTP requests handled by masquerade (debug level)
- Added environment variable `HYSTERIA_ACME_DIR` to control ACME data directory location

## 2.0.0

This is the first stable release of Hysteria 2. It's almost a complete rewrite of the original Hysteria, with a new protocol, new features, and various improvements.
