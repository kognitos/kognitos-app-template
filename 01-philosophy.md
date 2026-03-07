# Philosophy

## Feature-Agnostic Design System

The Lattice design system is a **pure design library** with no business logic or domain context. It provides reusable UI primitives that you compose into feature-specific components in your application.

### ✅ Acceptable in the Design System

- Generic names: `Button`, `Card`, `DataTable`, `Modal`
- Generic props: `variant`, `size`, `disabled`, `isLoading`
- Semantic tokens: `primary`, `secondary`, `destructive`, `muted`
- Placeholder content: "Click me", "Title", "Description"

### ❌ Not Acceptable in the Design System

- Feature names: `InvoiceCard`, `UserProfileButton`, `WorkflowModal`
- Domain props: `invoiceId`, `userId`, `workflowStatus`
- Business logic inside components
- Feature-specific text: "Process Invoice", "Submit Workflow"

## Where to Build What

| Build in Design System | Build in Your App |
|------------------------|-------------------|
| Generic UI primitives | Feature-specific components |
| Reusable patterns | Business logic |
| Semantic tokens | Domain models |
| Accessible building blocks | Composed workflows |

## Composition Over Customization

When you need a specialized component, **compose** Lattice primitives in your application:

```tsx
// ✅ In your application
import { Button, Icon } from '@kognitos/lattice';

export function SubmitInvoiceButton({ onSubmit }) {
  return (
    <Button onClick={onSubmit}>
      <Icon type="Send" />
      Submit Invoice
    </Button>
  );
}
```

Don't add feature-specific components to the design system. Build them by composing primitives.

## Design-First Workflow

Design changes flow in one direction:

1. **Figma** — Designers create/update components and tokens
2. **Lattice** — Design system implements and syncs from Figma
3. **Your App** — Consume updated components and tokens

Never implement UI that doesn't exist in the Figma design system. Request designs from the design team first.
