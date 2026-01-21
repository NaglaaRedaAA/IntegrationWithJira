# Integration with Jira

A sample project demonstrating Git workflow with branches, pull requests, and Jira integration.

## Project Structure

```
├── src/
│   ├── index.js           - Main application entry point
│   └── jira-connector.js  - Jira API connector module
├── package.json           - Project dependencies
├── .gitignore            - Git ignore rules
└── README.md             - This file
```

## Getting Started

### Installation

```bash
npm install
```

### Running the Application

```bash
npm start
```

### Development Mode

```bash
npm run dev
```

### Build

```bash
npm run build
```

## Git Workflow

This project demonstrates a complete Git workflow with the following branches:

### Main Branches

- **main** - Production-ready code
- **develop** - Development branch

### Feature Branches

- **feature/user-authentication** - User login and authentication
- **feature/jira-sync** - Jira synchronization feature
- **feature/notification-system** - Notification system implementation
- **bugfix/issue-tracking** - Bug fixes for issue tracking

## Pull Request Examples

Pull requests demonstrate:
- Code reviews
- Branch protection rules
- CI/CD pipeline checks
- Merge strategies

## Jira Integration

The project includes a `JiraConnector` class that handles:
- Fetching issues
- Updating issues
- Creating new issues

## Contributing

1. Create a feature branch from `develop`
2. Make your changes
3. Create a pull request for code review
4. After approval, merge to `develop`
5. When ready for release, merge `develop` to `main`

## License

ISC
