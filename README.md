# PlatformIO Home patch for code-server

Backup of a working patch for:

- PlatformIO IDE extension 3.3.4
- code-server 1.133.0
- PlatformIO Home running behind code-server proxy

## Problem

PlatformIO Home normally generates an iframe URL pointing directly to
the PIO Home server address, which does not work correctly when running
inside code-server.

## Patch

The extension was modified so that the PIO Home iframe is routed through:

https://armbian.local:8080/proxy/<PIO_PORT>/session/...

The PIO Home port is detected dynamically from the generated URL.

## Required setting

platformio-ide.pioHomeServerHttpHost = 0.0.0.0
platformio-ide.pioHomeIframeUrl = https://armbian.local:8080

## Important

extension.js is a built/minified extension file. This repository is a
personal backup of the working patched installation, not the original
PlatformIO source tree.
