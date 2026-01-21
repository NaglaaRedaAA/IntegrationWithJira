# Sample Project - Branches & Pull Requests Example

## 📋 Project Overview

This is a complete sample project demonstrating a professional Git workflow with multiple branches, pull requests, and best practices.

## 🌿 Branch Structure

### Current Branches

```
main
  └─ (Production branch - v1.0.0)

develop
  ├─ feature/user-authentication
  ├─ feature/jira-sync
  ├─ feature/notification-system
  └─ bugfix/issue-tracking
```

### Branch Details

| Branch | Type | Status | Purpose |
|--------|------|--------|---------|
| `main` | Main | ✅ Stable | Production-ready code |
| `develop` | Main | 🔄 Active | Development base branch |
| `feature/user-authentication` | Feature | 🚀 Ready for PR | User login and auth tokens |
| `feature/jira-sync` | Feature | 🚀 Ready for PR | Jira issue synchronization |
| `feature/notification-system` | Feature | 🚀 Ready for PR | Email & in-app notifications |
| `bugfix/issue-tracking` | Bugfix | 🚀 Ready for PR | Issue tracking reliability |

## 📁 Project Structure

```
IntegrationWithJira/
├── src/
│   ├── index.js                  - Main entry point
│   ├── jira-connector.js         - Jira API connector
│   ├── auth-module.js            - User authentication
│   ├── jira-sync.js              - Issue synchronization
│   ├── notification-system.js    - Notification handling
│   └── issue-tracker.js          - Issue tracking
├── .github/
│   └── pull_request_template.md  - PR template
├── package.json                  - Project dependencies
├── README.md                     - Project documentation
├── GIT_WORKFLOW.md               - Git workflow guide
└── .gitignore                    - Git ignore rules
```

## 🚀 How to Use This Sample

### 1. View All Branches

```bash
# List all local branches
git branch

# List all branches (local + remote)
git branch -a

# View branch tree with commit history
git log --graph --decorate --oneline --all
```

### 2. Create Pull Requests

To create a pull request for any feature branch:

```bash
# Push branch to remote
git push -u origin feature/user-authentication

# Go to GitHub and create PR:
# - Base: develop
# - Compare: feature/user-authentication
# - Fill in PR template
```

### 3. Switch Between Branches

```bash
# Switch to a branch
git checkout feature/user-authentication

# Or use newer syntax
git switch develop

# Create and switch to new branch
git checkout -b feature/new-feature
```

### 4. View Branch Information

```bash
# Show branches with last commit message
git branch -v

# Show merged branches
git branch --merged

# Show unmerged branches
git branch --no-merged
```

## 📝 Commit History

### Main Branch
- **44ee07f** - Initial commit: Setup project structure with Jira connector module

### Feature: User Authentication
- **a8a224e** - feat: Add user authentication module with login and token verification

### Feature: Jira Sync
- **b471b64** - feat: Implement Jira sync module for issue synchronization

### Feature: Notification System
- **f522857** - feat: Add notification system with email and in-app alerts

### Bugfix: Issue Tracking
- **57463ae** - fix: Resolve issue tracking status update bug and improve tracking reliability

### Develop Branch
- **2415223** - docs: Add PR template and Git workflow documentation

## 📖 Pull Request Examples

### PR Example 1: Feature/User Authentication

**Title:** Add user authentication module  
**Base:** develop  
**Compare:** feature/user-authentication  
**Description:**
```
## Description
Implements user authentication system with JWT token support.

## Changes
- Added login/logout functionality
- Implemented token generation and validation
- Added token verification middleware

## Related Issues
Fixes #123

## Testing
- [x] Login with valid credentials
- [x] Reject invalid credentials
- [x] Token validation works
```

### PR Example 2: Bugfix/Issue Tracking

**Title:** Fix issue tracking status update bug  
**Base:** develop  
**Compare:** bugfix/issue-tracking  
**Description:**
```
## Description
Resolves issue where issue status updates were not being tracked properly.

## Root Cause
Status validation was failing silently instead of raising errors.

## Solution
- Added proper error handling
- Fixed status validation logic
- Added issue history tracking

## Testing
- [x] Status updates now tracked
- [x] Invalid statuses rejected
- [x] History retrieval works
```

## 🔄 Git Workflow Commands

### Common Operations

```bash
# Clone repository
git clone https://github.com/NaglaaRedaAA/IntegrationWithJira.git
cd IntegrationWithJira

# Update branches
git fetch origin
git pull origin develop

# Create feature branch
git checkout -b feature/my-new-feature

# Make changes and commit
git add .
git commit -m "feat: Describe your feature"

# Push to remote
git push -u origin feature/my-new-feature

# Merge feature back to develop
git checkout develop
git merge --no-ff feature/my-new-feature
git push origin develop

# Delete branch
git branch -d feature/my-new-feature
git push origin --delete feature/my-new-feature
```

## 📚 Documentation Files

### GIT_WORKFLOW.md
Complete guide on the Git Flow workflow used in this project, including:
- Branch strategy and naming conventions
- Step-by-step workflow instructions
- Commit message conventions
- Best practices
- Troubleshooting guide

### .github/pull_request_template.md
Standard PR template with:
- Description section
- Type of change checklist
- Related issues
- Testing checklist
- Code review checklist
- Screenshots section

## 🎯 Next Steps

1. **Read GIT_WORKFLOW.md** for detailed workflow documentation
2. **Review the PR template** at `.github/pull_request_template.md`
3. **Explore branches** using git commands
4. **Create feature branches** following the naming conventions
5. **Push branches** and create pull requests
6. **Request reviews** from team members

## 💡 Key Takeaways

✅ **Multiple branches** - Feature isolation with organized workflow  
✅ **Clean history** - Meaningful commits with conventional commit messages  
✅ **Documentation** - Comprehensive guides for team members  
✅ **PR template** - Standardized pull request format  
✅ **Git Flow** - Professional branch strategy  
✅ **Scalable** - Ready for team collaboration  

## 📞 Support

For questions about the Git workflow, see **GIT_WORKFLOW.md**  
For PR guidelines, see **.github/pull_request_template.md**  
For project details, see **README.md**

---

**Created:** January 2026  
**Last Updated:** January 2026
