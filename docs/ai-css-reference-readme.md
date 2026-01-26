# AI CSS Reference - How This Document Was Created

This README explains how `ai-css-reference.md` was generated so future AI assistants can update or extend it.

## Purpose

The `ai-css-reference.md` serves as a knowledge base for AI assistants creating landing pages in OroCommerce's page builder. It prevents hallucination of non-existent CSS classes by providing an authoritative list of available classes.

## Important: Values vs Class Names

**The class names are the stable API. The values are client-specific.**

This reference was extracted from the default OroCommerce installation (Refreshing Teal theme). However:

- **Class names stay the same** across all client installations
- **Colors will differ** - each client has their own brand palette
- **Sizes/spacing may differ** - clients customize these via SCSS variables
- **The intent/purpose remains the same** - `.btn--destructive` is always for destructive actions, regardless of the actual color

When using this reference:
- ✅ Trust the class names
- ✅ Trust the semantic purpose (e.g., "primary button", "error state")
- ❌ Do not rely on specific hex values
- ❌ Do not assume exact pixel sizes
- ❌ Do not use inline styles (page builder strips them)
- ❌ Do not promise custom colors beyond what classes provide

## Important: No Color Names in Descriptions

**Never use actual color names (green, red, blue, teal, etc.) in class descriptions** unless the class name itself contains that color word.

### Why?
- Colors vary per client installation
- The AI should not "know" what color something is - only its semantic purpose
- Saying "red button" creates false expectations when the client's destructive color might be orange or purple

### Correct Examples
| Class | ✅ Good Description | ❌ Bad Description |
|-------|---------------------|-------------------|
| `.btn--destructive` | Destructive button for delete/remove actions | Red button for dangerous actions |
| `.status-label--success` | Success/completed status | Green success label |
| `.bg-primary-light` | Light primary tint for sections | Light teal background |
| `.text-error` | Error state text color | Red error text |

### Exception
Only use color names when the class name explicitly contains the color:
- `.red-label` → "Red colored label" ✅
- `.bg-white` → "White background" ✅

## Data Sources

### 1. Button Classes
**Source files:**
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/uikit/buttons.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/uikit/button-base.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/variables/uikit/buttons-config.scss`

**Extraction method:**
- Searched for `.btn` class definitions and BEM modifiers (`--`)
- Extracted from `$btn-palette` SCSS map which defines all button variants
- Size modifiers from `$btn-sizes` map

### 2. Grid System Classes
**Source files:**
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/grid.scss`

**Extraction method:**
- Grid classes are dynamically generated via SCSS loops
- Column classes: `.grid-col-{1-12}` generated from loop
- Responsive variants generated per breakpoint from `$breakpoints` map
- Breakpoints: `desktop`, `tablet-big`, `tablet`, `tablet-small`, `mobile-big`, `mobile-landscape`, `mobile`
- Gap classes use spacing scale: `4`, `8`, `12`, `16`, `24`, `32`, `40`

### 3. Typography Classes
**Source files:**
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/headings.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/uikit/caption.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/uikit/text-variants.scss`
- `vendor/oro/platform/src/Oro/Bundle/UIBundle/Resources/public/default/scss/settings/_typography.scss`

**Extraction method:**
- Heading classes from `%base-h{1-6}` placeholders
- Caption variants from component definitions
- Text utilities from Bootstrap-derived utilities

### 4. Utility Classes
**Source files:**
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/utilities.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/bootstrap/utilities/_text.scss`
- `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/bootstrap/utilities/_position.scss`

**Extraction method:**
- Direct class definitions in utilities.scss
- Bootstrap-derived utility classes

### 5. Content Template Classes
**Source files:**
- `vendor/oro/commerce/src/Oro/Bundle/CMSBundle/Migrations/Data/Demo/ORM/data/content-template/template/*.html`
- `vendor/oro/commerce/src/Oro/Bundle/CMSBundle/Migrations/Data/Demo/ORM/data/content-template/css/*.css`

**Extraction method:**
- Parsed HTML template files for class attributes
- Root container classes identified by template naming convention
- Inner classes extracted from actual usage in templates

### 6. Color System & CSS Custom Properties

**Note:** Inline styles **cannot be used** in the page builder - the WYSIWYG editor strips them. However, `<style>` tags with CSS custom properties DO work.

#### Source Files
| File | Purpose |
|------|---------|
| `vendor/oro/platform/src/Oro/Bundle/UIBundle/Resources/public/default/scss/settings/_colors.scss` | Defines `$color-palette` SCSS map with all color values |
| `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/theme-colors.scss` | Generates CSS variables from `$color-palette` |
| `public/build/default/css/styles.css` | Compiled CSS with all `--{section}-{key}` variables |

#### How CSS Variables Are Generated

The `theme-colors.scss` file uses an SCSS loop to generate all CSS custom properties:

