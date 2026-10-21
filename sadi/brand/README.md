# SADI — original vector identity

SADI means **Study AI Digital Product**. This identity uses custom-drawn uppercase lettering and a deliberately small six-arm typographic asterisk. The mark is an editorial signature, not a generic four-point AI sparkle.

## Assets

| File | Use |
| --- | --- |
| `sadi-wordmark-light.svg` | Primary horizontal wordmark; ink letters + terracotta asterisk on a light surface |
| `sadi-wordmark-dark.svg` | Reverse horizontal wordmark; warm letters + terracotta asterisk on ink |
| `sadi-wordmark-mono.svg` | One-ink horizontal wordmark for simple footer or print use |
| `sadi-mark.svg` | Compact S + asterisk on rounded ink tile; app/avatar use |
| `sadi-favicon.svg` | SVG browser icon; tested at 16 × 16 and 32 × 32 CSS pixels |
| `preview.html` | Local identity specimen with large, small, light/dark and actual-size icon examples |

**No font dependency.** Every letter, counter, asterisk and tile is an editable SVG path. No external assets, embedded raster images, filters, scripts, motion, or CDN calls. Original geometry was authored for this project; no third-party logo template or typeface outlines were used.

## Color

- Canvas: `#F8F8F6`
- Ink: `#252521`
- Terracotta: `#C15F3C`

The accent occupies only the asterisk. Do not recolor the whole wordmark terracotta in normal navigation. Reverse letters use warm canvas rather than stark white.

## Sizing and spacing

- Horizontal SVG viewBox: `0 0 248 80`; preserve this aspect ratio.
- Recommended navbar width: **112 px** (36.13 px intrinsic height), suitable inside a 55–56 px navbar. Recommended minimum: **96 px** wide. The 80 px monochrome footer specimen is a small-use fallback; 96 px remains preferred.
- Large identity specimen: 440 px wide. Scale freely for print; all source geometry is vector.
- Compact mark viewBox: `0 0 64 64`; use at 32 px or larger for prominent application branding.
- Favicon: use the dedicated SVG at 16 px and 32 px. It keeps the S and asterisk, not a miniaturized four-letter wordmark.
- Keep external clear space equal to at least one I-stem width (13 SVG units; about 6 px at 112 px logo width) on every side. The SVG bounds include optical breathing room vertically and to the right, but external left clear space is still needed.
- Never distort width/height independently, add shadows/outlines, rotate the asterisk, crop the viewBox, or use the reverse variant over a light surface.

## Integration (root-owned UI files)

```html
<a href="/" aria-label="SADI home">
  <img src="/sadi-brand/sadi-wordmark-light.svg" alt="SADI" width="112" height="36" style="height:auto">
</a>
<link rel="icon" type="image/svg+xml" href="/sadi-brand/sadi-favicon.svg">
```

For a dark footer, use `/sadi-brand/sadi-wordmark-dark.svg`; for a restrained light footer, use `/sadi-brand/sadi-wordmark-mono.svg`. The image already includes its asterisk: do not append a second `*`. Keep the legal/accessible brand name **SADI**, not a spoken “SADI asterisk”.

Inline-SVG consumers must uniquify `title`/`desc` IDs for multiple instances. External `<img>` use is isolated and needs only appropriate `alt` text.

## Local review

With the existing app HTTP server, open `/sadi-brand/preview.html`. A deterministic Playwright checker also serves these assets over an ephemeral loopback HTTP server and records source bounds, actual-size favicon pixels, loaded-image status, console errors, and desktop/mobile screenshots in `.unlazy/sadi-overhaul-20261021/logo/`.

```powershell
node .unlazy/sadi-overhaul-20261021/logo/verify.mjs --source
node .unlazy/sadi-overhaul-20261021/logo/verify.mjs --browser
node .unlazy/sadi-overhaul-20261021/logo/verify.mjs --rollback
```

No Navbar, Footer, app entry or backend file was changed by the logo worker. Root integrates the chosen asset paths.
