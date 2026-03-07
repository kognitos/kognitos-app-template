# Tokens and Themes

## Theme System

Lattice uses CSS custom properties that automatically switch between light and dark values based on the `.dark` class on the root element. `ThemeProvider` manages this for you.

## Color Tokens

### Base Colors

- `black`, `white`, `transparent`

### Semantic Theme Colors

| Token | Purpose |
|-------|---------|
| `primary` / `primary-foreground` | Primary actions, brand |
| `secondary` / `secondary-foreground` | Secondary elements |
| `accent` / `accent-foreground` | Highlights, hover states |
| `background` / `foreground` | Page background, default text |
| `card` / `card-foreground` | Card surfaces |
| `muted` / `muted-foreground` | Subdued backgrounds and text |
| `destructive` / `destructive-foreground` | Errors, danger |
| `border`, `input`, `ring` | Borders, inputs, focus rings |

### Status Colors

- `success` / `success-foreground`
- `warning` / `warning-foreground`
- `informative` / `informative-foreground`
- `brand`, `link`

### Chart Colors

- `chart-1` through `chart-10` — For data visualization

### Sidebar Colors

- `sidebar`, `sidebar-foreground`, `sidebar-primary`, `sidebar-accent`, `sidebar-border`, `sidebar-muted`

## Using Tokens in Code

```tsx
// Via Tailwind (preferred)
<div className="bg-primary text-primary-foreground" />
<span className="text-muted-foreground" />

// Via design system API (when needed)
import { getColorToken } from '@kognitos/lattice';
const color = getColorToken('primary'); // Returns "var(--primary)"
```

## Theme Modes

- `light` — Light theme
- `dark` — Dark theme  
- `system` — Follows OS preference

## Typography Tokens

- **Font**: `PP Neue Montreal` (sans), `IBM Plex Mono` (mono)
- **Radius**: `--radius`, `--radius-sm`, `--radius-md`, `--radius-lg`

## Never Hardcode

Always use tokens. Hardcoded colors break theme switching and design consistency.
