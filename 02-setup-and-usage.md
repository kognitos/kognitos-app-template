# Setup and Usage

## Installation

```bash
npm install @kognitos/lattice
```

## Required Peer Dependencies

- `react`: ^18.0.0 || ^19.0.0
- `react-dom`: ^18.0.0 || ^19.0.0
- `dayjs`: ^1.11.0 (for date utilities)
- `react-hook-form`: ^7.0.0 (for Form components)
- `recharts`: ^2.0.0 || ^3.0.0 (for Chart components)

## CSS Setup

Import Lattice theme and fonts in your root CSS file:

```css
/* index.css or global styles */
@import 'tailwindcss';
@import 'tw-animate-css';

@import '../node_modules/@kognitos/lattice/theme.css';
@import '../node_modules/@kognitos/lattice/fonts.css';
@source '../node_modules/@kognitos/lattice/**/*.{js}';

/* Your customizations go after this */
```

## App Setup

Wrap your app with `ThemeProvider`:

```tsx
import { ThemeProvider } from '@kognitos/lattice';

function App() {
  return (
    <ThemeProvider defaultTheme="system" storageKey="kognitos-theme">
      <YourApp />
    </ThemeProvider>
  );
}
```

## Importing Components

Use named imports from the package:

```tsx
import {
  Button,
  Card,
  Input,
  ThemeProvider,
  type IButtonProps,
} from '@kognitos/lattice';
```

## Theme Switching

Use the `useTheme` hook for theme state:

```tsx
import { useTheme, ModeToggle } from '@kognitos/lattice';

function Header() {
  const { theme, setTheme } = useTheme();

  return (
    <header>
      <ModeToggle /> {/* Pre-built light/dark/system toggle */}
    </header>
  );
}
```
