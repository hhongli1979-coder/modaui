# Wellness Shopify Theme - Customization Guide

## Overview

This theme has been completely redesigned with a modern wellness aesthetic, featuring calming colors, smooth animations, and a responsive design optimized for wellness industry brands including:
- Spas & Beauty Salons
- Yoga & Fitness Studios
- Natural & Organic Products
- Health & Nutrition Brands
- Wellness Retreats & Centers
- Holistic Health Practitioners

## 🎨 Wellness Color Palette

The theme includes a comprehensive wellness-focused color system:

### Primary Colors

#### Sage Green (Primary)
- Perfect for natural, calming wellness brands
- Shades: `wellness-sage-50` through `wellness-sage-900`
- Primary: `#6b8a6b`
- Usage: Buttons, links, accents

#### Cream (Secondary)
- Warm, inviting tones
- Shades: `wellness-cream-50` through `wellness-cream-900`
- Secondary: `#ddb77d`
- Usage: Backgrounds, highlights

### Accent Colors

#### Lavender
- Calming purple tones
- Shades: `wellness-lavender-50` through `wellness-lavender-900`
- Accent: `#9a8cc1`

#### Eucalyptus
- Fresh, spa-like greens
- Shades: `wellness-eucalyptus-50` through `wellness-eucalyptus-900`

#### Sand
- Earthy, natural tones
- Shades: `wellness-sand-50` through `wellness-sand-900`

#### Terracotta
- Warm, grounding colors
- Shades: `wellness-terracotta-50` through `wellness-terracotta-900`

### Using Colors

All colors use the `twcss-` prefix. Examples:
```liquid
<div class="twcss-bg-wellness-sage-100 twcss-text-wellness-sage-900">
  Wellness content
</div>
```

## 🎯 Header Customization

### Logo Position Options

The theme now supports 6 different header layouts:

1. **Top Left** - Logo aligned to top left
2. **Top Center** - Logo centered at top
3. **Top Right** - Logo aligned to top right
4. **Middle Left** - Logo on left with menu on right (default)
5. **Middle Center** - Logo centered with menu split
6. **Middle Right** - Logo on right with menu on left

To change the header layout:
1. Go to Theme Editor
2. Click on Header section
3. Select "Logo position" dropdown
4. Choose your preferred layout
5. Save changes

### Header Features
- Sticky header with smooth scroll behavior
- Backdrop blur effect on scroll
- Smooth transitions on all interactive elements
- Hover effects on menu items with underline animation
- Cart icon with wellness-themed count bubble

## 🎨 Pre-built Wellness Components

### Buttons

#### Primary Button
```liquid
<a href="#" class="btn-wellness-primary">Shop Now</a>
```
- Rounded full corners
- Wellness green background
- Hover: Darker green with shadow and scale effect

#### Secondary Button
```liquid
<a href="#" class="btn-wellness-secondary">Learn More</a>
```
- Cream background
- Smooth hover transitions

#### Outline Button
```liquid
<a href="#" class="btn-wellness-outline">Discover</a>
```
- Border with wellness green
- Fills on hover

### Cards

#### Wellness Card
```liquid
<div class="card-wellness">
  <!-- Your content -->
</div>
```
Features:
- Rounded corners (2xl)
- Soft shadow
- Hover: Lifts up with wellness shadow
- White background
- Smooth transitions

### Form Inputs

```liquid
<input type="email" class="input-wellness" placeholder="Your email">
```
Features:
- Rounded corners
- Border transitions on focus
- Wellness-colored focus ring
- Full width responsive

### Badges

```liquid
<span class="badge-wellness">New</span>
```
- Pill-shaped
- Sage green background
- Perfect for product tags

### Text Links

```liquid
<a href="#" class="link-wellness">Read more</a>
```
- Wellness green color
- Smooth underline on hover
- Medium font weight

## 📐 Layout Utilities

### Sections

```liquid
<section class="section-wellness">
  <!-- Responsive padding: 16/24/30 -->
</section>
```

### Containers

```liquid
<div class="container-wellness">
  <!-- Max-width container with responsive padding -->
</div>
```

### Gradient Background

```liquid
<div class="bg-wellness-gradient">
  <!-- Wellness gradient: sage to cream -->
</div>
```

### Headings

```liquid
<h2 class="heading-wellness">Your Heading</h2>
```
- Uses heading font family
- Wellness dark green color
- Tight line-height and letter-spacing

### Dividers

```liquid
<div class="divider-wellness"></div>
```
- Gradient line from transparent to sage green

## 🏗️ Updated Sections

### Homepage Sections

All homepage sections have been updated with wellness styling:

#### Image Banner
- Smooth fade-in animations
- Responsive overlay
- Wellness-themed content boxes

#### Multicolumn
- Wellness gradient background
- Card-style columns with hover effects
- Centered headings with large wellness typography

