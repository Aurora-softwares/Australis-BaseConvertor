# Australis Base Convertor

## Current status

The current source prints `Hello, World!`; it does not convert numeric bases.

`BaseConvertor.hyproj` builds `base-convertor.exec`. The Australis OS aggregate includes
this project and installs the executable at `/System/Bin/base-convertor.exec` in the read-only
HyFS 2 boot image. Run it by its bare name `/System/Bin/` through the current
recovery shell's `PATH`, or use `run /System/Bin/base-convertor.exec`.

## Planned direction

Implement a bounded argument-driven base conversion utility after the Stage 2 command and error-result APIs are stable.

Build this checkout with:

```bash
mkdir -p build
hy build BaseConvertor.hyproj -o build/base-convertor.exec
```

AUEX `.exec` files currently run in the checked interpreter. Native ring-3
processes and a normal userland shell are later milestones. The boot root is
read-only; writable application data belongs on the separate `/data` volume.
The OS-level build, supported APIs, and packaging rules are described in the
Australis OS `applications/README.md`. This README describes this project's
actual source rather than treating its filename as proof of a finished feature.
