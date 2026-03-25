# Regex Tester

A lightweight, offline regex testing tool that runs entirely in the browser — no server, no dependencies, no internet required.

## Usage

1. Open `regextest.html` in any modern browser.
2. Type your regular expression pattern in the **Regular Expression** field.
3. Enter any flags (e.g. `g`, `i`, `m`) in the flags field on the right (defaults to `g`).
4. Paste or type your sample text / log output in the **Sample Log** textarea.
5. Matches are highlighted in real time and listed below with their index positions.

## Features

- **Live highlighting** — matches are highlighted directly in the text area as you type.
- **Match list** — each match is listed with its value and character index range.
- **Match counter** — displays the total number of matches found.
- **Inline error feedback** — invalid patterns show an error message immediately.
- **Flags support** — `g`, `i`, `m`, `s`, `u`, `d` flags are all supported.
- **Zero-length match safety** — prevents infinite loops on patterns that match empty strings.

## Supported Flags

| Flag | Description |
|------|-------------|
| `g`  | Global — find all matches (default) |
| `i`  | Case-insensitive |
| `m`  | Multiline — `^`/`$` match line boundaries |
| `s`  | Dotall — `.` matches newlines |
| `u`  | Unicode mode |
| `d`  | Generate match indices (ES2022+) |

## Requirements

- Any modern browser (Chrome, Edge, Firefox, Safari).
- No installation, build step, or internet connection needed.

## File Structure

```
regextester/
└── regextest.html   # The entire app — single self-contained HTML file
```
