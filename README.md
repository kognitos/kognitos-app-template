# Kognitos App Design Rules

Design rules and guidelines for building Kognitos applications using the [Lattice Design System](https://github.com/kognitos/lattice) (`@kognitos/lattice`).

## Overview

These rules distill patterns, conventions, and best practices from the Lattice design system into actionable guidelines for application development. Follow them to ensure consistency, accessibility, and maintainability across Kognitos products.

## Quick Links

| Document | Purpose |
|----------|---------|
| [01-philosophy.md](./01-philosophy.md) | Core principles: feature-agnostic design, composition |
| [02-setup-and-usage.md](./02-setup-and-usage.md) | Lattice setup, imports, ThemeProvider |
| [03-styling.md](./03-styling.md) | Styling rules: tokens, components, what to avoid |
| [04-tokens-and-themes.md](./04-tokens-and-themes.md) | Color tokens, theme system, light/dark mode |
| [05-components.md](./05-components.md) | Component usage patterns and composition |
| [06-data-tables.md](./06-data-tables.md) | DataTable usage with proper typing |
| [07-internationalization.md](./07-internationalization.md) | i18n for user-facing text |
| [08-accessibility.md](./08-accessibility.md) | Accessibility requirements |

## Golden Rules

1. **Use Lattice components** — Don't reinvent. Compose primitives for custom UI.
2. **Use design tokens** — Never hardcode colors or spacing.
3. **Keep features in your app** — The design system is generic; domain logic stays in application code.
4. **Design first** — Changes flow from Figma → design system → your app.

## Design System Reference

- **Package**: `@kognitos/lattice`
- **Figma**: [Kognitos Design System](https://www.figma.com/design/CzPeHQcKj6bNvk4EBMQQRD/Kognitos-Design-System---shadcn)
- **Storybook**: Run `npm run storybook` in the Lattice repo for component documentation
