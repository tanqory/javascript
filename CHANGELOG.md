# Changelog

All notable changes to the Tanqory JavaScript Style Guide will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2024-01-11

### Added
- 🎉 Initial release as Tanqory JavaScript Style Guide
- 📦 Published packages under @tanqory scope
  - `@tanqory/eslint-config` - Full ESLint config with React support
  - `@tanqory/eslint-config-base` - Base ESLint config for Node.js/vanilla JS
- 🚀 Modern JavaScript support (ES2022+)
  - Optional chaining (`?.`)
  - Nullish coalescing (`??`)
  - Private class fields
  - Top-level await
  - Logical assignment operators
- 📚 Comprehensive documentation
  - Migration guide from Airbnb config
  - IDE integration instructions
  - CI/CD setup examples
  - TypeScript integration guide
- ⚡ Performance optimizations
  - ESLint caching support
  - Optimized rule configurations
- 🔧 Developer experience improvements
  - Detailed error messages
  - Auto-fix capabilities for most rules
  - Better import/export validation

### Changed
- 📦 Package naming from `eslint-config-airbnb` to `@tanqory/eslint-config`
- 🔄 Updated minimum Node.js version to 16.0.0
- 📝 Modernized documentation with better examples
- ⬆️ Updated ESLint support to 8.2.0+ and 9.0.0
- 🎨 Improved code style recommendations for modern JavaScript

### Fixed
- 🐛 Missing dependency issues
- 🔧 Deprecated package warnings
- 📝 Documentation typos and broken links

### Security
- 🔒 Updated all dependencies to latest secure versions
- 🛡️ Added security scanning in CI/CD pipeline

## Migration from Airbnb Config

If you're upgrading from the original Airbnb config:

1. **Update package.json**:
```json
// Old
"eslint-config-airbnb": "^19.0.4"
"eslint-config-airbnb-base": "^15.0.0"

// New
"@tanqory/eslint-config": "^1.0.0"
"@tanqory/eslint-config-base": "^1.0.0"
```

2. **Update .eslintrc.json**:
```json
// Old
{ "extends": "airbnb" }

// New
{ "extends": "@tanqory/eslint-config" }
```

3. **Run the update**:
```bash
npm uninstall eslint-config-airbnb eslint-config-airbnb-base
npm install --save-dev @tanqory/eslint-config
npm run lint:fix
```

---

## Previous History (as Airbnb Config)

For the complete history before the Tanqory fork, see [README.original.md](README.original.md)

### Notable Previous Versions

- **19.0.4** - Last version as eslint-config-airbnb
- **15.0.0** - Last version as eslint-config-airbnb-base
- Multiple years of community contributions and improvements

## Acknowledgments

This project builds upon the excellent foundation created by the Airbnb team and the JavaScript community. We're grateful for their work in establishing these coding standards.