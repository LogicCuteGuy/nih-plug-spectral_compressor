# Spectral Compressor

Have you ever wondered what a 16384 band OTT would sound like? Neither have I.
Spectral Compressor can squash anything into pink noise, apply simultaneous
upwards and downwards compressor to dynamically match the sidechain signal's
spectrum and morph one sound into another, and lots more.

![Screenshot](https://i.imgur.com/r6WfoYp.png)

This is a port of https://github.com/robbert-vdh/spectral-compressor with more
features and much better performance.  A recent addition is a "Delta" switch that
outputs a per‑channel difference signal (processed minus dry), which is useful for
monitoring exactly what the compressor is doing in stereo.

## Download

You can download the development binaries for Linux, Windows and macOS from the
[automated
builds](https://github.com/robbert-vdh/nih-plug/actions/workflows/build.yml?query=branch%3Amaster)
page. Or if you're not signed in on GitHub, then you can also find the latest nightly
build [here](https://nightly.link/robbert-vdh/nih-plug/workflows/build/master).

On macOS you may need to [disable
Gatekeeper](https://disable-gatekeeper.github.io/) as Apple has recently made it
more difficult to run unsigned code on macOS.

### Building

### Delta mode

When the Delta parameter is enabled the plugin no longer passes through the normal
wet audio.  Instead it outputs `(processed - dry)` on each channel.  This keeps the
stereo field intact while making it trivial to hear just the change introduced by
the compressor.


After installing [Rust](https://rustup.rs/), you can compile Spectral Compressor
as follows:

```shell
cargo xtask bundle spectral_compressor --release
```
