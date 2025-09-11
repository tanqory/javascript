# @tanqory/eslint-config-base

[![npm version](https://badge.fury.io/js/%40tanqory%2Feslint-config-base.svg)](https://www.npmjs.com/package/@tanqory/eslint-config-base)
[![Downloads](https://img.shields.io/npm/dm/@tanqory/eslint-config-base.svg)](https://www.npmjs.com/package/@tanqory/eslint-config-base)

This package provides Tanqory's base JavaScript ESLint configuration (without React plugins) as an extensible shared config.

## Installation

```bash
npm install --save-dev @tanqory/eslint-config-base
```

### Peer Dependencies

```bash
npm install --save-dev eslint@^8.2.0 eslint-plugin-import@^2.30.0
```

## Usage

Add to your `.eslintrc.json`:

```json
{
  "extends": "@tanqory/eslint-config-base"
}
```

### Using with TypeScript

```json
{
  "extends": [
    "@tanqory/eslint-config-base",
    "plugin:@typescript-eslint/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "plugins": ["@typescript-eslint"]
}
```

## What's Included?

This configuration includes:

- **ECMAScript 2022+ Support**: Modern JavaScript features
- **Best Practices**: Enforce good coding patterns
- **Error Prevention**: Catch common mistakes
- **Import/Export Rules**: Module system best practices
- **Node.js Support**: Optimized for Node.js environments

### Rule Categories

1. **Best Practices** (`rules/best-practices.js`)
   - Enforce return statements in callbacks
   - Require default case in switch statements
   - Disallow eval() and implied eval
   - Require strict equality operators

2. **Possible Errors** (`rules/errors.js`)
   - Disallow assignment in conditional expressions
   - Disallow duplicate case labels
   - Disallow empty statements
   - Disallow irregular whitespace

3. **Node.js and CommonJS** (`rules/node.js`)
   - Disallow new operators with requires
   - Enforce error handling in callbacks
   - Disallow process.exit()

4. **Stylistic Issues** (`rules/style.js`)
   - Enforce consistent naming conventions
   - Require trailing commas
   - Enforce consistent indentation (2 spaces)
   - Maximum line length of 100 characters

5. **Variables** (`rules/variables.js`)
   - Disallow delete of variables
   - Disallow unused variables
   - Disallow use before define

6. **ES6+** (`rules/es6.js`)
   - Require const for never reassigned variables
   - Disallow var, use let/const instead
   - Enforce arrow function conventions
   - Template literals instead of string concatenation

## Customizing Rules

You can override any rule in your `.eslintrc.json`:

```json
{
  "extends": "@tanqory/eslint-config-base",
  "rules": {
    "no-console": "off",
    "max-len": ["error", { "code": 120 }]
  }
}
```

## Alternative Configurations

### Legacy ES5

For legacy projects using ES5:

```json
{
  "extends": "@tanqory/eslint-config-base/legacy"
}
```

### Whitespace Rules Only

For projects that only want whitespace rules:

```json
{
  "extends": "@tanqory/eslint-config-base/whitespace"
}
```

## Development

```bash
# Clone the repository
git clone https://github.com/tanqory/javascript.git
cd javascript/packages/eslint-config-airbnb-base

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
- [NPM Package](https://www.npmjs.com/package/@tanqory/eslint-config-base)
- [Issue Tracker](https://github.com/tanqory/javascript/issues)