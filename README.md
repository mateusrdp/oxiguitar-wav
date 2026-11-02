# oxiguitar-wav

The WAV export plugin for [OxiGuitar](https://github.com/mateusrdp/oxiguitar), a free, open-source guitar tablature and score viewer, editor and player for Windows, macOS and Linux. It adds **File, Export, WAV Audio**: OxiGuitar plays the whole song, or the selected bars, through its instruments, amps and mixer faster than real time, as written or at your practice speed, and this plugin writes the sound as a WAV file.

- Plugin file `wav.oxp`, id `oxiguitar.wav`. The format is in its settings (Tools, Plugins, WAV export, Settings): 24-bit at 48 kHz by default; 16-bit (with dither), 24-bit or 32-bit float, 44.1 or 48 kHz.
- It needs an instrument plugin to make the sound ([oxiguitar-midi](https://github.com/mateusrdp/oxiguitar-midi)) and a format plugin to open the score ([oxiguitar-guitarpro](https://github.com/mateusrdp/oxiguitar-guitarpro)). `oxiguitar-cli export SONG.gp5 SONG.wav` does the same from the command line.
- The manual's [Exporting audio](https://mateusrdp.github.io/oxiguitar/audio-export.html) page says what goes in; the plugin guide's [Exporters](https://mateusrdp.github.io/oxiguitar/plugin-guide/exporters.html) page is how an exporter plugin works.

## Install

Every [release](https://github.com/mateusrdp/oxiguitar-wav/releases) holds a zip per system (Linux x86_64 and ARM64, Windows x86_64 and ARM64, macOS), a `.deb` and an `.rpm` for Linux, a per-user Windows installer (no administrator needed), a macOS `.pkg`, and a `SHA256SUMS` file. The OxiGuitar manual's [install page](https://mateusrdp.github.io/oxiguitar/installing.html) says which one to use and how to keep the plugin updated through your package manager. The plugin needs OxiGuitar 0.11 or later (plugin interface 1.4).

## Build and test

Rust 1.99 or later from [rustup](https://rustup.rs). The plugin SDK comes from OxiGuitar's repository by git tag (`v0.11.0`); nothing of OxiGuitar's is on crates.io.

```sh
cargo test          # unit tests, and the contract suite on the built .oxp file
./build-oxp.sh      # dist/wav-VERSION-SYSTEM-ARCH.oxp
```

## History

This plugin lived in the [OxiGuitar repository](https://github.com/mateusrdp/oxiguitar) until its version 0.11.0. Its history came along; an issue number such as `mateusrdp/oxiguitar#123` in an old commit message is in that repository.

## Licence

GPL-3.0-or-later. See LICENSE. Contributions are welcome under the same terms; see [CONTRIBUTING.md](CONTRIBUTING.md).