#### Featured Collection
- Updated product cards with wellness shadows
- Smooth hover animations
- Rounded corners throughout

### Product Pages

Product pages feature:
- Wellness-styled add to cart buttons
- Enhanced product images with smooth transitions
- Wellness-themed product badges
- Clean, spacious layout

### Cart & Checkout

- Modernized cart drawer with backdrop blur
- Wellness-themed buttons
- Smooth animations
- Clear typography

### Footer

- Wellness gradient background (sage tones)
- Improved link hover effects with dot indicators
- Social icons with lift-on-hover animation
- Newsletter signup with wellness-styled button
- Clean, organized layout

## 📱 Responsive Design

All components are fully responsive with breakpoints:

- `sm`: 320px (Mobile)
- `md`: 750px (Tablet)
- `lg`: 990px (Desktop)
- `xlg`: 1440px (Large desktop)
- `x2lg`: 1920px (Extra large)

Use responsive classes:
```liquid
<div class="twcss-text-sm md:twcss-text-base lg:twcss-text-lg">
  Responsive text
</div>
```

## ⚡ Animations

The theme includes custom animations:

- `animate-fade-in` - Smooth fade in
- `animate-slide-up` - Slide up with fade
- `animate-slide-down` - Slide down with fade
- `animate-scale-in` - Scale in effect

Usage:
```liquid
<div class="twcss-animate-fade-in">Content</div>
```

## 🎭 Shadows

Custom shadow utilities:

- `shadow-soft` - Subtle shadow
- `shadow-soft-lg` - Larger soft shadow
- `shadow-wellness` - Wellness-themed shadow (sage tint)

## 🛠️ Development

### Compiling Tailwind CSS

After making changes to Tailwind classes, compile:

```bash
npx tailwindcss -i ./assets/app-tailwind.css -o ./assets/app.css --watch
```

For production build:

```bash
npx tailwindcss -i ./assets/app-tailwind.css -o ./assets/app.css --minify
```

### Adding Custom Colors

Edit `tailwind.config.js` to add more wellness colors:

```javascript
extend: {
  colors: {
    wellness: {
      // Add your custom wellness colors
      'custom': {
        500: '#yourcolor',
      }
    }
  }
}
```

## ✅ Shopify Theme Compliance

This theme follows all Shopify theme development best practices:

- ✅ Proper use of Liquid syntax
- ✅ Accessibility standards (ARIA labels, semantic HTML)
- ✅ Performance optimized (lazy loading, proper image sizing)
- ✅ Section-based architecture
- ✅ Customizable through Theme Editor
- ✅ Mobile-first responsive design
- ✅ Compatible with Shopify's required features
- ✅ Proper schema structure for all sections

## 📦 What's Included

### Updated Files:
- ✅ Tailwind configuration with wellness palette
- ✅ Header section with 6 layout options
- ✅ Footer with wellness branding
- ✅ Product cards with hover effects
- ✅ Custom wellness CSS utilities
- ✅ Cart drawer with modern design
- ✅ Homepage sections (banner, multicolumn, etc.)
- ✅ Compiled Tailwind CSS

### Design Features:
- ✅ Cohesive wellness color scheme
- ✅ Smooth animations throughout
- ✅ Hover effects on all interactive elements
- ✅ Rounded corners for modern feel
- ✅ Soft shadows for depth
- ✅ Backdrop blur effects
- ✅ Responsive typography
- ✅ Mobile-optimized layouts

## 🚀 Getting Started

1. **Upload to Shopify**: Upload this theme to your Shopify store
2. **Customize Header**: Choose your preferred header layout
3. **Set Colors**: The wellness colors are pre-configured, but you can adjust in the Theme Editor
4. **Add Content**: Add your products, collections, and content
5. **Test Responsive**: Check on mobile, tablet, and desktop
6. **Go Live**: Publish your wellness-focused store!

## 💡 Tips for Best Results

1. **Use High-Quality Images**: The theme's design shines with professional wellness photography
2. **Keep Text Minimal**: Clean, concise copy works best with this aesthetic
3. **Leverage Whitespace**: Don't overcrowd sections - let the design breathe
4. **Consistent Imagery**: Use images with natural, calming tones to match the color palette
5. **Test Everything**: Check all pages on different devices before launching

## 🎯 Ideal Products for This Theme

- Organic skincare & beauty products
- Essential oils & aromatherapy
- Yoga mats & fitness equipment
- Herbal supplements & vitamins
- Natural home goods
- Meditation & mindfulness products
- Healthy food & beverages
- Sustainable wellness products

## 📞 Support

For questions about customization or technical support, refer to:
- Shopify Theme Documentation: https://shopify.dev/docs/themes
- Tailwind CSS Documentation: https://tailwindcss.com/docs

---

**Version**: 1.0.0
**Last Updated**: November 2025
**Theme Base**: Dawn v15.2.0 + Tailwind CSS
**License**: MIT
