# Accessibility

## General Requirements

Lattice components are built on [Radix UI](https://www.radix-ui.com/) primitives and follow accessibility best practices. When using or composing them:

1. **Preserve ARIA attributes** — Don't strip or override without reason.
2. **Support keyboard navigation** — All interactive elements must be focusable and operable via keyboard.
3. **Provide aria-labels** — For icon-only buttons and controls without visible text.
4. **Use semantic HTML** — Prefer native elements where appropriate.

## Focus Management

- Focus rings use the `--ring` token. Don't remove `focus:ring` styles.
- Modals and dialogs trap focus and restore it on close.
- Use `aria-describedby` and `aria-labelledby` for complex widgets.

## Form Accessibility

- Always associate labels with inputs via `Field` or `Label`.
- Use `FieldError` for validation messages with `aria-invalid` and `aria-describedby`.
- Ensure error messages are announced to screen readers.

## Color and Contrast

- Use semantic tokens (`primary`, `destructive`, `muted-foreground`) — they're designed for contrast.
- Don't rely on color alone to convey information.
- Test with both light and dark themes.

## Testing

- Run accessibility audits (e.g., axe, Lighthouse).
- Test with keyboard only (Tab, Enter, Space, Arrow keys).
- Test with a screen reader when possible.
