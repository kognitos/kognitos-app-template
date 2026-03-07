# Internationalization (i18n)

Lattice components use built-in i18n for user-facing text. When building your app, follow these patterns.

## Golden Rules

- **NEVER hardcode user-facing strings** in shared components.
- **ALWAYS allow prop overrides** — Use `??` fallback so consumers can override.
- **Keep translations generic** — No feature-specific language in the design system.
- **Include aria-labels** — Accessibility text must be translatable.

## In Your Application

For app-specific text, use your own i18n solution (e.g., react-i18next, next-intl). Lattice components accept prop overrides for their default text:

```tsx
// Lattice components allow overrides
<Input placeholder={t('app.searchPlaceholder')} />
<Button aria-label={t('app.submitButton')}>Submit</Button>
```

## What Requires Translation

| Text Type | Example |
|-----------|---------|
| Placeholders | "Type here", "Search..." |
| Button text | "Previous", "Next", "Submit" |
| Empty state messages | "No messages yet" |
| Aria-labels | "Send message", "Remove attachment" |
| Status text | "Loading...", "Completed" |
| Error messages | "No results found" |

## Testing with Translations

When testing components that use Lattice's i18n, you can provide custom translations via `I18nProvider` if needed. By default, Lattice falls back to English.

## Lattice i18n (Design System Internal)

Lattice manages its own translations for component defaults. As an app developer, you typically override these via props when you need localized text. The design system uses `useI18n` internally and follows the `??` fallback pattern: `placeholder ?? t('input.placeholder')`.
