# 🏘️ Village of prebuilt executables for multiple platforms

## [Releases](https://github.com/binarylandia/appville/releases)

## Build

```bash
./dev/cross/all <tool-name>
```

## What is this?

Cross-compiles command-line tools as portable, self-contained binaries for Linux, macOS, and Windows. No runtime dependencies required.

## Features

- Fully static linking (no shared library dependencies)
- Optimized builds (-O3, vectorization, loop unrolling)
- Architecture-tuned for modern CPUs
- Single-file deployment

## Use Cases

- Deploying tools to minimal containers (Alpine, scratch)
- Running on systems without package managers
- Air-gapped environments
- CI/CD pipelines with portable tooling

## Releases

Download from [GitHub Releases](https://github.com/binarylandia/appville/releases).

## Keywords

static binaries, prebuilt executables, portable binaries, statically linked, cross compile binaries, linux static binary, macos static binary, windows static binary, self-contained executable, no dependencies
