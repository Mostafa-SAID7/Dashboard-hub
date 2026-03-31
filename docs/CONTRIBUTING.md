# Contributing Guidelines

Thank you for your interest in contributing to Dashboard Hub! We welcome contributions from everyone.

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/your-username/Dashboard-hub.git
   cd Dashboard-hub
   ```
3. Add the upstream repository:
   ```bash
   git remote add upstream https://github.com/Mostafa-SAID7/Dashboard-hub.git
   ```
4. Create a new branch for your work:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Development Setup

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the development server:
   ```bash
   npm run dev
   ```

3. Make changes and test them locally

## Code Standards

### TypeScript
- Use TypeScript for all new code
- Specify proper types for all functions and components
- Avoid using the `any` type
- Use interfaces for object shapes

### React Components
- Use functional components with hooks
- Keep components small and focused
- Use meaningful component names
- Add PropTypes or TypeScript interfaces

### Naming Conventions
- Components: PascalCase (e.g., `Dashboard`)
- Functions: camelCase (e.g., `getDashboardData`)
- Constants: UPPER_SNAKE_CASE (e.g., `MAX_DASHBOARDS`)
- Files: Match the exported component name

### Code Style
- Use 2 spaces for indentation
- Use single quotes for strings
- Use semicolons at the end of statements
- Use arrow functions for callbacks
- Keep lines under 100 characters when possible

### Comments
- Write clear and concise comments
- Explain "why", not "what"
- Use JSDoc for functions and components
- Keep comments updated with code changes

## Commit Guidelines

### Commit Messages
Follow conventional commit format:

```
type(scope): subject

body

footer
```

**Types:**
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `style`: Style changes
- `refactor`: Code refactoring
- `perf`: Performance improvements
- `test`: Adding or updating tests
- `chore`: Build and library updates

**Examples:**
```
feat(dashboard): add new chart widget
fix(auth): correct login validation
docs(readme): update installation instructions
```

### Commit Best Practices
- Make commits small and focused
- Commit regularly
- Write descriptive commit messages
- Don't commit sensitive information
- Review changes before committing

## Pull Request Process

1. Update your branch with the latest changes:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

2. Push your changes to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

3. Create a pull request on GitHub with:
   - A clear title describing the changes
   - A detailed description of what changed and why
   - References to any related issues
   - Screenshots for UI changes

4. Ensure all checks pass:
   - Code quality checks (ESLint)
   - Type checking (TypeScript)
   - Tests (if applicable)

5. Address any review comments
6. Wait for approval from maintainers

## Testing

### Running Tests
```bash
npm run test
```

### Writing Tests
- Write tests for new features
- Aim for high code coverage
- Test edge cases and errors
- Use descriptive test names

### Code Quality
```bash
npm run lint
```

Fix any linting issues before submitting a pull request.

## Documentation

- Update README.md if you add new features
- Add comments for complex code
- Update related documentation files
- Provide examples for new features

## Types of Contributions

### Bug Reports
- Use the bug report template
- Include steps to reproduce
- Provide expected vs actual behavior
- Attach screenshots if possible

### Feature Requests
- Use the feature request template
- Explain the use case
- Describe the expected behavior
- Provide examples if possible

### Documentation
- Fix typos and improve clarity
- Add missing documentation
- Provide examples
- Update outdated information

### Code Improvements
- Refactor for better readability
- Improve performance
- Reduce code duplication
- Add type safety

## Review Process

### What Reviewers Look For
- Code quality and style
- Adherence to project standards
- Proper error handling
- Performance considerations
- Security implications
- Test coverage
- Documentation completeness

### Responding to Reviews
- Be open to feedback
- Ask questions if unclear
- Make requested changes
- Explain your reasoning if you disagree
- Thank reviewers for their time

## License

By contributing to this project, you agree that your contributions will be licensed under the same license as the project.

## Code of Conduct

Please note that this project is governed by our [Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you agree to abide by its terms.

## Questions?

If you have questions about contributing:
- Check the existing documentation
- Search for similar issues
- Ask in discussions
- Contact us

Thank you for contributing to Dashboard Hub!
