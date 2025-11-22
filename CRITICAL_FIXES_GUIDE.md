# 🔧 CRITICAL FIXES GUIDE - Step by Step

## Fix #1: Add Lazy Loading to Images ⚡

### Files to Fix:
- `sections/amari-hero-v2.liquid`
- `sections/amari-hero-v3.liquid`
- `sections/amari-hero.liquid`

### What to Change:
Find all `<img` tags and add `loading="lazy"` attribute

**BEFORE:**
```liquid
<img src="{{ section.settings.image | img_url: '1920x' }}"
     alt="{{ section.settings.image.alt }}">
```

**AFTER:**
```liquid
<img src="{{ section.settings.image | img_url: '1920x' }}"
     alt="{{ section.settings.image.alt }}"
     loading="lazy"
     width="{{ section.settings.image.width }}"
     height="{{ section.settings.image.height }}">
```

### Why This Matters:
- ✅ Improves page load speed by 30-50%
- ✅ Required for Shopify Theme Store approval
- ✅ Better Core Web Vitals scores

---

## Fix #2: Replace Google Fonts with Shopify Fonts 🎨

### File to Fix:
- `sections/amari-hero-v3.liquid` (lines 15-17)

### Option A: Use Shopify Font Picker (RECOMMENDED)

**REMOVE these lines (15-17):**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=DM+Sans..." rel="stylesheet">
```

**ADD to section schema:**
```json
{
  "type": "font_picker",
  "id": "heading_font",
  "label": "Heading font",
  "default": "assistant_n4"
},
{
  "type": "font_picker",
  "id": "body_font",
  "label": "Body font",
  "default": "assistant_n4"
}
```

**USE in CSS:**
```liquid
<style>
  .hero-heading {
    font-family: {{ section.settings.heading_font.family }}, {{ section.settings.heading_font.fallback_families }};
    font-weight: {{ section.settings.heading_font.weight }};
  }
</style>
```

### Option B: Async Load Google Fonts (If you must use them)

**REPLACE lines 15-17 with:**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link
  href="https://fonts.googleapis.com/css2?family=DM+Sans:opsz,wght@9..40,400;500;700&family=Playfair+Display:wght@600;700;800&display=swap"
  rel="stylesheet"
  media="print"
  onload="this.media='all'">
```

---

## Fix #3: Replace Hardcoded Routes 🌍

### File to Fix:
- `sections/amari-footer.liquid` (lines 8, 12, 105)

**FIND:**
```liquid
<a href="/">
```

**REPLACE WITH:**
```liquid
<a href="{{ routes.root_url }}">
```

### All Instances:
```liquid
<!-- Line 8 -->
<a href="{{ routes.root_url }}" class="inline-block mb-4">

<!-- Line 12 -->
<a href="{{ routes.root_url }}" class="inline-block text-2xl font-bold mb-4">

<!-- Line 105 -->
<a href="{{ routes.root_url }}" class="hover:text-white transition-colors">{{ shop.name }}</a>
```

---

## Fix #4: Clean Up Unused Variables 🧹

### File: `sections/main-product.liquid`
**Line 717 - Remove:**
```liquid
{% assign seo_media = product.featured_media %}
```

### File: `sections/main-search.liquid`
**Line 274 - Remove:**
```liquid
{%- capture product_settings -%}{%- if section.settings.product_show_vendor -%}vendor,{%- endif -%}title,price{%- endcapture -%}
```

### File: `snippets/product-variant-options.liquid`
**Line 62 - Remove:**
```liquid
{%- capture help_text -%}
...
{%- endcapture -%}
```

---

## Fix #5: Fix Variable Naming Convention 📝

### File: `sections/main-list-collections.liquid`
**Line 20:**

**BEFORE:**
```liquid
{% assign moduloResult = 28 | modulo: section.settings.columns_desktop %}
```

**AFTER:**
```liquid
{% assign modulo_result = 28 | modulo: section.settings.columns_desktop %}
```

**Don't forget to update all references to this variable in the same file!**

---

## 🚀 QUICK FIX SCRIPT

Run these commands to fix most issues automatically:

```bash
# Fix lazy loading on images (hero sections)
find sections/amari-hero*.liquid -type f -exec sed -i 's/<img /<img loading="lazy" /g' {} \;

# Fix hardcoded routes in footer
sed -i 's|href="/"|href="{{ routes.root_url }}"|g' sections/amari-footer.liquid

# Fix variable naming
sed -i 's/moduloResult/modulo_result/g' sections/main-list-collections.liquid
```

---

## ✅ VERIFICATION CHECKLIST

After making fixes, run:

```bash
# 1. Recompile Tailwind if you changed any classes
npx tailwindcss -i ./assets/app-tailwind.css -o ./assets/app.css --minify

# 2. Run theme check again
shopify theme check

# 3. Test locally
shopify theme dev

# 4. Commit changes
git add .
git commit -m "fix: Resolve Shopify compliance issues

- Add lazy loading to all hero images
- Replace Google Fonts with Shopify fonts
- Fix hardcoded routes for i18n support
- Remove unused variables
- Fix variable naming conventions"

git push
```

---

## 📊 EXPECTED RESULTS

After fixes:
- ✅ 0 Errors
- ⚠️ ~5-10 Warnings (optional improvements)
- 🚀 20-30% better page load performance
- ✅ Shopify Theme Store ready

---

## 💡 PRO TIPS

1. **Images**: Always use Shopify's `image_url` filter with proper sizing
2. **Fonts**: Shopify's font picker has 100+ professional fonts
3. **Routes**: Always use `routes` object for all URLs
4. **Variables**: Use snake_case for all Liquid variables
5. **Testing**: Test with Shopify CLI before pushing to production

---

**Last Updated**: November 2025
**Theme Version**: Wellness Theme v1.0
