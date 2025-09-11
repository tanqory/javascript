# @tanqory/eslint-config

[![npm version](https://badge.fury.io/js/%40tanqory%2Feslint-config.svg)](https://www.npmjs.com/package/@tanqory/eslint-config)
[![Downloads](https://img.shields.io/npm/dm/@tanqory/eslint-config.svg)](https://www.npmjs.com/package/@tanqory/eslint-config)

This package provides Tanqory's ESLint configuration with React support as an extensible shared config.

## Installation

```bash
npm install --save-dev @tanqory/eslint-config
```

### Peer Dependencies

```bash
npm install --save-dev \
  eslint@^8.2.0 \
  eslint-plugin-import@^2.30.0 \
  eslint-plugin-jsx-a11y@^6.10.0 \
  eslint-plugin-react@^7.36.1 \
  eslint-plugin-react-hooks@^5.1.0
```

## Usage

Add to your `.eslintrc.json`:

```json
{
  "extends": "@tanqory/eslint-config"
}
```

### Using with Next.js

```json
{
  "extends": [
    "@tanqory/eslint-config",
    "next/core-web-vitals"
  ],
  "rules": {
    "react/react-in-jsx-scope": "off"
  }
}
```

### Using with TypeScript

```json
{
  "extends": [
    "@tanqory/eslint-config",
    "plugin:@typescript-eslint/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"],
  "settings": {
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

## What's Included?

This configuration extends `@tanqory/eslint-config-base` and adds:

- **React Support**: Best practices for React development
- **React Hooks**: Rules for proper hooks usage
- **JSX Accessibility**: Ensure accessible React components
- **Import Validation**: React-specific import rules

### React-Specific Rules

1. **React Best Practices** (`rules/react.js`)
   - Enforce prop types validation
   - Prevent missing key props in iterators
   - Enforce JSX boolean value notation
   - Prevent direct state mutation

2. **React Hooks** (`rules/react-hooks.js`)
   - Rules of Hooks enforcement
   - Exhaustive dependencies check
   - Custom hooks naming convention

3. **JSX Accessibility** (`rules/react-a11y.js`)
   - Alt text for images
   - ARIA roles validation
   - Interactive element accessibility
   - Label associations for form controls

## Alternative Configurations

### Without React Hooks

For projects not using React Hooks:

```json
{
  "extends": "@tanqory/eslint-config/base"
}
```

### Hooks Only

For projects that only want React Hooks rules:

```json
{
  "extends": "@tanqory/eslint-config/hooks"
}
```

### Legacy

For legacy projects:

```json
{
  "extends": "@tanqory/eslint-config/legacy"
}
```

## Customizing Rules

You can override any rule in your `.eslintrc.json`:

```json
{
  "extends": "@tanqory/eslint-config",
  "rules": {
    "react/prop-types": "off",
    "react/jsx-filename-extension": ["error", { "extensions": [".js", ".jsx", ".ts", ".tsx"] }]
  }
}
```

## React Version

Specify your React version in `.eslintrc.json`:

```json
{
  "extends": "@tanqory/eslint-config",
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```

## Example Configurations

### Create React App

```json
{
  "extends": "@tanqory/eslint-config",
  "env": {
    "browser": true,
    "es2022": true
  }
}
```

### React Native

```json
{
  "extends": "@tanqory/eslint-config",
  "env": {
    "react-native/react-native": true
  },
  "plugins": ["react-native"],
  "rules": {
    "react-native/no-unused-styles": "error",
    "react-native/no-inline-styles": "warn"
  }
}
```

### Gatsby

```json
{
  "extends": [
    "@tanqory/eslint-config",
    "plugin:gatsby/recommended"
  ]
}
```

## Development

```bash
# Clone the repository
git clone https://github.com/tanqory/javascript.git
cd javascript/packages/eslint-config-airbnb

# Install dependencies
npm install

# Run tests
npm test

# Run linting
npm run lint
```

## License

MIT © Tanqory

## Links

- [Main Documentation](https://github.com/tanqory/javascript)
- [NPM Package](https://www.npmjs.com/package/@tanqory/eslint-config)
- [Issue Tracker](https://github.com/tanqory/javascript/issues)