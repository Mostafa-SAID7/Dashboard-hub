# Project Structure

This document describes the organization and structure of the Dashboard Hub project.

## Directory Layout

```
Dashboard-hub/
├── src/
│   ├── components/
│   │   ├── ui/              # shadcn-ui components
│   │   ├── layout/          # Layout components
│   │   ├── dashboard/       # Dashboard-specific components
│   │   └── common/          # Common reusable components
│   ├── pages/
│   │   ├── Dashboard.tsx    # Main dashboard page
│   │   ├── Analytics.tsx    # Analytics page
│   │   ├── Settings.tsx     # Settings page
│   │   └── NotFound.tsx     # 404 page
│   ├── types/
│   │   ├── index.ts         # Type definitions
│   │   ├── dashboard.ts     # Dashboard types
│   │   └── api.ts           # API types
│   ├── lib/
│   │   ├── utils.ts         # Utility functions
│   │   ├── api.ts           # API client
│   │   └── constants.ts     # Constants
│   ├── hooks/
│   │   ├── useDashboard.ts  # Dashboard hook
│   │   └── useAuth.ts       # Authentication hook
│   ├── App.tsx              # Main App component
│   ├── App.css              # Global styles
│   ├── index.css            # Tailwind imports
│   └── main.tsx             # Application entry point
├── public/
│   ├── logo.svg             # Application logo
│   └── favicon.ico          # Favicon
├── docs/                    # Documentation
├── .vscode/                 # VS Code settings
├── index.html               # HTML template
├── vite.config.ts           # Vite configuration
├── tailwind.config.ts       # Tailwind CSS configuration
├── tsconfig.json            # TypeScript configuration
├── tsconfig.app.json        # App TypeScript configuration
├── tsconfig.node.json       # Node TypeScript configuration
├── eslint.config.js         # ESLint configuration
├── postcss.config.js        # PostCSS configuration
├── package.json             # Dependencies and scripts
├── package-lock.json        # Dependency lock file
├── README.md                # Project README
└── .gitignore               # Git ignore rules
```

## Component Organization

### UI Components (`src/components/ui/`)
Reusable UI components from shadcn-ui and custom components:
- Buttons, inputs, forms
- Cards, modals, dialogs
- Navigation components
- Data display components

### Layout Components (`src/components/layout/`)
Layout-related components:
- Header/Navbar
- Sidebar
- Footer
- Main layout wrapper

### Dashboard Components (`src/components/dashboard/`)
Dashboard-specific components:
- Dashboard cards
- Charts and graphs
- Metrics display
- Data tables

### Common Components (`src/components/common/`)
Commonly used components:
- Loading spinners
- Error boundaries
- Empty states
- Notifications

## Pages Organization

Each page represents a route in the application:
- **Dashboard** - Main dashboard view
- **Analytics** - Analytics and reporting
- **Settings** - User and app settings
- **NotFound** - 404 error page

## Types Organization

TypeScript type definitions organized by domain:
- **index.ts** - Common types
- **dashboard.ts** - Dashboard-related types
- **api.ts** - API response types

## Utilities and Hooks

### Utilities (`src/lib/`)
- **utils.ts** - General utility functions
- **api.ts** - API client and requests
- **constants.ts** - Application constants

### Hooks (`src/hooks/`)
- **useDashboard.ts** - Dashboard data management
- **useAuth.ts** - Authentication logic

## Styling

### Global Styles
- **index.css** - Tailwind CSS imports and global styles
- **App.css** - Application-level styles

### Component Styles
- Tailwind CSS classes in components
- CSS modules for component-specific styles (if needed)

## Configuration Files

### Build Configuration
- **vite.config.ts** - Vite build tool configuration
- **tsconfig.json** - TypeScript configuration
- **postcss.config.js** - PostCSS configuration

### Code Quality
- **eslint.config.js** - ESLint rules
- **.vscode/settings.json** - VS Code settings

### Package Management
- **package.json** - Dependencies and scripts
- **package-lock.json** - Locked dependency versions

## File Naming Conventions

- **Components**: PascalCase (e.g., `Dashboard.tsx`)
- **Utilities**: camelCase (e.g., `utils.ts`)
- **Types**: PascalCase (e.g., `Dashboard.ts`)
- **Hooks**: camelCase with `use` prefix (e.g., `useDashboard.ts`)
- **Constants**: UPPER_SNAKE_CASE (e.g., `API_URL`)

## Import Paths

Use path aliases for cleaner imports:
```typescript
// Instead of:
import { Button } from '../../../components/ui/Button'

// Use:
import { Button } from '@/components/ui/Button'
```

Path alias `@` is configured in `vite.config.ts` and `tsconfig.json`.

## Related Documentation

- [TECHNOLOGIES](./TECHNOLOGIES.md) - Technology stack
- [PROJECT_SETUP](./PROJECT_SETUP.md) - Setup instructions
- [CONTRIBUTING](./CONTRIBUTING.md) - Contribution guidelines
