# Changelog

## 0.4

> **Disclaimer:** I'm not a professional programmer. The code changes in this
> version were written with the help of an AI assistant (Claude, by Anthropic).
> I directed the changes, tested them and decided what I wanted, but I did not
> write all of the code myself. Please review it before relying on it.

### Added
- **Rebind hotkeys inside the app.** A new "Hotkeys" row has a Start and a Stop
  button. Click one, then press the new key (Ctrl, Shift and Alt combinations
  work). Press Esc to cancel.
- **Hotkeys are saved** to `config.txt` (`start_key` / `stop_key`) and restored
  on the next launch. Existing filters and comments in `config.txt` are kept.
- **Toggle mode.** If Start and Stop are bound to the same key, that key starts
  filtering when idle and stops it when running. The UI shows "(same key: toggles)"
  when this is active. With two different keys, each key only does its own job.

### Changed
- Throttle module: the allowed range now goes up to 10000 ms.
- The Presets dropdown now uses all the free width, so long preset names fit.
- Start/Stop hotkeys no longer fire when they don't apply (for example, pressing
  the Start key while already filtering does nothing).
- Modifier names in `config.txt` are case-insensitive (`Ctrl+F5` and `ctrl+F5`
  both work).

### Fixed
- Hotkeys using keys with codes above 127 never matched.
- Hotkeys that include Alt never triggered.
- `config.txt` was left open after loading, which would have blocked saving it.

### Credits
Based on [clumsy](https://github.com/jagt/clumsy) by jagt (MIT license) and the
0.3 "with keybinds" version it builds on. All credit for the original work goes
to their authors.
