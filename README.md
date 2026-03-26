# Regex Tester & Splunk props.conf Builder

A collection of lightweight, offline browser tools — no server, no dependencies, no internet required.

## Tools

- **`regextest.html`** — Live regex tester with match highlighting and index reporting.
- **`propsbuilder.html`** — Splunk `props.conf` builder with live event-splitting and timestamp tests.

---

## Requirements

- Any modern browser (Chrome, Edge, Firefox, Safari).
- No installation, build step, or internet connection needed.

---

## regextest.html

### Usage

1. Open `regextest.html` in any modern browser.
2. Type your regular expression pattern in the **Regular Expression** field.
3. Enter any flags (e.g. `g`, `i`, `m`) in the flags field on the right (defaults to `g`).
4. Paste or type your sample text / log output in the **Sample Log** textarea.
5. Matches are highlighted in real time and listed below with their index positions.

### Features

- **Live highlighting** — matches are highlighted directly in the text area as you type.
- **Match list** — each match is listed with its value and character index range.
- **Match counter** — displays the total number of matches found.
- **Inline error feedback** — invalid patterns show an error message immediately.
- **Flags support** — `g`, `i`, `m`, `s`, `u`, `d` flags are all supported.
- **Zero-length match safety** — prevents infinite loops on patterns that match empty strings.

### Supported Flags
|------|-------------|
| `g`  | Global — find all matches (default) |
| `i`  | Case-insensitive |
| `m`  | Multiline — `^`/`$` match line boundaries |
| `s`  | Dotall — `.` matches newlines |
| `u`  | Unicode mode |
| `d`  | Generate match indices (ES2022+) |

## propsbuilder.html

A browser-based builder for Splunk `props.conf` stanzas. Configure sourcetype parsing settings through a form UI and get a ready-to-paste `props.conf` output.

### Usage

1. Open `propsbuilder.html` in any modern browser.
2. Enter a **Sourcetype Name** — this becomes the `[stanza]` header.
3. Paste raw log lines into the **Log Sample** textarea.
4. Configure **Parser Settings** as needed.
5. Optionally add extra directives via **Additional Fields**.
6. Use the **Line Breaker Test** and **Timestamp Test** tabs to validate your settings against the sample.
7. Click **Regenerate** to refresh the output, then **Copy** to copy it to the clipboard.

### Features

- **Sourcetype builder** — sets the `[stanza]` name with bracket formatting.
- **Log Sample** — paste raw log lines used for live testing.
- **Parser Settings** — configure the most common `props.conf` directives through a form:
  - `SHOULD_LINEMERGE`, `LINE_BREAKER`
  - `TIME_PREFIX`, `TIME_FORMAT`, `MAX_TIMESTAMP_LOOKAHEAD`
  - `TZ`, `TRUNCATE`, `NO_BINARY_CHECK`, `CHARSET`
  - `KV_MODE`, `INDEXED_EXTRACTIONS`, `TRANSFORMS`
  - `disabled`
- **Additional Fields** — add any arbitrary `props.conf` key/value pair not covered by the form.
- **Line Breaker Test** — runs `LINE_BREAKER` against the log sample and shows how events would be split.
- **Timestamp Test** — tests `TIME_PREFIX` + `TIME_FORMAT` against each log line and shows extracted timestamps with parse status.
- **Generated output** — produces a clean, copy-ready `props.conf` stanza.

---

## Requirements

- Any modern browser (Chrome, Edge, Firefox, Safari).
- No installation, build step, or internet connection needed.

## File Structure

```
regextester/
├── regextest.html     # Regex tester — single self-contained HTML file
└── propsbuilder.html  # Splunk props.conf builder — single self-contained HTML file
```
