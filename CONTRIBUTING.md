# Contributing to Tanqory JavaScript Style Guide

Thank you for your interest in contributing to Tanqory JavaScript Style Guide! We appreciate your time and effort to help improve our project.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [How to Contribute](#how-to-contribute)
- [Pull Request Process](#pull-request-process)
- [Style Guidelines](#style-guidelines)
- [Testing](#testing)
- [Documentation](#documentation)

## Code of Conduct

By participating in this project, you agree to abide by our Code of Conduct:

- Be respectful and inclusive
- Welcome newcomers and help them get started
- Focus on constructive criticism
- Accept feedback gracefully
- Prioritize the community's best interests

## Getting Started

1. **Fork the Repository**: Click the "Fork" button on GitHub
2. **Clone Your Fork**: 
   ```bash
   git clone https://github.com/YOUR_USERNAME/javascript.git
   cd javascript
   ```
3. **Add Upstream Remote**:
   ```bash
   git remote add upstream https://github.com/tanqory/javascript.git
   ```

## Development Setup

### Prerequisites

- Node.js >= 16.0.0
- npm >= 7.0.0
- Git

### Installation

```bash
# Install dependencies
npm install

# Install dependencies for all packages
npm run install:config
npm run install:config:base
```

### Available Scripts

```bash
# Run tests
npm test

# Run linting
npm run lint

# Run specific package tests
npm run test:config        # Test eslint-config
npm run test:config:base   # Test eslint-config-base

# Fix linting issues
npm run lint:fix
```

## How to Contribute

### Reporting Bugs

Before creating a bug report:
1. Check existing issues to avoid duplicates
2. Verify the issue in the latest version
3. Collect relevant information (error messages, environment details)

When reporting:
- Use a clear, descriptive title
- Describe steps to reproduce
- Include expected vs actual behavior
- Add code samples if applicable
- Specify your environment details

### Suggesting Enhancements

For feature requests:
1. Check if it's already suggested
2. Explain the problem it solves
3. Describe your proposed solution
4. Consider alternatives
5. Explain why this benefits users

### Contributing Code

#### For Small Changes (typos, documentation):
1. Make changes directly in your fork
2. Submit a pull request

#### For Larger Changes:
1. Open an issue for discussion first
2. Get feedback from maintainers
3. Implement after approval
4. Submit pull request

## Pull Request Process

### Before Submitting

1. **Update from upstream**:
   ```bash
   git fetch upstream
   git rebase upstream/master
   ```

2. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes**:
   - Follow existing code style
   - Add/update tests
   - Update documentation

4. **Test thoroughly**:
   ```bash
   npm test
   npm run lint
   ```

5. **Commit with meaningful messages**:
   ```bash
   git commit -m "feat: add new rule for array methods"
   ```

### Commit Message Format

We follow Conventional Commits:

```
<type>(<scope>): <subject>

<body>

<footer>
```

Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Test additions or changes
- `chore`: Maintenance tasks

Examples:
```bash
feat(rules): add no-console rule configuration
fix(imports): resolve module resolution issue
docs(readme): update installation instructions
```

### Submitting the PR

1. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

2. **Create Pull Request**:
   - Go to your fork on GitHub
   - Click "New Pull Request"
   - Select your feature branch
   - Fill in the PR template

3. **PR Description Should Include**:
   - What changes were made
   - Why changes were necessary
   - How to test changes
   - Related issue numbers

## Style Guidelines

### JavaScript Code Style

Follow our ESLint configuration:
```javascript
// ✅ Good
const processData = (data = []) => {
  return data.map(item => ({
    ...item,
    processed: true
  }));
};

// ❌ Bad
function processData(data) {
  data = data || [];
  for (var i = 0; i < data.length; i++) {
    data[i].processed = true;
  }
  return data;
}
```

### Documentation Style

- Use clear, concise language
- Include code examples
- Keep line length under 100 characters
- Use proper markdown formatting

## Testing

### Running Tests

```bash
# Run all tests
npm test

# Run specific test file
npm run test -- --grep "specific test"

# Run with coverage
npm run test:coverage
```

### Writing Tests

```javascript
import test from 'tape';
import config from '../index';

test('config: should have rules property', (t) => {
  t.ok(config.rules, 'rules property exists');
  t.equal(typeof config.rules, 'object', 'rules is an object');
  t.end();
});
```

### Test Requirements

- All new features must have tests
- Bug fixes should include regression tests
- Maintain or improve code coverage
- Tests must pass in CI/CD

## Documentation

### Where to Document

1. **Code Comments**: For complex logic
2. **README.md**: For user-facing features
3. **API Documentation**: For public APIs
4. **Migration Guides**: For breaking changes

### Documentation Standards

- Use JSDoc for function documentation:
```javascript
/**
 * Processes array items with given transformer
 * @param {Array} items - Items to process
 * @param {Function} transformer - Transform function
 * @returns {Array} Processed items
 */
const processItems = (items, transformer) => {
  return items.map(transformer);
};
```

## Review Process

### What to Expect

1. **Initial Review**: Within 2-3 business days
2. **Feedback**: Constructive suggestions for improvement
3. **Iterations**: May require changes before approval
4. **Approval**: Requires review from maintainers
5. **Merge**: After CI passes and approval received

### Review Criteria

- Code quality and style compliance
- Test coverage and quality
- Documentation completeness
- Performance impact
- Security considerations
- Backward compatibility

## Release Process

We follow semantic versioning (SemVer):

- **Major** (1.0.0): Breaking changes
- **Minor** (0.1.0): New features, backward compatible
- **Patch** (0.0.1): Bug fixes, backward compatible

Releases are automated through CI/CD when changes are merged to master.

## Getting Help

- 📧 Email: dev@tanqory.com
- 💬 GitHub Discussions: [Ask questions](https://github.com/tanqory/javascript/discussions)
- 🐛 Issues: [Report bugs](https://github.com/tanqory/javascript/issues)

## Recognition

Contributors are recognized in:
- GitHub contributors page
- Release notes
- Special mentions for significant contributions

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to Tanqory JavaScript Style Guide! 🎉