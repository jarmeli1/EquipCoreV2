# GitHub Integration Setup Guide

This guide walks you through setting up the Shopify GitHub integration for automatic theme deployment.

## Prerequisites

- Shopify store (development or production)
- GitHub account
- Admin access to both Shopify and GitHub
- This theme repository pushed to GitHub

## Step 1: Install Shopify GitHub App

1. Go to the [Shopify GitHub App](https://github.com/apps/shopify) page
2. Click **Install** or **Configure**
3. Select the GitHub account/organization where your theme repository is located
4. Choose which repositories Shopify can access:
   - **Recommended**: Select only your theme repository
   - Grant read and write permissions when prompted

## Step 2: Create Development Store (if needed)

If you don't have a store yet:

1. Log in to [Shopify Partners](https://partners.shopify.com)
2. Click **Stores** > **Add store** > **Create development store**
3. Select "Create a store to test and build"
4. Name your store (e.g., "EquipCore Dev")
5. Select your region
6. Click **Create development store**

## Step 3: Connect GitHub to Your Store

1. In your Shopify admin, go to **Online Store** > **Themes**
2. Click **Add theme** > **Connect from GitHub**
3. If prompted, authenticate with GitHub
4. Select your GitHub account/organization
5. Choose your repository (`equipcore-theme`)
6. Select the branch to connect:
   - `main` for production
   - `develop` for testing
7. Click **Connect**

## Step 4: Understanding the Workflow

### Automatic Deployments

Once connected, the workflow is:

```
GitHub Push → Shopify Detects Change → Automatic Theme Update
```

- **Production**: Connect `main` branch to your live theme
- **Development**: Connect feature branches to preview themes
- **Testing**: Use `develop` branch for integration testing

### Branch Protection (Recommended)

Protect your `main` branch on GitHub:

1. Go to Settings > Branches in your GitHub repo
2. Add branch protection rule for `main`
3. Enable:
   - Require pull request reviews
   - Dismiss stale reviews
   - Require status checks

## Step 5: Working with Multiple Themes

You can connect multiple branches to different themes:

1. **Production Theme**: `main` branch (published)
2. **Staging Theme**: `develop` branch (unpublished)
3. **Feature Themes**: `feature/*` branches (unpublished)

To add another branch:
1. Repeat Step 3 with a different branch
2. Each branch creates a separate theme

## Step 6: Managing Theme Updates

### From GitHub (Recommended)

```bash
# Make changes locally
git add .
git commit -m "Update: Description of changes"
git push origin main
# Theme updates automatically
```

### From Shopify Admin

When changes are made in the Theme Editor:
1. Shopify commits changes to GitHub automatically
2. Commit message: "Update from Shopify"
3. Pull these changes before working locally:
   ```bash
   git pull origin main
   ```

## Step 7: Deployment Workflow

### Feature Development

```bash
# Create feature branch
git checkout -b feature/new-section

# Make changes
git add .
git commit -m "Add: New product showcase section"
git push origin feature/new-section

# Create PR on GitHub
# Review and test
# Merge to develop, then main
```

### Hotfix Process

```bash
# Create hotfix from main
git checkout main
git checkout -b hotfix/urgent-fix

# Make fix
git add .
git commit -m "Fix: Urgent issue description"
git push origin hotfix/urgent-fix

# Create PR directly to main
# Deploy immediately after merge
```

## Step 8: Monitoring Deployments

### In Shopify Admin

1. Go to **Online Store** > **Themes**
2. Your connected theme shows:
   - GitHub icon
   - Branch name
   - Last commit info
   - "Updating..." status during deployment

### Deployment Logs

To view deployment history:
1. Click theme actions menu (...)
2. Select **View deployment logs**
3. See status, errors, and commit info

## Troubleshooting

### Theme Not Updating

1. Check GitHub webhook delivery:
   - GitHub repo > Settings > Webhooks
   - Look for Shopify webhook
   - Check recent deliveries

2. Verify branch connection:
   - Theme should show correct branch name
   - Try disconnecting and reconnecting

### Sync Issues

If theme is out of sync:
1. In theme actions, click **Sync from GitHub**
2. Or disconnect and reconnect the branch

### Permission Errors

Ensure:
- GitHub app has write access to repo
- You have admin access to both platforms
- Repository isn't archived or private (if using free plan)

## Best Practices

1. **Never commit `config/settings_data.json` from local**
   - This file contains merchant customizations
   - Let Shopify manage it

2. **Use meaningful commit messages**
   - Good: "Add: Product comparison table section"
   - Bad: "Update theme"

3. **Test on development theme first**
   - Connect `develop` branch to preview theme
   - Test thoroughly before merging to `main`

4. **Regular syncing**
   - Pull changes daily if team is editing in Shopify admin
   - Communicate when making Theme Editor changes

5. **Backup before major changes**
   - Download theme backup from Shopify admin
   - Tag releases in GitHub

## GitHub Actions (Optional)

The theme includes a `.github/workflows/theme-check.yml` for automated testing:

```yaml
name: Theme Check
on: [push, pull_request]

jobs:
  theme-check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: shopify/theme-check-action@v1
```

This runs automatically on every push and PR.

## Support

- [Shopify GitHub Integration Docs](https://shopify.dev/themes/tools/github)
- [Shopify CLI Documentation](https://shopify.dev/themes/tools/cli)
- [Theme Development Best Practices](https://shopify.dev/themes/best-practices)

For EquipCore-specific questions, see [CLAUDE.md](../CLAUDE.md) or contact the development team.