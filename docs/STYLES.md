# Design and Style Guidelines

This document provides guidelines for maintaining consistent design in Dashboard Hub.

## Design System

### Color Palette

#### Primary Colors
- **Primary Blue**: `#3b82f6` (217 91% 60%) - Main brand color
- **Dark Blue**: `#1e40af` (217 91% 40%) - Darker shade for hover states
- **Light Blue**: `#93c5fd` (217 91% 80%) - Lighter shade for backgrounds

#### Semantic Colors
- **Success**: `#10b981` - For successful actions
- **Warning**: `#f59e0b` - For warnings and alerts
- **Danger**: `#ef4444` - For destructive actions
- **Info**: `#0ea5e9` - For informational messages

#### Neutral Colors
- **Background**: `#f9fafb` - Light mode background
- **Surface**: `#ffffff` - Card and surface backgrounds
- **Border**: `#e5e7eb` - Border color
- **Primary Text**: `#111827` - Primary text color
- **Secondary Text**: `#6b7280` - Secondary text color

### Typography

#### Font Families
- **Base Font**: `Source Sans Pro` - For text and UI
- **Display Font**: `Poppins` - For headings and titles
- **Monospace Font**: `Source Code Pro` - For code and technical content

#### Font Sizes
- **H1**: 32px (2rem) - Page titles
- **H2**: 24px (1.5rem) - Section headings
- **H3**: 20px (1.25rem) - Subsection headings
- **H4**: 16px (1rem) - Secondary headings
- **Body**: 14px (0.875rem) - Regular text
- **Small**: 12px (0.75rem) - Helper text and labels

#### Font Weights
- **Light**: 300 - Subtle text
- **Regular**: 400 - Body text
- **Medium**: 500 - Emphasis
- **Semibold**: 600 - Headings
- **Bold**: 700 - Strong emphasis

### Spacing

Using a base unit of 4px:
- **xs**: 4px (0.25rem)
- **sm**: 8px (0.5rem)
- **md**: 12px (0.75rem)
- **lg**: 16px (1rem)
- **xl**: 24px (1.5rem)
- **2xl**: 32px (2rem)

### Border Radius

- **sm**: 4px - Small elements
- **md**: 8px - Standard elements
- **lg**: 12px - Large elements
- **xl**: 16px - Extra large elements

## Tailwind CSS Usage

### Class Organization

Organize Tailwind classes in this order:
1. Layout (display, position, flex, grid)
2. Size (width, height, padding, margin)
3. Typography (font, text color, text alignment)
4. Backgrounds (background color, gradients)
5. Borders (border, border-radius, border-color)
6. Effects (shadow, opacity, transform)
7. Transitions (duration, timing, animation)

### Component Example

```tsx
export function DashboardCard({ title, children }) {
  return (
    <div className={cn(
      // Layout
      'flex flex-col',
      // Size
      'p-6 rounded-lg',
      // Typography
      'text-sm font-medium',
      // Backgrounds
      'bg-card',
      // Borders
      'border border-border',
      // Effects
      'shadow-md',
      // Transitions
      'transition-all duration-200 hover:shadow-lg'
    )}>
      <h3 className="text-lg font-semibold mb-4">{title}</h3>
      {children}
    </div>
  );
}
```

## Component Design

### Button Component

```tsx
// Primary button
<button className="bg-primary text-white px-4 py-2 rounded-lg hover:bg-primary/90 transition-colors">
  Click Here
</button>

// Secondary button
<button className="bg-secondary text-white px-4 py-2 rounded-lg hover:bg-secondary/90 transition-colors">
  Cancel
</button>
```

### Card Component

```tsx
<div className="bg-card rounded-lg shadow-md p-6 border border-border">
  <h3 className="text-lg font-semibold text-foreground mb-4">Card Title</h3>
  <p className="text-muted-foreground">Card content</p>
</div>
```

## Dark Mode

The application supports dark mode using Tailwind's `dark:` prefix:

```tsx
<div className="bg-white dark:bg-gray-900 text-gray-900 dark:text-white">
  Content
</div>
```

## Responsive Design

Use Tailwind's responsive prefixes:

```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  {/* Responsive grid */}
</div>
```

### Breakpoints
- **sm**: 640px
- **md**: 768px
- **lg**: 1024px
- **xl**: 1280px
- **2xl**: 1536px

## Animations and Transitions

### Transition Classes

```tsx
// Smooth color transition
<button className="transition-colors duration-200 hover:bg-primary/90">
  Hover me
</button>

// Smooth transform transition
<div className="transition-transform duration-300 hover:scale-105">
  Scale on hover
</div>
```

## Accessibility

### Color Contrast
- Ensure sufficient contrast between text and background
- Follow WCAG AA standards (4.5:1 for regular text)
- Test using contrast checking tools

### Focus States
```tsx
<button className="focus:outline-none focus:ring-2 focus:ring-primary focus:ring-offset-2">
  Accessible button
</button>
```

## Best Practices

1. **Use Tailwind Classes** - Prefer Tailwind over custom CSS
2. **Avoid Inline Styles** - Use classes instead
3. **Use CSS Variables** - For theme colors and spacing
4. **Keep Components Small** - Easier to style and maintain
5. **Test Responsiveness** - Check all breakpoints
6. **Maintain Consistency** - Follow the design system
7. **Document Custom Styles** - Explain non-obvious patterns

## Related Documentation

- [STRUCTURE](./STRUCTURE.md) - Project structure
- [TECHNOLOGIES](./TECHNOLOGIES.md) - Technology stack
- [CONTRIBUTING](./CONTRIBUTING.md) - Contribution guidelines
