# GIT WORKFLOW GUIDE

## Branch Strategy (Git Flow)

This project uses Git Flow workflow with the following branch structure:

### Main Branches

#### `main` (Production)
- Contains production-ready code
- Only receives merges from `release/*` or `hotfix/*` branches
- Tagged with version numbers (v1.0.0, v1.0.1, etc.)

#### `develop` (Development)
- Contains the latest development changes
- Base branch for feature development
- Code here is tested but may not be production-ready

### Supporting Branches

#### Feature Branches (`feature/*`)
- **Created from:** `develop`
- **Merged back into:** `develop`
- **Naming convention:** `feature/feature-name` or `feature/JIRA-123-feature-name`

Examples:
- `feature/user-authentication`
- `feature/jira-sync`
- `feature/notification-system`

#### Bugfix Branches (`bugfix/*`)
- **Created from:** `develop`
- **Merged back into:** `develop`
- **Naming convention:** `bugfix/issue-name` or `bugfix/JIRA-456-issue-name`

Examples:
- `bugfix/issue-tracking`
- `bugfix/login-error`

#### Release Branches (`release/*`)
- **Created from:** `develop`
- **Merged back into:** `main` and `develop`
- **Naming convention:** `release/v1.0.0`

#### Hotfix Branches (`hotfix/*`)
- **Created from:** `main`
- **Merged back into:** `main` and `develop`
- **Naming convention:** `hotfix/v1.0.1` or `hotfix/critical-bug`

---

## Workflow Steps

### Creating a Feature Branch

```bash
# Update develop branch
git checkout develop
git pull origin develop

# Create feature branch
git checkout -b feature/my-feature

# Make your changes
# ... edit files ...

# Commit changes
git add .
git commit -m "feat: Add my feature"

# Push to remote
git push -u origin feature/my-feature
```

### Creating a Pull Request

1. Push your branch to remote
2. Go to GitHub repository
3. Click "New Pull Request"
4. Select:
   - Base: `develop` (for features) or `main` (for releases/hotfixes)
   - Compare: your feature branch
5. Fill in the PR template with:
   - Clear description
   - Related issues
   - Testing done
   - Checklist completion
6. Request reviewers
7. Wait for approval and CI/CD checks

### Reviewing a Pull Request

Reviewers should check:
- [ ] Code quality and style
- [ ] Test coverage
- [ ] No breaking changes
- [ ] Documentation updated
- [ ] Commits are meaningful

### Merging a Pull Request

```bash
# After approval, merge to develop/main
git checkout develop
git pull origin develop
git merge --no-ff feature/my-feature
git push origin develop

# Delete feature branch
git branch -d feature/my-feature
git push origin --delete feature/my-feature
```

---

## Commit Message Convention

Use conventional commits for clear history:

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation
- `style`: Code style (no logic change)
- `refactor`: Code refactoring
- `test`: Adding tests
- `chore`: Build/dependency changes

### Examples:
```
feat(auth): Add user login functionality
fix(jira-sync): Resolve issue sync timeout
docs: Update installation instructions
test(api): Add integration tests
```

---

## Current Branches

### Feature Branches
- `feature/user-authentication` - User login and token management
- `feature/jira-sync` - Jira issue synchronization
- `feature/notification-system` - Email and in-app notifications

### Bugfix Branches
- `bugfix/issue-tracking` - Issue tracking reliability improvements

### Release Branches
- (None at this time)

### Hotfix Branches
- (None at this time)

---

## Best Practices

1. **Keep branches focused** - One feature per branch
2. **Keep branches short-lived** - Merge within 1-2 weeks
3. **Write descriptive commits** - Use conventional commits
4. **Add tests** - Include unit/integration tests
5. **Update documentation** - Keep README and docs in sync
6. **Request reviews** - Get peer feedback before merging
7. **Use `--no-ff` flag** - Preserve branch history

---

## Common Commands

```bash
# List all branches
git branch -a

# View branch tree
git log --graph --decorate --oneline --all

# Delete local branch
git branch -d branch-name

# Delete remote branch
git push origin --delete branch-name

# Rename branch
git branch -m old-name new-name

# Rebase feature branch on develop
git checkout feature/my-feature
git rebase develop

# Interactive rebase last 3 commits
git rebase -i HEAD~3
```

---

## Troubleshooting

### Merge Conflicts

```bash
# Check conflicts
git status

# Resolve conflicts manually in your editor
# Then:
git add .
git commit -m "resolve: Merge conflicts"
git push origin branch-name
```

### Accidentally Committed to Main?

```bash
git reset HEAD~1
git stash
git checkout -b feature/my-feature
git stash pop
git push -u origin feature/my-feature
```

### Need to Update Feature Branch from Develop?

```bash
git checkout feature/my-feature
git fetch origin
git rebase origin/develop
git push -f origin feature/my-feature
```

---

## Resources

- [Git Flow Cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Pull Request Best Practices](https://docs.github.com/en/pull-requests)
