# osa

Small **Klin** library used as a **fixture** for remote imports
(`klin get` / [issue 049](https://github.com/MrHIDEn/klin/blob/main/issues/049-remote-imports.md)
in the Klin repository).

Not part of the Klin stdlib. API is intentionally minimal and stable for tags.

## Requirements

- [Klin](https://github.com/MrHIDEn/klin) compiler

## Usage (requires Klin issue 049)

Until remote fetch lands, use a local copy or `-I` / `KLIN_PATH`. After 049:

```klin
import "github/mrhiden/osa"

fn main() {
    let n = osa.add(2, 3)
    // …
}
```

Alias:

```klin
import "github/mrhiden/osa" o
```

## API

| Symbol | Meaning |
|---|---|
| `version(): i32` | package version (`1` at `v0.1.0`) |
| `add(a, b): i32` | sum |
| `clamp(v, lo, hi): i32` | clamp to range |

## Layout

Directory `osa/` is one module (multiple `.kl` files, Go/V-style).
`*_test.kl` files are not loaded on import.

## Versions

Pins are git tags (`v0.1.0`, …). Breaking changes get a new tag;
`version()` bumps when used for `klin update` tests.

## License

MIT
