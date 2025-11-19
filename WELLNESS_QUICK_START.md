# Wellness Theme - Quick Start Guide

## 🎨 Header Layout Options

Change your header layout in **Theme Editor > Header**:

| Layout | Description |
|--------|-------------|
| Top Left | Logo top left corner |
| Top Center | Centered logo at top |
| Top Right | Logo top right corner |
| Middle Left | Logo left, menu right (default) |
| Middle Center | Centered logo, split menu |
| Middle Right | Logo right, menu left |

## 🎯 Quick Wellness Classes

### Buttons
```liquid
btn-wellness-primary      <!-- Green button -->
btn-wellness-secondary    <!-- Cream button -->
btn-wellness-outline      <!-- Outline button -->
```

### Cards & Containers
```liquid
card-wellness            <!-- Product/content card -->
container-wellness       <!-- Page container -->
section-wellness         <!-- Section padding -->
```

### Typography
```liquid
heading-wellness         <!-- Wellness-styled heading -->
link-wellness           <!-- Wellness-styled link -->
```

### Backgrounds
```liquid
bg-wellness-gradient    <!-- Sage to cream gradient -->
twcss-bg-wellness-sage-100   <!-- Light sage background -->
twcss-bg-wellness-cream-50   <!-- Light cream background -->
```

### Styling
```liquid
shadow-wellness         <!-- Wellness shadow -->
input-wellness         <!-- Form input -->
badge-wellness         <!-- Product badge -->
divider-wellness       <!-- Section divider -->
```

## 🎨 Color Reference

### Main Colors
- **Primary Green**: `twcss-bg-primary` / `twcss-text-primary`
- **Secondary Cream**: `twcss-bg-secondary` / `twcss-text-secondary`
- **Accent Lavender**: `twcss-bg-accent` / `twcss-text-accent`

### Wellness Palette
- `wellness-sage-{50-900}` - Natural greens
- `wellness-cream-{50-900}` - Warm neutrals
- `wellness-lavender-{50-900}` - Calming purples
- `wellness-eucalyptus-{50-900}` - Fresh greens
- `wellness-sand-{50-900}` - Earthy tones
- `wellness-terracotta-{50-900}` - Warm reds

## 📱 Responsive Breakpoints

```liquid
sm:   <!-- 320px - Mobile -->
md:   <!-- 750px - Tablet -->
lg:   <!-- 990px - Desktop -->
xlg:  <!-- 1440px - Large Desktop -->
```

Example:
```liquid
<div class="twcss-text-sm md:twcss-text-lg lg:twcss-text-xl">
  Responsive Text
</div>
```

## ⚡ Common Tasks

### 1. Change Primary Color
Edit `tailwind.config.js`:
```javascript
primary: {
  DEFAULT: '#your-color',
}
```

### 2. Add Wellness Button
```liquid
<a href="/collections/all" class="btn-wellness-primary">
  Shop Now
</a>
```

### 3. Create Wellness Card
```liquid
<div class="card-wellness">
  <img src="image.jpg" alt="Product">
  <h3 class="heading-wellness">Product Name</h3>
  <p>Description</p>
</div>
```

### 4. Responsive Section
```liquid
<section class="section-wellness bg-wellness-gradient">
  <div class="container-wellness">
    <!-- Your content -->
  </div>
</section>
```

### 5. Compile Tailwind (After Changes)
```bash
npx tailwindcss -i ./assets/app-tailwind.css -o ./assets/app.css
```

## ✨ Design Tips

1. **Use gradient backgrounds** for hero sections
2. **Add hover effects** with `hover:twcss-transform hover:twcss-scale-105`
3. **Round corners** with `twcss-rounded-2xl` or `twcss-rounded-full`
4. **Add shadows** with `shadow-wellness` or `shadow-soft`
5. **Smooth transitions** with `twcss-transition-all twcss-duration-300`

## 🎯 Example: Complete Wellness Section

```liquid
<section class="section-wellness bg-wellness-gradient">
  <div class="container-wellness">
    <h2 class="heading-wellness twcss-text-4xl twcss-text-center twcss-mb-12">
      Our Products
    </h2>

    <div class="twcss-grid twcss-grid-cols-1 md:twcss-grid-cols-3 twcss-gap-8">
      {% for product in collection.products %}
        <div class="card-wellness twcss-p-6">
          <img src="{{ product.featured_image | img_url: 'large' }}"
               alt="{{ product.title }}"
               class="twcss-w-full twcss-rounded-xl twcss-mb-4">

          <h3 class="heading-wellness twcss-text-xl twcss-mb-2">
            {{ product.title }}
          </h3>

          <p class="twcss-text-neutral-600 twcss-mb-4">
            {{ product.description | truncate: 100 }}
          </p>

          <a href="{{ product.url }}" class="btn-wellness-primary">
            View Product
          </a>
        </div>
      {% endfor %}
    </div>
  </div>
</section>
```

## 🚀 Launch Checklist

- [ ] Test all pages (home, product, collection, cart)
- [ ] Check mobile responsiveness
- [ ] Verify all links work
- [ ] Test checkout process
- [ ] Review on different browsers
- [ ] Optimize images
- [ ] Set up navigation menus
- [ ] Configure header layout
- [ ] Add social media links
- [ ] Enable customer accounts (if needed)

---

Need more details? See `WELLNESS_THEME_GUIDE.md` for complete documentation.
