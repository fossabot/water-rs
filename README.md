# W.A.T.E.R.: WebAssembly Transport Executables Runtime
![GitHub License](https://img.shields.io/github/license/erikziyunchi/water-rs)
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Ferikziyunchi%2Fwater-rs.svg?type=shield&issueType=license)](https://app.fossa.com/projects/git%2Bgithub.com%2Ferikziyunchi%2Fwater-rs?ref=badge_shield&issueType=license) [![Build & Test Status](https://github.com/erikziyunchi/WASMable-Transport/actions/workflows/rust.yml/badge.svg?branch=main)](https://github.com/erikziyunchi/WASMable-Transport/actions/workflows/rust.yml)

<div style="width: 100%; height = 160px">
    <div style="width: 75%; height: 150px; float: left;"> 
        WATER-rs provides a Rust runtime for WebAssembly Transport Modules(WATM) as a pluggable application-layer transport protocol provider. It is designed to be highly portable and lightweight, allowing for rapidly deployable pluggable transports. While other pluggable transport implementations require a fresh client deployment (and app-store review) to update their protocol WATER allows dynamic delivery of new transports in real time over the network.<br />
        <br />
    </div>
    <div style="margin-left: 80%; height: 150px;"> 
        <img src=".github/assets/logo_v0.svg" alt="WATER wasm transport" align="right">
    </div>
</div>

The Go implementation of the runtime library can be found in [water-go](https://github.com/gaukas/water). We now also support building WATM in Go, please refer to [watm](https://github.com/gaukas/watm) for examples and helper libraries interfacing Pluggable Transports-like interfaces. Official Go compiler is currently not supported ([watm#4](https://github.com/gaukas/watm/issues/4)).

### Cite our work

If you quoted or used our work in your own project/paper/research, please cite our paper [Just add WATER: WebAssembly-based Circumvention Transports](https://arxiv.org/pdf/2312.00163.pdf).

<details>
  <summary>BibTeX</summary>
    
  ```bibtex
  @inproceedings{water-foci24,
	  author = {Chi, Erik and Wang, Gaukas and Halderman, J. Alex and Wustrow, Eric and Wampler, Jack},
	  year = {2024},
	  month = {02},
	  title = {Just add {WATER}: {WebAssembly}-based Circumvention Transports},
	  address = {Virtual Event},
	  series = {FOCI '24},
	  booktitle = {Free and Open Communications on the Internet},
  }
  ```
</details>

**Update**: our paper has been accepted by FOCI and will appear at [FOCI 2024](https://foci.community/foci24.html) on Feb 19, 2024!

## Be Water

> Empty your mind, be formless, shapeless, like water. If you put water into a cup, it becomes the cup. You put water into a bottle and it becomes the bottle. You put it in a teapot, it becomes the teapot. Now, water can flow or it can crash. Be water, my friend.
>
> -- Bruce Lee

## Contents

The repo contains 2 main components:
1. A Rust crate [`water`](https://github.com/erikziyunchi/water-rs/tree/main/crates/water) runtime library used to interact with `.wasm` WebAssembly Transport Modules(WATM).
2. A Rust crate [`watm_v0`](https://github.com/erikziyunchi/water-rs/tree/main/crates/watm_v0) for the v0 WATM-development where developers can easily create their own `.wasm` (the general version of `watm` is still under development).


Also include examples for demonstration of usage:
1. ⭐ A standalone [`cli`](https://github.com/erikziyunchi/water-rs/tree/main/examples/clients/cli) tool which is compatible with both `v0` and `v1_preview`, and can run all different roles with all of our example WATM binaries.
2. A few examples WATM implementations with `water_wasm` crate, see [water-rs/tree/main/examples/water_bins](https://github.com/erikziyunchi/water-rs/tree/main/examples/water_bins).
3. Examples of using the above WATM examples with our `water` library, see [tests](https://github.com/erikziyunchi/water-rs/tree/main/tests/tests) for usage.

## Running tests

```sh
# runs ALL tests
cargo test --workspace --verbose

# run tests for a single crate
cargo test -p <crate_name> --verbose

# run a single test (or test matching name prefix) in a single crate
cargo test -p <crate_name> --verbose -- <test_name>
```
