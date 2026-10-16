# App icons

| File | Size | Use |
|---|---|---|
| `favicon.svg` | vector (64 grid) | Modern browsers. Flat mark colours for crispness at 16–32px |
| `favicon.ico` | 16, 32, 48 | Legacy browsers, Windows |
| `apple-touch-icon.png` | 180 × 180 | iOS home screen (full-bleed square, iOS rounds the corners) |
| `icon-192.png`, `icon-512.png` | 192, 512 | PWA manifest `icons` (`purpose: "any"`), rounded square |
| `maskable-icon-512.png` | 512 × 512 | PWA manifest (`purpose: "maskable"`), mark inside the 80% safe zone |
| `*.svg` | vector | Sources for the PNGs above |

```html
<link rel="icon" href="/favicon.ico" sizes="48x48">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="apple-touch-icon" href="/apple-touch-icon.png">
```

```json
"icons": [
  { "src": "/icon-192.png", "sizes": "192x192", "type": "image/png" },
  { "src": "/icon-512.png", "sizes": "512x512", "type": "image/png" },
  { "src": "/maskable-icon-512.png", "sizes": "512x512", "type": "image/png", "purpose": "maskable" }
],
"theme_color": "#0d0d0c",
"background_color": "#0d0d0c"
```
