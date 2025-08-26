# Hero Section Guide

## Overview

The hero section has been modularized to be fully editable from the Shopify theme editor. You can now add multiple slides with customizable content, images, and positioning.

## Features

### 🎯 **Multiple Slides Support**

- Add unlimited hero slides
- Each slide can have different content and images
- Automatic navigation controls when multiple slides are present

### 🎨 **Fully Customizable Content**

- **Images**: Use Shopify's image picker or external URLs
- **Title**: Customizable heading text
- **Description**: Multi-line description text
- **Button**: Customizable button text and link
- **Button Styles**: Choose from different button appearance options

### 📱 **Responsive Design**

- Mobile-optimized layouts
- Responsive text sizing
- Touch-friendly navigation

### ⚙️ **Advanced Settings**

- **Minimum Height**: Control section height (50vh - 100vh)
- **Autoplay Duration**: Set slide transition timing (1-8 seconds)
- **Animation Duration**: Control transition speed (200ms - 2s)
- **Pause on Hover**: Enable/disable autoplay pause on hover
- **Navigation Arrows**: Show/hide arrow navigation
- **Bullet Navigation**: Show/hide dot navigation

### 🎯 **Content Positioning**

Content is always positioned at the bottom left of each slide for consistency and clean design.

## How to Use

### 1. Adding the Hero Section

1. Go to your theme editor
2. Add a new section
3. Select "Hero Section" from the available sections

### 2. Configuring Global Settings

1. Set the minimum height for the section
2. Configure autoplay and animation settings
3. Choose navigation options

### 3. Adding Slides

1. Click "Add block" → "Hero Slide"
2. Upload or select an image
3. Add title, description, and button content
4. Set button link and style

### 4. Reordering Slides

- Use the drag handles in the theme editor to reorder slides
- The order determines the slide sequence

## File Structure

```
sections/
├── hero.liquid          # Main hero section with inline styles
snippets/
├── hero-slide.liquid    # Individual slide template
```

## Customization

### Button Styles

- **Default**: White border, transparent background
- **Filled**: White background, black text
- **Transparent**: Transparent background

### Image Options

- **Shopify Image Picker**: Recommended for better performance
- **External URL**: Alternative for external images

## Best Practices

1. **Image Optimization**: Use high-quality images (1920x1080 recommended)
2. **Content Length**: Keep titles under 50 characters for mobile
3. **Button Text**: Use action-oriented text (e.g., "Shop Now", "Learn More")
4. **Accessibility**: Ensure sufficient contrast between text and background
5. **Performance**: Limit to 3-5 slides for optimal performance

## Troubleshooting

### Slides Not Showing

- Ensure at least one slide block is added
- Check that images are properly uploaded
- Verify section is added to the correct template

### Navigation Not Working

- Ensure Glide.js library is loaded in theme.liquid
- Check browser console for JavaScript errors
- Verify multiple slides are present for navigation

### Mobile Issues

- Test on actual mobile devices
- Check responsive breakpoints in CSS
- Ensure touch targets are large enough

## Code Examples

### Adding Custom Button Styles

Add to your theme's CSS:

```css
.hero-slide-content .custom-button {
  background: linear-gradient(45deg, #ff6b6b, #ee5a24);
  border: none;
  color: white;
}
```

### Content Positioning

Content is fixed at bottom left position for consistent design across all slides.

### Styling Approach

All styling is kept minimal and inline within the section files, following the original approach for simplicity and maintainability.

## Support

For issues or questions, refer to the Shopify theme documentation or contact your theme developer.
