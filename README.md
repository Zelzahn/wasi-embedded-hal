# `wasi-embedded-hal`

> Implementation of the [`embedded-hal`] traits for Webassembly components

[`embedded-hal`]: https://crates.io/crates/embedded-hal

## Status

Currently only support for I2C and Delay is provided, but more is planned.

Note that only `embedded-hal` version 1.O is supported.

## Usage

Simply use this crate and then add `add_i2c_hal!(i2c)` in your file. Where `i2c` is the module from `bindings.rs` generated by [`cargo-component`](https://github.com/bytecodealliance/cargo-component).

## Why the need for this crate

The generated bindings and the `embedded-hal` API differ slightly, e.g. `&[...]` vs. `Vec<...>`. This crate defines methods that follow the `embedded-hal` API, and that underneath call those from the generated bindings. Effectively allowing one to very easily use crates that adhere to `embedded-hal` inside Wasm.

## Minimum Supported Rust Version (MSRV)

This crate is guaranteed to compile on stable Rust 1.76.0 and up. It might compile with older versions but that may change in any new patch release.
