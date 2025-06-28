# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an EquipCore Shopify theme based on Dawn, customized for selling professional physical therapy and rehabilitation equipment. The theme is designed to showcase medical-grade exercise equipment with an emphasis on product specifications, compliance information, and professional credibility.

## Key Development Commands

### Local Development
- `shopify theme dev --store {store-name}` - Start local development server with hot reload
- `shopify theme push` - Push theme changes to the current development theme
- `shopify theme push --unpublished` - Push as a new unpublished theme
- `shopify theme pull` - Pull latest theme changes from store
- `shopify theme publish` - Publish theme to live store

### Testing & Validation
- `shopify theme check` - Run theme validation checks
- `shopify theme package` - Create a .zip file of the theme

## Architecture & Structure

### Theme Directories
- `/assets` - CSS, JS, images, and other static files
- `/config` - Theme settings (settings_schema.json) and data (settings_data.json)
- `/layout` - Base layout files (theme.liquid)
- `/locales` - Translation files for internationalization
- `/sections` - Reusable page sections with settings
- `/snippets` - Reusable code fragments
- `/templates` - Page templates (product.json, collection.json, etc.)

### Key Files to Remember
- `config/settings_schema.json` - Theme-wide settings configuration
- `sections/header.liquid` - Main navigation and branding
- `sections/main-product.liquid` - Product page template
- `templates/product.json` - Product page structure
- `assets/equipcore-logo.png` - Company logo

## Business Context

### Product Categories
1. **Knee Rehabilitation Equipment** - Slide boards, range of motion devices
2. **Resistance Training** - TPE/Latex bands, tubes with handles
3. **Core & Balance** - Pilates balls, balance equipment
4. **Flexibility Tools** - Yoga straps, stretching aids
5. **Accessories** - Door anchors, storage solutions

### Key Product Attributes
- FDA compliance status
- Material specifications (latex-free options important)
- Weight capacity/resistance levels
- Dimensions and portability
- Professional/clinical vs home use designation
- Warranty information

## Customization Guidelines

### Brand Colors
- Primary: Professional medical blue/teal
- Secondary: Clean whites and light grays
- Accent: Trust-building green for CTAs

### Typography
- Headers: Clean, professional sans-serif
- Body: Readable, accessible font sizes
- Product specs: Monospace for measurements

### Key Sections to Customize
1. **Product Pages**
   - Emphasize specifications table
   - Add compliance/safety information
   - Include professional use cases
   - Show dimension diagrams

2. **Homepage**
   - Featured rehabilitation categories
   - Professional credibility indicators
   - Quick product finder by body part/therapy type

3. **Collection Pages**
   - Filter by resistance level, material, therapy type
   - Comparison tools for similar products

## GitHub Workflow

### Branch Strategy
- `main` - Production theme (auto-deploys to live store)
- `develop` - Integration branch for features
- `feature/*` - Individual feature branches
- `hotfix/*` - Emergency fixes

### Deployment Process
1. Feature branches merged to `develop`
2. `develop` tested on preview theme
3. `develop` merged to `main` for production
4. Shopify GitHub integration auto-deploys from `main`

## Common Tasks

### Adding a New Product Section
1. Create new section file in `/sections`
2. Add schema with customizable settings
3. Include section in relevant template JSON files
4. Test in theme editor for merchant customization

### Updating Product Information Display
- Product specs: Modify `sections/main-product.liquid`
- Add metafield displays for compliance info
- Update `snippets/product-variant-picker.liquid` for size/resistance options

### Performance Considerations
- Lazy load product images
- Minimize third-party scripts
- Use responsive images with proper srcset
- Keep CSS/JS bundles optimized

## Important Notes
- Always test theme changes on a development theme first
- The `config/settings_data.json` file contains merchant customizations - handle with care
- Use translation keys for all visible text to support internationalization
- Follow Shopify's theme requirements for app blocks and Online Store 2.0 features