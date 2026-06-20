# Coinbroo Brand

Single source of truth for Coinbroo's visual identity. When a color/asset
changes, update it here first, then propagate to each project (see **Where it
lives**).

## Logo

- **Mark:** teal cursive "C" (`logo.png`, transparent background)
- **Source file:** generated from the original artwork with the white
  background removed and trimmed to a square.
- **Assets:**
  | File | Size | Use |
  |---|---|---|
  | `logo.png` | 256×256 | Header / nav logo |
  | `favicon-32.png` | 32×32 | Browser favicon |
  | `favicon-16.png` | 16×16 | Browser favicon |
  | `apple-touch-icon.png` | 180×180 | iOS home-screen icon |
- **Clear space:** keep padding ≥ the height of the "C" stem around the mark.
- **Don't:** place the mark on a busy/low-contrast background, recolor it, or
  add a drop shadow.

## Colors

### Brand

| Role | Hex | RGB | Notes |
|---|---|---|---|
| **Accent (teal)** | `#1EBCAD` | `30, 188, 173` | Primary brand color, sampled from the logo |
| **Accent hover (dark)** | `#179C8F` | `23, 156, 143` | Darker variant for hover/pressed states |

### Neutrals

| Role | Hex | Notes |
|---|---|---|
| Background (near-black) | `#0A0E14` | Landing page bg |
| Text (off-white) | `#E8EDF3` | Primary text |
| Text muted | `#6B7A8D` | Secondary/footer text |

> The app uses a slightly different, fuller neutral + state scale (below).
> The **accent teal is identical** across both.

### App state colors (trading UI)

Defined in `app.coinbroo.com` `tailwind.config.js`:

| Token | Hex | Use |
|---|---|---|
| `bg.primary` / `secondary` / `tertiary` / `hover` | `#0A0E0F` / `#0F1415` / `#161B1D` / `#1C2325` | Surfaces |
| `border.primary` / `secondary` | `#1F2628` / `#2E3739` | Dividers |
| `text.primary` / `secondary` / `muted` | `#E6EDF0` / `#7D8A8C` / `#5A6668` | Text |
| `long` / `long-dim` / `long-bg` | `#1FB98A` / `#178A67` / `#0C2A22` | Buy / long |
| `short` / `short-dim` / `short-bg` | `#ED7088` / `#C2526A` / `#2A1219` | Sell / short |

## Where it lives

The two projects are separate stacks, so each keeps its own declaration of the
brand color. Keep them in sync with the values above.

| Project | Stack | Canonical location | Accent token = hex | Hover token = hex |
|---|---|---|---|---|
| `coinbroo.com` (landing) | Static HTML/CSS | `:root` CSS variables in `index.html` | `--brand` = `#1EBCAD` | `--brand-hover` = `#179C8F` |
| `app.coinbroo.com` (app) | Next.js + Tailwind | `theme.extend.colors.accent` in `tailwind.config.js` | `accent.blue` = `#1EBCAD` | `accent.blue-dim` = `#179C8F` |

> **Note 1:** the Tailwind token is named `accent.blue` for historical reasons —
> it is actually the teal accent, not blue.
>
> **Note 2:** do **not** confuse `accent.blue-dim` (`#179C8F`, the teal hover)
> with `long-dim` (`#178A67`). `long-dim` is the dimmed **green for long/buy**
> positions in the trading UI — a completely separate token, unrelated to the
> brand accent, despite looking similar.

## Typography

- **Font:** Inter (with system-ui / `-apple-system` fallback)
- **Headings:** weight 800, tight letter-spacing
- **Body:** weight 400–500

---
*Update this file whenever the palette or logo changes.*
