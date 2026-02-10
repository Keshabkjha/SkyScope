# Contributing to SkyScope

Thank you for your interest in contributing to SkyScope! This document provides guidelines and information for contributors.

## 🤝 How to Contribute

We welcome contributions of all kinds, including:

- 🐛 **Bug fixes**
- ✨ **New features**
- 📚 **Documentation improvements**
- 🧪 **Test coverage**
- 🎨 **UI/UX enhancements**
- ⚡ **Performance optimizations**

## 🚀 Getting Started

### Prerequisites

- Node.js 18.0 or higher
- npm or yarn package manager
- Git
- Basic knowledge of React, TypeScript, and modern web development

### Development Setup

1. **Fork the repository**
   ```bash
   # Fork the repository on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/SkyScope.git
   cd SkyScope
   ```

2. **Add the original repository as upstream**
   ```bash
   git remote add upstream https://github.com/Keshabkjha/SkyScope.git
   ```

3. **Install dependencies**
   ```bash
   npm install
   ```

4. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

5. **Set up environment variables**
   ```bash
   cp .env.example .env.local
   # Add your API keys and configuration
   ```

6. **Start the development server**
   ```bash
   npm run dev
   ```

## 📋 Development Workflow

### 1. Before You Start

- Check existing [issues](../../issues) and [pull requests](../../pulls) to avoid duplicates
- Read the project documentation and understand the codebase
- Join our [Discussions](../../discussions) to ask questions or propose ideas

### 2. Making Changes

#### Code Style

We use the following tools and standards:

- **TypeScript** for type safety
- **ESLint** for code linting (when configured)
- **Prettier** for code formatting (when configured)
- **Conventional Commits** for commit messages

#### Commit Message Format

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

```
type(scope): description

[optional body]

[optional footer]
```

Examples:
```
feat(weather): add 7-day forecast feature
fix(chat): resolve message display issue on mobile
docs(readme): update installation instructions
```

#### Types of Commits

- `feat`: New features
- `fix`: Bug fixes
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### 3. Testing

Before submitting your pull request:

1. **Run the development server** and test your changes manually
2. **Check for TypeScript errors**:
   ```bash
   npm run type-check
   ```
3. **Run tests** (when implemented):
   ```bash
   npm run test
   ```
4. **Test on different browsers** and screen sizes
5. **Ensure accessibility** standards are met

### 4. Submitting Your Changes

1. **Commit your changes** with clear, descriptive messages
2. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```
3. **Create a Pull Request** with:
   - Clear title and description
   - Reference to related issues
   - Screenshots for UI changes
   - Testing instructions

## 🏗️ Project Structure

```
SkyScope/
├── components/          # React components
│   ├── ChatBubble.tsx  # Chat message component
│   └── WeatherMap.tsx  # Weather map component
├── services/           # API services
│   └── geminiService.ts # Google AI integration
├── types.ts           # TypeScript type definitions
├── App.tsx            # Main application component
├── index.tsx          # Application entry point
└── vite.config.ts     # Vite configuration
```

### Component Guidelines

- Use functional components with hooks
- Follow React best practices
- Implement proper TypeScript types
- Add comments for complex logic
- Consider accessibility (ARIA labels, keyboard navigation)

### Service Guidelines

- Use async/await for API calls
- Implement proper error handling
- Add loading states and error messages
- Cache responses when appropriate

## 🎯 Coding Standards

### TypeScript

- Use strict mode
- Define interfaces for all data structures
- Avoid `any` type when possible
- Use proper generics when needed

### React

- Use functional components and hooks
- Follow the Rules of Hooks
- Implement proper prop types with TypeScript
- Use memoization for performance when needed

### CSS/Styling

- Use consistent naming conventions
- Implement responsive design
- Follow mobile-first approach
- Use CSS variables for theming

## 🐛 Bug Reports

When reporting bugs, please include:

1. **Clear description** of the issue
2. **Steps to reproduce** the problem
3. **Expected vs actual behavior**
4. **Environment details** (browser, OS, etc.)
5. **Screenshots** or screen recordings if applicable
6. **Console errors** (if any)

Use our [bug report template](.github/ISSUE_TEMPLATE/bug_report.md) for consistency.

## ✨ Feature Requests

For feature requests:

1. **Check existing issues** first
2. **Provide clear description** of the feature
3. **Explain the use case** and benefits
4. **Consider implementation complexity**
5. **Offer to contribute** if possible

Use our [feature request template](.github/ISSUE_TEMPLATE/feature_request.md).

## 📖 Documentation

We appreciate documentation improvements:

- **README.md**: Project overview and setup
- **Code comments**: Complex logic explanations
- **API documentation**: Service and component interfaces
- **User guides**: Feature usage instructions

## 🔍 Code Review Process

### What We Look For

- **Functionality**: Does the code work as intended?
- **Code Quality**: Is it clean, readable, and maintainable?
- **Performance**: Are there any performance implications?
- **Security**: Are there any security concerns?
- **Testing**: Is the code properly tested?
- **Documentation**: Is the code well-documented?

### Review Guidelines

- Be constructive and respectful
- Provide specific, actionable feedback
- Explain the reasoning behind suggestions
- Acknowledge good work and improvements

## 🎉 Recognition

Contributors are recognized in:

- **README.md**: Contributors section
- **Release notes**: Feature credits
- **GitHub contributors**: Automatic attribution
- **Community highlights**: Outstanding contributions

## 📞 Getting Help

- **GitHub Discussions**: General questions and ideas
- **Issues**: Bug reports and feature requests
- **Email**: support@skyscope.dev (for maintainers)

## 📄 License

By contributing to SkyScope, you agree that your contributions will be licensed under the [MIT License](LICENSE).

---

Thank you for contributing to SkyScope! Your contributions help make this project better for everyone. 🌟
