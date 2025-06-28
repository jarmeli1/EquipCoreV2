# EquipCore Shopify Theme

A professional Shopify theme for EquipCore, specializing in physical therapy and rehabilitation equipment. Built on Shopify's Dawn theme framework for optimal performance and Online Store 2.0 features.

## Overview

This theme is designed specifically for selling professional-grade physical therapy equipment, with features tailored to showcase:
- Product specifications and compliance information
- Professional credibility and medical-grade quality
- Detailed product categorization by therapy type
- Clear resistance levels and material options

## Prerequisites

- [Shopify Partner Account](https://partners.shopify.com/signup) or store owner access
- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli) installed
- [Git](https://git-scm.com/) installed
- [GitHub Account](https://github.com/) for version control
- [Node.js](https://nodejs.org/) (v14 or higher)

## Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/[your-username]/equipcore-theme.git
cd equipcore-theme
```

### 2. Install Shopify CLI (if not already installed)

```bash
npm install -g @shopify/cli @shopify/theme
```

### 3. Connect to Your Store

```bash
shopify theme dev --store your-store.myshopify.com
```

This will:
- Upload the theme as a development theme
- Start a local development server
- Open a preview URL with hot reload enabled

## GitHub Integration Setup

### 1. Create GitHub Repository

1. Go to [GitHub](https://github.com/new)
2. Create a new repository named `equipcore-theme`
3. Keep it private initially
4. Don't initialize with README (we already have one)

### 2. Push to GitHub

```bash
git remote add origin https://github.com/[your-username]/equipcore-theme.git
git branch -M main
git push -u origin main
```

### 3. Connect to Shopify

1. Install the [Shopify GitHub app](https://github.com/apps/shopify)
2. In your Shopify admin, go to **Online Store > Themes**
3. Click **Add theme > Connect from GitHub**
4. Select your repository and branch
5. The theme will auto-deploy when you push to the connected branch

## Development Workflow

### Branch Strategy

- `main` - Production theme (auto-deploys to live store)
- `develop` - Integration branch for testing
- `feature/*` - Individual feature development
- `hotfix/*` - Emergency fixes

### Common Commands

```bash
# Start development server
shopify theme dev

# Push changes to current theme
shopify theme push

# Pull latest changes from store
shopify theme pull

# Create a new theme on the store
shopify theme push --unpublished

# Run theme validation
shopify theme check

# Package theme as .zip
shopify theme package
```

## Theme Structure

```
├── assets/          # CSS, JS, images, and fonts
├── config/          # Theme settings configuration
├── layout/          # Theme layouts (theme.liquid)
├── locales/         # Translation files
├── sections/        # Reusable page sections
├── snippets/        # Reusable code snippets
├── templates/       # Page templates
└── Public/          # Reference files and documentation
```

## Customization Guide

### Adding Your Logo

1. Upload your logo in **Online Store > Themes > Customize**
2. Navigate to **Theme settings > Logo**
3. Upload your logo image
4. Adjust logo width as needed

### Brand Colors

Update colors in **Theme settings > Colors**:
- Primary: Professional medical blue
- Secondary: Clean whites and grays
- Accent: Trust-building green for CTAs

### Product Setup

1. Use the product template in `Public/shopify_product_template.md` as a guide
2. Ensure all products include:
   - Detailed specifications
   - Material information (especially latex-free options)
   - Resistance levels or weight capacities
   - Dimensions and weight
   - Compliance/safety information

## Testing

### Local Testing

1. Use `shopify theme dev` for local development
2. Test on multiple devices and browsers
3. Verify all product information displays correctly

### Theme Check

Run validation before deploying:

```bash
shopify theme check
```

## Deployment

### To Development Store

```bash
shopify theme push --development
```

### To Production

1. Merge feature branch to `develop`
2. Test thoroughly on preview theme
3. Merge `develop` to `main`
4. GitHub integration auto-deploys to live store

## Support

For theme-specific questions:
- Review [CLAUDE.md](./CLAUDE.md) for AI assistance
- Check Shopify's [Dawn documentation](https://github.com/Shopify/dawn)
- Consult [Shopify Theme Documentation](https://shopify.dev/themes)

For EquipCore business questions:
- Contact: support@equipcore.com
- Documentation: [Product Guide](./Public/shopify_product_template.md)

## License

This theme is proprietary to EquipCore. All rights reserved.

Based on Shopify's Dawn theme - see [Dawn License](https://github.com/Shopify/dawn/blob/main/LICENSE.md) for underlying framework license.