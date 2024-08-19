# BAE - Your companion to detect kernel attacks by a Behaviour Analysis of Exploits

BAE is the result of my Master Thesis project realised at the National University of Singapore.

It offers a real time protection against threats in the Kernel by detecting malicious behaviours described in the Behaviour of Functions Formatting Language (BFFL) files.

BAE is developped in Rust using the eBPF technology.

## Prerequisites

1. Ensure Rust is installed
2. Install toolchains:
 - `rustup install stable`
 - `rustup toolchain install nightly --component rust-src`
3. Install bpf-linker: `cargo install bpf-linker`

## Build BAE

```bash
cargo xtask build-ebpf
```

To perform a release build you can use the `--release` flag.
You may also change the target architecture with the `--target` flag.

### Build Userspace

```bash
cargo build
```

### Build eBPF and Userspace

```bash
cargo xtask build
```

## Load BFFL files

1. Save your BFFL file in *behaviour.bffl*
2. Run the loader `./loader.py`


## Run BAE

```bash
RUST_LOG=info cargo xtask run
```
