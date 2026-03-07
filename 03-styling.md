# Styling Rules

## Golden Rules

1. **Use pre-built components first** — They handle accessibility, theming, and responsive design.
2. **Use component variants and props** — Prefer `<Button variant="primary" size="lg">` over custom classes.
3. **Use design tokens** — Never hardcode colors or spacing.
4. **Avoid inline styles** — They break theme consistency.
5. **Avoid arbitrary Tailwind values** — Use tokens instead of `bg-[#ff0000]`.

## Semantic Color Classes

Use Tailwind classes that map to design tokens:

| Use | Instead of |
|-----|------------|
| `bg-primary` | `bg-[#hex]` or `bg-blue-500` |
| `text-muted-foreground` | `text-gray-500` |
| `border-border` | `border-gray-200` |
| `bg-destructive` | Custom red |
| `text-success` | Custom green |

## Component Variants

Prefer variant props over custom styling:

```tsx
// ✅ Use variants
<Button variant="destructive" size="lg">Delete</Button>
<Badge variant="success">Active</Badge>
<Alert variant="warning">Check your input</Alert>

// ❌ Don't add custom classes for standard cases
<Button className="bg-red-500 text-white">Delete</Button>
```

## Layout and Spacing

Use Tailwind utilities for layout. Design tokens define spacing scale:

- `gap-2`, `gap-4`, `p-4`, `m-2` — Use standard scale
- `flex`, `grid`, `flex-col` — Layout utilities
- `rounded-md`, `rounded-lg` — Use `--radius-*` tokens via Tailwind

## The `cn()` Utility

For merging classes with proper precedence:

```tsx
import { cn } from '@kognitos/lattice';

<div className={cn('base-styles', variantStyles, className)} />
```

## What NOT to Do

```tsx
// ❌ Inline styles
<div style={{ backgroundColor: 'red' }} />

// ❌ Arbitrary color values
<div className="bg-[#3b82f6]" />

// ❌ Overriding design system theme
<DataTable className="custom-table-styles" />

// ❌ Hardcoded spacing that ignores tokens
<div className="p-[13px]" />
```
