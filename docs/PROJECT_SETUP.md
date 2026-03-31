# Project Setup Guide

This guide provides detailed instructions for setting up the development environment for Dashboard Hub.

## Prerequisites

Before getting started, ensure you have the following installed:

- **Node.js** (version 16 or higher) - [Download](https://nodejs.org/)
- **npm** (version 7 or higher) - Comes with Node.js
- **Git** - [Download](https://git-scm.com/)
- Code editor (VS Code recommended) - [Download](https://code.visualstudio.com/)

## Installation Steps

### 1. Clone the Repository

```bash
git clone https://github.com/Mostafa-SAID7/Dashboard-hub.git
cd Dashboard-hub
```

### 2. Install Dependencies

```bash
npm install
```

All required dependencies listed in `package.json` will be installed.

### 3. Set Up Environment Variables

Create a `.env.local` file in the root directory (if needed):

```env
VITE_API_URL=http://localhost:3000
VITE_APP_NAME=Dashboard Hub
```

### 4. Run the Development Server

```bash
npm run dev
```

The application will be available at `http://localhost:8080`

## Development Workflow

### Run Development Server

```bash
npm run dev
```

The development server includes:
- Hot Module Replacement (HMR)
- Fast React component reloading
- Source maps for debugging

### Build for Production

```bash
npm run build
```

Creates an optimized production build in the `dist` folder.

### Preview Production Build

```bash
npm run preview
```

Allows you to preview the production build locally before deployment.

### Code Quality Checks

```bash
npm run lint
```

Runs ESLint to check for code quality issues.

## Project Structure

```
Dashboard-hub/
├── src/
│   ├── components/        # Reusable components
│   ├── pages/            # Page components
│   ├── types/            # TypeScript definitions
│   ├── lib/              # Helper functions
│   ├── App.tsx           # Main component
│   ├── App.css           # Global styles
│   └── main.tsx          # Entry point
├── public/               # Static files
├── docs/                 # Documentation
├── index.html            # HTML template
├── vite.config.ts        # Vite configuration
├── tailwind.config.ts    # Tailwind CSS configuration
├── tsconfig.json         # TypeScript configuration
└── package.json          # Dependencies and scripts
```

## Configuration Files

### vite.config.ts
Vite configuration for development and production builds.

### tailwind.config.ts
Tailwind CSS configuration for styling.

### tsconfig.json
TypeScript compiler options and settings.

### package.json
Project metadata and dependencies.

## Troubleshooting

### Port Already in Use

If port 8080 is already in use:

```bash
npm run dev -- --port 3000
```

### Dependency Installation Issues

If you encounter issues installing dependencies:

```bash
# Clear npm cache
npm cache clean --force

# Delete node_modules and package-lock.json
rm -rf node_modules package-lock.json

# Reinstall dependencies
npm install
```

### Build Errors

If you encounter build errors:

1. Verify all dependencies are installed: `npm install`
2. Clear build cache: `rm -rf dist`
3. Try building again: `npm run build`

## Code Editor Setup

### Recommended VS Code Extensions

- **ES7+ React/Redux/React-Native snippets** - dsznajder.es7-react-js-snippets
- **Tailwind CSS IntelliSense** - bradlc.vscode-tailwindcss
- **TypeScript Vue Plugin** - Vue.volar
- **ESLint** - dbaeumer.vscode-eslint
- **Prettier** - esbenp.prettier-vscode

### VS Code Settings

Create `.vscode/settings.json`:

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

## Next Steps

1. Read the [STRUCTURE](./STRUCTURE.md) guide to understand project organization
2. Review [TECHNOLOGIES](./TECHNOLOGIES.md) for tech stack details
3. Check [CONTRIBUTING](./CONTRIBUTING.md) for contribution guidelines
4. Explore [FEATURES](./FEATURES.md) documentation

## Support

For issues or questions, please contact the development team.
