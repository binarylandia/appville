# 🏘️ Village of prebuilt executables for multiple platforms

## [Releases](https://github.com/binarylandia/appville/releases)

## Build

```bash
./dev/cross/all <tool-name>
```

## What is this?

Cross-compiles command-line tools as portable, self-contained binaries for Linux, macOS, and Windows. No runtime dependencies required.

## Patched upstream tools

Some tools are upstream releases with small fixes. Their tasks download the upstream source by checksum and apply the numbered patch files in `tasks/<name>/patches/`; each patch file explains the defect it fixes. The packages carry the patches in `share/<name>/patches/`.

- **wasm-bindgen**: the [wasm-bindgen](https://github.com/wasm-bindgen/wasm-bindgen) CLI, built from its crates.io packages with upstream's `Cargo.lock`. In Emscripten mode, upstream moves the start function of the linker, which initializes the shared memory of a module with threads (`-pthread`), to an export that its JavaScript calls after instantiation. The memory is then no longer initialized at instantiation, and the `emcc` link fails for modules whose `EM_JS` or `EM_ASM` strings `emcc` reads from that memory, for example with `-sMALLOC=mimalloc`. The patch keeps that start function in place

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