```scss
:root {
    @each $section-name, $section in $color-palette {
        @each $key, $value in $section {
            --#{$section-name}-#{$key}: #{$value};
        }
    }
}
```

This generates variables like `--primary-main`, `--destructive-light`, `--neutral-grey1`, etc.

#### Color Palette Sections

The `$color-palette` map contains these sections (all variables are documented in `ai-css-reference.md`):

| Section | Variables | Intent |
|---------|-----------|--------|
| `primary` | main, hover, active, disabled, light | Brand colors |
| `secondary` | c1-c6, sale | Accent/promotional colors |
| `neutral` | white-100/50/30/15, grey1-3, dark, focus | Structural backgrounds |
| `text` | primary, secondary, disabled, inverse, link variants | Text colors |
| `destructive` | light, base, main, dark, disabled, on-dark variants | Error/delete states |
| `success` | light, dark | Success states |
| `warning` | light, base, dark | Warning states |
| `info` | light, dark | Informational states |

#### Usage in Page Builder

Since `<style>` tags work in the CMS, background colors can be applied by defining classes that map directly to variables:

```html
<style>
.bg-primary-light { background-color: var(--primary-light); }
</style>
<div class="bg-primary-light offset-inner">Content</div>
```

**Rule:** Class names must directly reflect the variable name (`.bg-{variable-name}`).

## How to Update This Document

### Adding New Classes

1. **Identify the source:** Find the SCSS file where the class is defined
2. **Verify it's available:** Check the compiled CSS in `public/build/default/css/styles.css`
3. **Add to appropriate section:** Use the existing table format
4. **Include description:** Explain what the class does, not just its name

### Search Commands for Discovery

```bash
# Find all SCSS files with specific class patterns
grep -r "\.btn--" vendor/oro --include="*.scss" | head -50

# Find grid-related classes
grep -r "\.grid-" vendor/oro --include="*.scss" | head -50

# Find utility classes
grep -r "^\." vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/utilities.scss

# Find content template classes
grep -r "class=" vendor/oro/commerce/src/Oro/Bundle/CMSBundle/Migrations/Data/Demo/ORM/data/content-template/template/
```

### Viewing the StyleBook (Dev Mode Only)

The StyleBook provides a visual reference of all components. It requires debug mode:

1. Set `APP_DEBUG=true` in `.env`
2. Clear cache: `bin/console cache:clear`
3. Visit: `https://your-domain/style-book/`

**Note:** StyleBook access is controlled by `Oro\Bundle\StyleBookBundle\Helper\AccessHelper` which checks `kernel.debug`.

## File Locations Summary

| Category | Primary Location |
|----------|------------------|
| Buttons | `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/uikit/` |
| Grid | `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/grid.scss` |
| Typography | `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/headings.scss` |
| Utilities | `vendor/oro/customer-portal/src/Oro/Bundle/FrontendBundle/Resources/public/default/scss/components/utilities.scss` |
| Templates | `vendor/oro/commerce/src/Oro/Bundle/CMSBundle/Migrations/Data/Demo/ORM/data/content-template/` |
| Colors | `vendor/oro/platform/src/Oro/Bundle/UIBundle/Resources/public/default/scss/settings/_colors.scss` |
| Compiled CSS | `public/build/default/css/styles.css` |
| StyleBook CSS | `public/build/default/css/stylebook.css` |

## Breakpoint Reference

These breakpoints are used for responsive class generation:

| Breakpoint | Media Query | Description |
|------------|-------------|-------------|
| `desktop` | min-width: 1366px | Large desktop |
| `desktop-big` | min-width: 1600px | Extra large desktop |
| `desktop-small` | min-width: 1280px | Small desktop |
| `tablet-big` | max-width: 1366px | Large tablet |
| `tablet` | max-width: 1279px | Standard tablet |
| `tablet-small` | max-width: 992px | Small tablet |
| `mobile-big` | max-width: 767px | Large mobile |
| `mobile-landscape` | max-width: 640px | Mobile landscape |
| `mobile` | max-width: 430px | Mobile portrait |

## Limitations & Caveats

1. **Dynamic classes:** Some classes are generated dynamically via SCSS loops - the full list depends on configuration variables
2. **Theme-specific:** This document covers the `default` theme (Refreshing Teal). Custom themes may have additional or different classes
3. **Version-specific:** Based on OroCommerce 6.1 - classes may change in future versions
4. **Not exhaustive:** Admin-only classes (backend) are not included - this focuses on storefront/page builder classes

## Validation

To verify a class exists in the compiled output:

```bash
# Search compiled CSS for a specific class
grep -o "\.btn--destructive" public/build/default/css/styles.css

# Count occurrences
grep -c "\.grid-col-" public/build/default/css/styles.css
```

---

*Last updated: 2026-01-26*
*OroCommerce version: 6.1*
