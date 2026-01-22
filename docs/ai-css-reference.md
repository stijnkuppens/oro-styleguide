# OroCommerce CSS Class Reference for AI Knowledge Base

This document provides a comprehensive list of all CSS classes available for use in the OroCommerce page builder and landing pages. Use this as a knowledge base to prevent hallucinating non-existent classes.

**Important**: Only use classes listed in this document. Do not invent or guess class names.

---

## Understanding This Reference

### Class Names vs Values

This reference documents the **class names** and their **semantic intent**. The actual values (colors, sizes, spacing) are **client-specific** and will vary per installation.

| What's Stable | What Varies |
|---------------|-------------|
| Class names (`.btn--primary`) | Exact colors (client's brand) |
| Semantic purpose ("destructive action") | Exact shade of red |
| Grid structure (12 columns) | Gap sizes, breakpoint values |

### How to Use This Reference

- ✅ **Use class names exactly as documented**
- ✅ **Trust the semantic intent** (primary = main brand action, destructive = delete/remove)
- ✅ **Combine classes** for desired effects (e.g., `.btn .btn--default .btn--full`)
- ❌ **Don't use inline styles** - the page builder strips them
- ❌ **Don't invent class names** - only use what's documented
- ❌ **Don't promise custom colors** - only colors available through classes can be used

### Example Values Note

Where hex values or pixel sizes appear in this document, they represent the **default OroCommerce theme** for illustration purposes only. Client installations will have different values.

---

## Table of Contents

1. [Button Classes](#button-classes)
2. [Grid System Classes](#grid-system-classes)
3. [Typography Classes](#typography-classes)
4. [Utility Classes](#utility-classes)
5. [Content Template Classes](#content-template-classes)
6. [Image & Media Classes](#image--media-classes)
7. [Spacing & Offset Classes](#spacing--offset-classes)
8. [Table Classes](#table-classes)

---

## Button Classes

### Base Button
| Class | Description |
|-------|-------------|
| `.btn` | Base button class - required for all buttons |

### Style Variants
| Class | Description |
|-------|-------------|
| `.btn--default` | Primary button with main brand color (teal) |
| `.btn--outlined` | Transparent background with colored border |
| `.btn--plain` | Transparent background and border, colored text only |
| `.btn--flat` | Flat button with underline on hover |
| `.btn--neutral` | Neutral grey button |
| `.btn--neutral-dark` | Darker neutral grey button |
| `.btn--inverse` | White button for use on dark backgrounds |
| `.btn--outlined-inverse` | Outlined button for dark backgrounds |
| `.btn--plain-inverse` | Plain text button for dark backgrounds |
| `.btn--flat-inverse` | Flat button for dark backgrounds |
| `.btn--simple` | Simple text button with secondary color |
| `.btn--simple-colored` | Simple button with primary color text |
| `.btn--simple-colored-inverse` | Simple colored button for dark backgrounds |
| `.btn--text` | Text-only button appearance |

### Destructive/Warning Variants
| Class | Description |
|-------|-------------|
| `.btn--destructive` | Red button for destructive actions (delete, remove) |
| `.btn--destructive-outlined` | Outlined red button |
| `.btn--destructive-plain` | Plain text red button |
| `.btn--destructive-flat` | Flat red button with underline |
| `.btn--destructive-light` | Light red background button |
| `.btn--simple-destructive` | Simple text destructive button |

### Size Modifiers
| Class | Description |
|-------|-------------|
| `.btn--size-small` | Small button - compact UI, secondary actions |
| `.btn--size-large` | Large button - prominent CTAs, hero sections |

### Shape & Width Modifiers
| Class | Description |
|-------|-------------|
| `.btn--full` | Full width button (100%) |
| `.btn--block` | Block-level full width button |
| `.btn--rounded` | Rounded corners (10px border-radius) |
| `.btn--circle` | Circular button (50% border-radius) |
| `.btn--no-padding` | Minimal padding button |

### Button Groups
| Class | Description |
|-------|-------------|
| `.btn-group` | Horizontal button group container |
| `.btn-group--flex` | Flexible button group |
| `.buttons-row` | Flex container for button rows |
| `.buttons-row--pull-end` | Align buttons to right |
| `.buttons-row--flex-end` | Margin-left auto alignment |

---

## Grid System Classes

### Grid Container
| Class | Description |
|-------|-------------|
| `.grid` | Main grid container (12-column CSS Grid) |

### Column Span Classes (Desktop)
| Class | Description |
|-------|-------------|
| `.grid-col-1` | Span 1 column (8.33% width) |
| `.grid-col-2` | Span 2 columns (16.67% width) |
| `.grid-col-3` | Span 3 columns (25% width) |
| `.grid-col-4` | Span 4 columns (33.33% width) |
| `.grid-col-5` | Span 5 columns (41.67% width) |
| `.grid-col-6` | Span 6 columns (50% width) |
| `.grid-col-7` | Span 7 columns (58.33% width) |
| `.grid-col-8` | Span 8 columns (66.67% width) |
| `.grid-col-9` | Span 9 columns (75% width) |
| `.grid-col-10` | Span 10 columns (83.33% width) |
| `.grid-col-11` | Span 11 columns (91.67% width) |
| `.grid-col-12` | Span 12 columns (100% width) |

### Tablet Responsive Columns
| Class | Description |
|-------|-------------|
| `.grid-col-tablet-1` to `.grid-col-tablet-12` | Column span on tablet (max-width: 1279px) |
| `.grid-col-tablet-small-1` to `.grid-col-tablet-small-12` | Column span on small tablet (max-width: 992px) |
| `.grid-col-tablet-big-1` to `.grid-col-tablet-big-12` | Column span on large tablet |

### Mobile Responsive Columns
| Class | Description |
|-------|-------------|
| `.grid-col-mobile-big-1` to `.grid-col-mobile-big-12` | Column span on large mobile (max-width: 767px) |
| `.grid-col-mobile-landscape-1` to `.grid-col-mobile-landscape-12` | Column span on mobile landscape (max-width: 640px) |
| `.grid-col-mobile-1` to `.grid-col-mobile-12` | Column span on mobile (max-width: 430px) |

### Grid Column Count
| Class | Description |
|-------|-------------|
| `.grid-columns-1` | Define grid as 1-column layout |
| `.grid-columns-2` | Define grid as 2-column layout |
| `.grid-columns-3` | Define grid as 3-column layout |
| `.grid-columns-4` | Define grid as 4-column layout |
| `.grid-columns-6` | Define grid as 6-column layout |
| `.grid-columns-12` | Define grid as 12-column layout (default) |

### Grid Start Position
| Class | Description |
|-------|-------------|
| `.grid-start-1` to `.grid-start-12` | Start item at specific column position |

### Row Gap Classes
| Class | Description |
|-------|-------------|
| `.grid-row-gap-4` | 4px gap between rows |
| `.grid-row-gap-8` | 8px gap between rows |
| `.grid-row-gap-12` | 12px gap between rows |
| `.grid-row-gap-16` | 16px gap between rows |
| `.grid-row-gap-24` | 24px gap between rows |
| `.grid-row-gap-32` | 32px gap between rows |
| `.grid-row-gap-40` | 40px gap between rows |

### Responsive Row Gaps
| Class | Description |
|-------|-------------|
| `.grid-row-gap-mobile-big-16` | 16px gap on large mobile |
| `.grid-row-gap-tablet-16` | 16px gap on tablet |

### Grid Alignment
| Class | Description |
|-------|-------------|
| `.grid-place-items-center` | Center all items |
| `.grid-place-items-start` | Align items to start |
| `.grid-place-items-end` | Align items to end |
| `.grid-place-items-center-start` | Center horizontal, start vertical |
| `.grid-place-content-center` | Center content |
| `.grid-place-content-start` | Content to start |
| `.grid-place-content-end` | Content to end |
| `.grid-place-content-start-center` | Start vertical, center horizontal |
| `.grid-place-self-center` | Center individual item |
| `.grid-place-self-start` | Align individual item to start |
| `.grid-place-self-end` | Align individual item to end |
| `.grid-place-self-center-start` | Center horizontal, start vertical for item |
| `.grid-place-self-end-center` | End vertical, center horizontal for item |

### Special Grid Classes
| Class | Description |
|-------|-------------|
| `.grid-responsive-content` | Responsive content sizing |
| `.grid-max-content` | Columns fit their content |
| `.grid-article` | Article grid styling |
| `.grid-item` | Grid item with styling |
| `.grid-item__text` | Text area in grid item |
| `.grid-item__bottom` | Bottom section of grid item |

---

## Typography Classes

### Heading Classes
| Class | Description |
|-------|-------------|
| `.h1` | Largest heading - page titles, hero sections |
| `.h2` | Second-level heading - section titles |
| `.h2-italic` | Italic variant of h2 - stylized section titles |
| `.h3` | Third-level heading - subsections |
| `.h4` | Fourth-level heading - card titles, smaller sections |
| `.h5` | Fifth-level heading - small headings |
| `.h5-caps` | Uppercase small heading - labels, categories |
| `.h6` | Smallest heading - uppercase, often used for labels |
| `.h-normal` | Modifier to make any heading normal weight |

### Caption Classes
| Class | Description |
|-------|-------------|
| `.caption` | Base caption text - small supporting text |
| `.caption-italic` | Italic caption - quotes, attributions |
| `.caption-1` | Caption variant - light italic style |
| `.caption-2` | Caption variant - normal weight |
| `.caption-3` | Caption variant - semi-bold, smallest |

### Text Alignment
| Class | Description |
|-------|-------------|
| `.text-left` | Left align text |
| `.text-center` | Center align text |
| `.text-right` | Right align text |
| `.text-justify` | Justify text |
| `.text-nowrap` | Prevent text wrapping |

### Text Transform
| Class | Description |
|-------|-------------|
| `.text-uppercase` | Transform text to uppercase |
| `.text-capitalize` | Capitalize first letter |
| `.text-clip` | Truncate text with ellipsis |
| `.bold` | Semi-bold font weight |
| `.normal` | Normal font weight |
| `.line-through` | Strikethrough text |

### Text Color Variants
| Class | Description |
|-------|-------------|
| `.text-success` | Success/green text color |
| `.text-error` | Error/red text color |
| `.extra-text` | Small secondary text (13px, lighter) |
| `.extra-text-dark` | Small text in darker color |

### Special Typography
| Class | Description |
|-------|-------------|
| `.blockquote-base` | Blockquote with left border and icon |
| `.highlight-text` | Highlighted text with background |

---

## Utility Classes

### Display & Visibility
| Class | Description |
|-------|-------------|
| `.hidden` | Hide element (display: none) |
| `.hide` | Hide element (display: none) |
| `.display` | Show element |
| `.invisible` | Make invisible (opacity: 0, keeps space) |
| `.hide-on-mobile-landscape` | Hide on mobile landscape |
| `.hide-on-empty:empty` | Hide when element is empty |

### Flexbox Utilities
| Class | Description |
|-------|-------------|
| `.inline-flex` | Display as inline-flex |
| `.items-center` | Flex with align-items: center |
| `.shrink-zero` | Prevent flex shrink |
| `.stretch` | Width 100% |

### Border & Shape
| Class | Description |
|-------|-------------|
| `.rounded` | Rounded corners (standard radius) |
| `.rounded-circle` | Circular shape (border-radius: 50%) |
| `.bordered` | Add border with standard styling |
| `.bordered-img-on-top` | Border on image with top radius |
| `.border-columns` | Border between columns |
| `.border-row-mobile` | Border for rows on mobile |

### Overflow & Scrolling
| Class | Description |
|-------|-------------|
| `.no-scroll` | Prevent scrolling (overflow: hidden) |
| `.vertical-scrolling` | Enable vertical scroll |
| `.invisible-scrollbar` | Hide scrollbar but allow scroll |

### Spacing
| Class | Description |
|-------|-------------|
| `.no-offset` | Remove all margins |
| `.offset-inner` | Inner padding offset |
| `.offset-bottom` | Bottom margin offset |

### Lists
| Class | Description |
|-------|-------------|
| `.list-unstyled` | Remove list styling |
| `.list-style-position-inside` | List bullets inside |

### Interaction
| Class | Description |
|-------|-------------|
| `.disabled` | Disabled state styling |
| `.none-pointer-events` | Disable pointer events |

### Transition
| Class | Description |
|-------|-------------|
| `.no-transition` | Disable transitions |

---

## Content Template Classes

These are root container classes for pre-built landing page templates:

### Category Templates
| Class | Description |
|-------|-------------|
| `.three-columns-category` | 3-column category layout |
| `.two-columns-text-category` | 2-column text category |
| `.two-columns-text-and-image-category` | 2-column with text and image |
| `.two-columns-image-and-text-category` | 2-column with image and text (reversed) |
| `.two-columns-text-and-images-category` | 2-column with multiple images |
| `.two-columns-text-and-images-flexible-category` | Flexible 2-column with images |
| `.two-columns-image-and-text-flexible-category` | Flexible image + text layout |

### Feature Templates
| Class | Description |
|-------|-------------|
| `.two-columns-text-features` | 2-column feature list |
| `.four-columns-text-features` | 4-column feature list |
| `.four-columns-text-and-images-features` | 4-column features with images |
| `.four-columns-text-bg-features` | 4-column with background |
| `.two-columns-text-and-image-features` | 2-column feature with image |
| `.two-columns-text-and-image-flexible-features` | Flexible 2-column feature |
| `.two-and-one-columns-button-feature` | Mixed columns with button |

### Call to Action Templates
| Class | Description |
|-------|-------------|
| `.one-column-text-and-button-call-to-action` | Single column CTA with text and button |
| `.one-column-title-and-button-call-to-action` | Single column CTA with title and button |
| `.one-column-banner-call-to-action` | Banner-style CTA |
| `.two-columns-text-and-button-call-to-action` | 2-column CTA |
| `.three-columns-call-to-action` | 3-column CTA |

### Team Templates
| Class | Description |
|-------|-------------|
| `.four-columns-team` | 4-column team grid |
| `.four-columns-small-images-team` | 4-column team with small images |
| `.seven-columns-large-images-team` | 7-column team with large images |
| `.two-columns-image-and-text-team` | 2-column team layout |

### Testimonial Templates
| Class | Description |
|-------|-------------|
| `.one-column-testimonials` | Single testimonial |
| `.one-column-text-and-images-testimonials` | Testimonial with images |
| `.three-columns-testimonials` | 3-column testimonials |
| `.three-columns-text-testimonials` | 3-column text testimonials |
| `.four-columns-testimonials` | 4-column testimonials |

### Featured Categories
| Class | Description |
|-------|-------------|
| `.featured-categories-grid` | Featured categories container |
| `.featured-categories-grid__cell` | Individual category cell |
| `.featured-categories-grid__content` | Content area |
| `.featured-categories-grid__content-flex` | Flexible content |
| `.featured-categories-grid__picture` | Picture wrapper |
| `.featured-categories-grid__img` | Image element |
| `.featured-categories-grid__link` | Link element |
| `.featured-categories-grid__2-rows` | Cell spanning 2 rows |

---

## Image & Media Classes

| Class | Description |
|-------|-------------|
| `.picture-wrapper` | Container for picture/image with proper sizing |
| `.stretch` | Stretch to fill container width |
| `.full-cover` | Fill entire container (like background-size: cover) |
| `.cover-img` | Object-fit: cover for images |
| `.img-fluid` | Responsive fluid image |
| `.img-min-h-400` | Minimum height 400px for images |

---

## Spacing & Offset Classes

### Content Block Classes
| Class | Description |
|-------|-------------|
| `.extra-block-bg` | Content block with background color and padding |
| `.offset-inner` | Inner padding for content |

### Grid Column Offsets
| Class | Description |
|-------|-------------|
| `.grid-col-inner-offset-left` | Left padding inside grid column |
| `.grid-col-inner-offset-right` | Right padding inside grid column |
| `.grid-col-inner-offset-top-mobile` | Top padding on mobile |
| `.grid-col-inner-offset-bottom-mobile` | Bottom padding on mobile |

### Featured Categories Offsets
| Class | Description |
|-------|-------------|
| `.featured-categories-offset-start` | Start-side offset |
| `.featured-categories-offset-top-bottom-start` | Top and bottom offset |
| `.featured-categories-offset-top-end-start` | Top and end offset |
| `.featured-categories-offset-top-end-start-mobile` | Mobile variant |

---

## Table Classes

| Class | Description |
|-------|-------------|
| `.table-bordered` | Table with borders |
| `.table-borderless` | Table without borders |
| `.table-hover` | Hoverable table rows |

---

## Usage Examples

### Basic Button
```html
<a href="#" class="btn btn--default">Click Me</a>
<a href="#" class="btn btn--outlined">Outlined</a>
<a href="#" class="btn btn--default btn--full">Full Width Button</a>
```

### Responsive Grid
```html
<div class="grid grid-row-gap-16">
    <div class="grid-col-4 grid-col-tablet-6 grid-col-mobile-big-12">
        Column 1
    </div>
    <div class="grid-col-4 grid-col-tablet-6 grid-col-mobile-big-12">
        Column 2
    </div>
    <div class="grid-col-4 grid-col-tablet-12 grid-col-mobile-big-12">
        Column 3
    </div>
</div>
```

### Image with Wrapper
```html
<div class="picture-wrapper">
    <picture class="stretch">
        <img src="image.jpg" class="full-cover cover-img" alt="Description">
    </picture>
</div>
```

### Content Block with Background
```html
<div class="extra-block-bg">
    <h3 class="h3 no-offset">Title</h3>
    <p class="extra-text-dark">Description text</p>
    <a href="#" class="btn btn--default btn--full">Action</a>
</div>
```

### Three Column Category Template
```html
<div class="three-columns-category">
    <div class="grid grid-row-gap-8">
        <div class="grid-col-4 grid-col-tablet-6 grid-col-mobile-big-12">
            <div class="picture-wrapper">
                <picture class="stretch">
                    <img src="image.jpg" class="full-cover cover-img" alt="">
                </picture>
            </div>
            <div class="grid grid-columns-1 grid-row-gap-8">
                <h3 class="h3 no-offset">Category Title</h3>
                <p class="extra-text-dark">Category description</p>
                <a href="#" class="btn btn--full">Shop Now</a>
            </div>
        </div>
    </div>
</div>
```

---

## Notes for AI Implementation

1. **Always use existing classes** - Never invent class names not in this document
2. **Combine classes appropriately** - Buttons need `.btn` base + modifier (e.g., `.btn .btn--default`)
3. **Use responsive classes** - Add tablet/mobile variants for responsive layouts
4. **Prefer semantic templates** - Use pre-built template classes when appropriate
5. **Grid is 12-column** - All column calculations are based on 12-column grid
6. **Trust intent, not values** - Class names and their semantic purpose are stable; actual colors/sizes vary per client
7. **No inline styles** - The page builder strips them; only classes work
8. **Colors are class-based** - Use `.btn--destructive` for red buttons, `.text-error` for error text, etc.
9. **No custom colors** - Content editors cannot apply arbitrary colors; only predefined class colors are available

---

## What's Stable vs What Varies

| Stable (Trust This) | Varies (Don't Hardcode) |
|---------------------|------------------------|
| Class names | Hex color values |
| CSS variable names | Pixel sizes |
| Semantic purpose | Breakpoint exact values |
| Grid column count (12) | Gap/spacing amounts |
| BEM naming structure | Font families |

---

*Document generated from OroCommerce 6.1 default theme*
*Class names are stable across installations; values are client-specific*
*Last updated: 2026-01-22*
*See ai-css-reference-readme.md for extraction methodology*
