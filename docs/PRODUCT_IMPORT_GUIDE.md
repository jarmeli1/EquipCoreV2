# Product Import Guide for EquipCore

This guide explains how to add products to your Shopify store using the EquipCore product template.

## Overview

The product template (`Public/shopify_product_template.md`) provides a structured format for organizing product information before importing to Shopify. This ensures consistency and completeness across all products.

## Product Categories

EquipCore products fall into these main categories:

1. **Knee Rehabilitation** - Slide boards, ROM devices
2. **Resistance Equipment** - Bands, tubes, loops
3. **Core & Balance** - Pilates balls, stability tools
4. **Flexibility Tools** - Yoga straps, stretching aids
5. **Accessories** - Door anchors, handles, storage

## Using the Product Template

### Step 1: Copy the Template

For each new product, copy the template structure from `Public/shopify_product_template.md`:

```yaml
product:
  name: "<Product Display Name>"
  short_handle: "<product-url-handle>"
  sku: "<SKU123>"
  type: "simple"
  # ... rest of template
```

### Step 2: Fill Required Fields

#### Basic Information
- **name**: Full product name as it appears to customers
- **short_handle**: URL-friendly version (lowercase, hyphens)
- **sku**: Your internal SKU/product code
- **type**: Usually "simple" unless part of a bundle

#### Pricing
```yaml
price:
  retail: 39.99        # Customer price
  compare_at: 49.99    # Original/MSRP (optional)
  cost: 12.50         # Your cost (for margin tracking)
```

#### Variants
For products with options (size, color, resistance):
```yaml
variants:
  - option_name: "Resistance"
    values: ["Light (4-6 lb)", "Medium (8-10 lb)", "Heavy (12-15 lb)"]
  - option_name: "Color"
    values: ["Blue", "Green", "Red"]
```

## Key Fields for PT Equipment

### Specifications (Critical for Professional Equipment)

```yaml
specs:
  dimensions_in:
    length: 30
    width: 12
    height: 0.5
  weight_lb: 1.8
  materials: "TPE, Latex-free"  # Always note if latex-free
  warranty_months: 12
```

### Compliance Information

```yaml
compliance:
  regulated: false  # true if FDA-registered
  hazard_classification: ""  # e.g., shipping restrictions
  disclaimers_md: "Consult healthcare professional before use"
```

### SEO Optimization

```yaml
seo:
  title: "Product Name | Key Benefit - EquipCore"  # ~60 chars
  meta_description: "Professional-grade [product] for [use case]. [Key features]. Latex-free options available."  # ~155 chars
  keywords: ["physical therapy", "rehabilitation", "product type"]
```

## Import Methods

### Method 1: Manual Entry (Recommended for <50 products)

1. Log in to Shopify Admin
2. Go to **Products** > **Add product**
3. Copy information from your YAML template:
   - Title → Product title
   - Description → Product description (use rich text editor)
   - Images → Upload from `assets/` or URL
   - Pricing → Enter prices
   - Inventory → Add SKU and tracking
   - SEO → Edit search engine listing

### Method 2: CSV Import (For bulk import)

1. Convert YAML to CSV format:
```csv
Handle,Title,Body (HTML),Vendor,Type,Tags,Published,Option1 Name,Option1 Value,Variant SKU,Variant Price
knee-rehab-slide-board,"Knee Rehab Slide Board","<p>Professional slide board...</p>",EquipCore,Rehabilitation Equipment,"Knee Rehab,Slide Board",TRUE,,,KR-SB-001,39.99
```

2. Go to **Products** > **Import**
3. Download sample CSV for reference
4. Map your fields correctly
5. Import and review

### Method 3: Shopify API (For developers)

Use the Admin API to create products programmatically:

```javascript
const product = {
  title: "Knee Rehab Slide Board",
  body_html: "<p>Professional slide board...</p>",
  vendor: "EquipCore",
  product_type: "Rehabilitation Equipment",
  tags: ["Knee Rehab", "Slide Board"],
  variants: [{
    price: "39.99",
    sku: "KR-SB-001",
    inventory_quantity: 100
  }]
};
```

## Product Information Best Practices

### 1. Descriptions

**Do:**
- Lead with primary use case
- List key benefits (3-5 bullet points)
- Include dimensions and weight capacity
- Mention latex-free if applicable
- Add care instructions

**Don't:**
- Make medical claims
- Use excessive technical jargon
- Copy manufacturer descriptions verbatim

### 2. Images

**Required:**
- Main product image (white background)
- In-use image showing proper form
- Detail shots of key features
- Size reference (with common object)

**Specifications:**
- 2048x2048px minimum
- Square aspect ratio
- JPG or PNG format
- Under 20MB per image

### 3. Variants & Options

Common variant types for PT equipment:
- **Resistance Levels**: Light, Medium, Heavy, X-Heavy
- **Sizes**: Standard measurements or S/M/L
- **Colors**: Especially for bands/straps
- **Material**: Latex vs Latex-free options

### 4. Collections

Organize products into collections:
- By therapy type (Knee, Shoulder, Back)
- By equipment type (Bands, Balls, Boards)
- By use case (Home vs Clinical)
- By price range
- "New Arrivals" and "Best Sellers"

## Metafields for Advanced Features

Consider adding metafields for:
- Video URLs (exercise demonstrations)
- PDF downloads (exercise guides)
- Certifications (FDA, CE mark)
- Clinical studies or endorsements
- Compatibility (works with X equipment)

## Quality Checklist

Before publishing each product:

- [ ] All images uploaded and optimized
- [ ] Description includes benefits and specs
- [ ] Correct categorization and tags
- [ ] SEO fields completed
- [ ] Pricing includes compare-at if applicable
- [ ] Inventory tracking enabled
- [ ] Shipping weight accurate
- [ ] Materials clearly stated (latex-free noted)
- [ ] Compliance information added if regulated

## Bulk Operations Tips

1. **Standardize SKU format**: 
   - Category-Type-Number (e.g., RB-TPE-001)
   
2. **Use consistent naming**:
   - "[Product Type] - [Key Feature] - [Variant]"
   
3. **Template descriptions**:
   - Create templates for each category
   - Customize key details per product

4. **Batch image processing**:
   - Standardize dimensions
   - Use consistent backgrounds
   - Compress for web

## Post-Import Tasks

1. **Review in theme**:
   - Check product page appearance
   - Verify variant picker works
   - Test on mobile devices

2. **Set up cross-sells**:
   - Add complementary products
   - Create product bundles
   - Set up "Frequently bought together"

3. **Monitor and optimize**:
   - Track view-to-purchase rates
   - A/B test descriptions
   - Update based on customer questions

## Support Resources

- [Shopify Product CSV Template](https://help.shopify.com/en/manual/products/import-export/using-csv#product-csv-file-format)
- [Shopify Admin API Reference](https://shopify.dev/api/admin-rest/2023-10/resources/product)
- [EquipCore Product Template](../Public/shopify_product_template.md)
- [CLAUDE.md](../CLAUDE.md) for AI assistance

For questions about specific products or medical claims, contact: compliance@equipcore.com