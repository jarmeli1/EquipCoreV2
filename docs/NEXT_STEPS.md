# Next Steps to Complete Your EquipCore Theme Setup

Follow these steps in order to get your theme running on Shopify.

## Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the **+** icon in the top right → **New repository**
3. Repository settings:
   - **Repository name**: `equipcore-theme`
   - **Description**: "EquipCore Shopify theme for physical therapy equipment"
   - **Private** or **Public**: Your choice (Private recommended initially)
   - **DO NOT** initialize with README, .gitignore, or license
4. Click **Create repository**
5. Copy the repository URL (looks like: `https://github.com/YOUR-USERNAME/equipcore-theme.git`)

## Step 2: Push Your Code to GitHub

Run these commands in your terminal:

```bash
# Add the remote repository (replace YOUR-USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR-USERNAME/equipcore-theme.git

# Push your code
git push -u origin main
```

If you get an authentication error, you may need to:
- Use a Personal Access Token instead of password
- Or use GitHub CLI: `gh auth login`

## Step 3: Create a Shopify Development Store

1. Go to [Shopify Partners](https://partners.shopify.com)
2. Sign up or log in
3. From the dashboard, click **Stores** → **Add store** → **Create development store**
4. Fill in:
   - **Store purpose**: Create a store to test and build
   - **Store name**: EquipCore Dev (or similar)
   - **Store region**: Your region
   - **Store type**: Keep default settings
5. Click **Create development store**
6. Note your store URL: `your-store-name.myshopify.com`

## Step 4: Install Shopify GitHub App

1. Go to [Shopify GitHub App](https://github.com/apps/shopify)
2. Click **Install** or **Configure**
3. Select your GitHub account
4. Choose repository access:
   - Select **Only select repositories**
   - Choose `equipcore-theme`
5. Click **Install**

## Step 5: Connect GitHub to Your Shopify Store

1. Log in to your Shopify development store admin
2. Go to **Online Store** → **Themes**
3. Click **Add theme** → **Connect from GitHub**
4. If prompted, authenticate with GitHub
5. Select:
   - **Account**: Your GitHub username
   - **Repository**: equipcore-theme
   - **Branch**: main
6. Click **Connect**

The theme will automatically import and appear in your theme library!

## Step 6: Preview and Customize Your Theme

1. In the theme library, find your EquipCore theme
2. Click **Actions** → **Preview** to see it in action
3. Click **Customize** to open the theme editor
4. Initial customizations to make:
   - **Theme settings** → **Logo**: Upload your logo
   - **Theme settings** → **Colors**: Set your brand colors
   - **Header**: Adjust menu and layout
   - **Announcement bar**: Add welcome message

## Step 7: Test Local Development

Once connected, test your local development workflow:

```bash
# Install Shopify CLI if not already installed
npm install -g @shopify/cli @shopify/theme

# Start development server
shopify theme dev --store your-store-name.myshopify.com

# This will:
# - Upload theme as development theme
# - Start local server with hot reload
# - Open preview in browser
```

## Common Issues and Solutions

### Authentication Issues
If you can't push to GitHub:
```bash
# Use GitHub CLI for easier auth
gh auth login
# Or create a Personal Access Token at github.com/settings/tokens
```

### Theme Not Appearing
If theme doesn't show after connecting:
1. Check the connection status in theme library
2. Try disconnecting and reconnecting
3. Verify the repository has code (check GitHub)

### Development Server Issues
If `shopify theme dev` fails:
1. Make sure you're logged in: `shopify auth logout` then `shopify theme dev`
2. Verify store URL is correct
3. Check you have proper permissions on the store

## What's Next?

After setup is complete:

1. **Customize the theme** for EquipCore branding
2. **Add products** using the product import guide
3. **Set up collections** for different equipment types
4. **Configure payment and shipping** settings
5. **Test the checkout process**

## Useful Commands Reference

```bash
# Development
shopify theme dev                    # Start dev server
shopify theme push                   # Push changes to current theme
shopify theme pull                   # Pull latest changes

# Branches and Deployment
git checkout -b feature/new-feature  # Create feature branch
git push origin feature/new-feature  # Push feature branch
git checkout main                    # Switch to main
git merge feature/new-feature        # Merge feature

# Theme Management
shopify theme list                   # List all themes
shopify theme publish                # Publish theme
shopify theme package                # Create theme zip
```

## Support Resources

- [Shopify Partner Dashboard](https://partners.shopify.com)
- [Shopify Dev Documentation](https://shopify.dev/themes)
- [GitHub Documentation](https://docs.github.com)
- Your documentation:
  - [README.md](../README.md) - Project overview
  - [CLAUDE.md](../CLAUDE.md) - AI assistant guide
  - [GitHub Setup Guide](./GITHUB_SETUP.md) - Detailed GitHub integration
  - [Product Import Guide](./PRODUCT_IMPORT_GUIDE.md) - Adding products

---

Need help? The setup guides in the `docs/` folder have detailed instructions for each step.