# Component Usage

## Component Categories

### Primitives (Low-Level)

Building blocks: `Button`, `Input`, `Card`, `Badge`, `Select`, `Dialog`, etc. Use these directly or compose them.

### Components (Higher-Level)

Composed patterns: `PageLayout`, `EmptyState`, `InsightsCard`, `StepperCard`, `Chat`, etc.

## Common Patterns

### Button

```tsx
import { Button } from '@kognitos/lattice';

<Button variant="default">Default</Button>
<Button variant="destructive">Delete</Button>
<Button variant="outline" size="sm">Small</Button>
<Button isLoading>Loading...</Button>
<Button asChild><a href="/link">Link as Button</a></Button>
```

Variants: `default`, `destructive`, `outline`, `secondary`, `ghost`, `link`  
Sizes: `default`, `sm`, `lg`, `icon`, `icon-xs`, `icon-sm`, `icon-lg`

### Card

```tsx
import { Card, CardHeader, CardTitle, CardDescription, CardContent, CardFooter } from '@kognitos/lattice';

<Card>
  <CardHeader>
    <CardTitle>Title</CardTitle>
    <CardDescription>Description</CardDescription>
  </CardHeader>
  <CardContent>Content</CardContent>
  <CardFooter>Footer</CardFooter>
</Card>
```

### Form Fields

Use `Field` for labels, descriptions, and errors. Use `Form` with React Hook Form for validation.

### Data Display

- `DataTable` — For tabular data (see [06-data-tables.md](./06-data-tables.md))
- `Avatar`, `Badge`, `Progress`, `Empty`
- `ChartContainer`, `ChartTooltip` — For Recharts integration

### Overlays

- `Dialog`, `Sheet`, `Drawer` — Modals and panels
- `Popover`, `Tooltip`, `HoverCard` — Contextual UI
- `DropdownMenu`, `ContextMenu` — Menus

### Icons

```tsx
import { Icon } from '@kognitos/lattice';

<Icon type="Send" size="md" />
<Icon type="ChevronDown" size="sm" />
```

Use Lucide icon names or custom SVGs. See Lattice `llm.txt` for full icon list.

## Composing Custom Components

Build feature components by composing primitives:

```tsx
import { Card, CardHeader, CardTitle, CardContent, Button, Icon } from '@kognitos/lattice';

export function ActionCard({ title, onAction }) {
  return (
    <Card>
      <CardHeader>
        <CardTitle>{title}</CardTitle>
      </CardHeader>
      <CardContent>
        <Button onClick={onAction}>
          <Icon type="Play" />
          Run
        </Button>
      </CardContent>
    </Card>
  );
}
```

## TypeScript

Use exported types for props:

```tsx
import { Button, type IButtonProps } from '@kognitos/lattice';

const props: IButtonProps = { variant: 'default', children: 'Click' };
```

Interface names are prefixed with `I` (e.g., `IButtonProps`, `ICardProps`).
