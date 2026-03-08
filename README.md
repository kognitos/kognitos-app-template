# Kognitos App Design Rules

Cursor rules for building Kognitos dashboard applications on top of the Kognitos automation platform, using the [Lattice Design System](https://github.com/kognitos/lattice) (`@kognitos/lattice`).

## Quick Links

| Document | Purpose |
|----------|---------|
| [01-workflow.mdc](./01-workflow.mdc) | Master workflow: 6-phase sequence, gates, tech stack, universal rules |
| [02-api-discovery.mdc](./02-api-discovery.mdc) | Phases 1-3: API reference, environment setup, automation discovery, run output inspection |
| [03-planning-build.mdc](./03-planning-build.mdc) | Phases 4-6: domain thinking, build plan, design system selection, app build |
| [04-lattice-ui.mdc](./04-lattice-ui.mdc) | Lattice UI: installation, component mapping, tokens, layout rules, gotchas |
| [05-npm-local-packages.mdc](./05-npm-local-packages.mdc) | Local npm packages: tarball installation to avoid duplicate dependencies |

## Usage

Copy these `.mdc` files into your project's `.cursor/rules/` directory to use them as Cursor AI rules.

```bash
# Clone this repo
git clone https://github.com/kognitos/kognitos-app-design-rules.git

# Copy rules into your project
cp kognitos-app-design-rules/*.mdc your-project/.cursor/rules/
```

## Golden Rules

1. **Follow the phases in order** — Do not skip ahead. Each phase has a gate that requires user confirmation.
2. **TypeScript only** — No Python scripts. Use `apache-arrow` npm package for Arrow IPC decoding.
3. **Use Lattice components** — Don't reinvent. Compose primitives for custom UI.
4. **Use design tokens** — Never hardcode colors or spacing.
5. **Never expose API tokens** — All API calls happen server-side.
6. **Use domain language** — No Kognitos jargon in user-facing text.
