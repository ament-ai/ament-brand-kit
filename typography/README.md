# Typography

AMENT uses two typefaces. Both are open-source under the
[SIL Open Font License 1.1](https://openfontlicense.org) and free to use in print, web and apps.
They are **linked, not bundled** here. Download them from the official sources below.

| Role | Typeface | Weights | Source |
|---|---|---|---|
| Everything: UI, headings, body, display | **Archivo** (variable: `wght` 100–900, `wdth` 62–125%) | 400, 500, 600 | [Google Fonts](https://fonts.google.com/specimen/Archivo) |
| Data and labels: IDs, timestamps, temperatures, eyebrows | **IBM Plex Mono** | 400, 500 | [Google Fonts](https://fonts.google.com/specimen/IBM+Plex+Mono) |

The logo wordmark is **not** set in a font. It is drawn geometry (crossbar-less A, short-armed E).
Always use the files in [`/logos`](../logos) and never retype "AMENT" in a typeface to stand in for the logo.

## Web embed

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Archivo:wdth,wght@62..125,100..900&family=IBM+Plex+Mono:wght@400;500&display=swap" rel="stylesheet">
```

Next.js (as used by ament.ai and AMENT Hive):

```ts
import { Archivo, IBM_Plex_Mono } from 'next/font/google';
const archivo = Archivo({ subsets: ['latin', 'latin-ext'], axes: ['wdth'], variable: '--font-archivo' });
const plexMono = IBM_Plex_Mono({ subsets: ['latin', 'latin-ext'], weight: ['400', '500'], variable: '--font-plex-mono' });
```

Always include the `latin-ext` subset so Turkish characters (ç, ğ, ı, İ, ö, ş, ü) render in the brand fonts.

## Styles

**Display:** Archivo at `font-stretch: 118%`, `letter-spacing: -0.02em`, weight 600. Use it for page titles,
large numerals and product names ("Hive").

```css
.display { font-family: "Archivo", sans-serif; font-stretch: 118%; letter-spacing: -0.02em; font-weight: 600; }
```

**Eyebrow (spec-sheet label):** IBM Plex Mono, 10–11px, UPPERCASE, `letter-spacing: 0.16em`.
It sits above headings and on data labels, like the header of a technical data sheet.

```css
.eyebrow { font-family: "IBM Plex Mono", monospace; font-size: 11px; line-height: 1.2; letter-spacing: 0.16em; text-transform: uppercase; }
```

**Text:** Archivo at normal width (100%), weight 400 for body and 500–600 for emphasis.

## Scale

These are the sizes used in AMENT Hive. Keep to them rather than inventing in-between sizes.

| Token | Size / line height | Typeface & style | Use |
|---|---|---|---|
| Numeral | 26–32px / 1.0 | Archivo display 600, tabular figures | Stat values |
| Title | 28px (34px ≥ md) / 1.08 | Archivo display 600 | Page titles |
| Heading | 18–20px / 1.25 | Archivo display 600 | Panel and section headings |
| Body | 14–15px / 1.5 | Archivo 400 | Running text |
| Small | 12–13px / 1.45 | Archivo 400–500 | Hints, table cells, metadata |
| Eyebrow | 10–11px / 1.2 | IBM Plex Mono 400–500, UPPERCASE, +0.16em | Labels, IDs, timestamps |

Use tabular figures (`font-variant-numeric: tabular-nums`) wherever numbers update or align in columns.

## Fallbacks

`"Archivo", ui-sans-serif, system-ui, sans-serif` and `"IBM Plex Mono", ui-monospace, monospace`.
In office documents without the brand fonts, use Arial and Courier New, never decorative substitutes.
