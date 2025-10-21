# Product Images - Complete Guide

## ✅ ALL PRODUCT IMAGES UPDATED!

All 10 placeholder images have been replaced with real product images from your WordPress backup.

---

## Images Locations

All product images are located in:
```
imbilling-github-pages/images/
```

### Current Product Images (7 total):

1. **billing-tshirt.png** (27KB)
   - Used for: "I'm Billing You For This Conversation® T-Shirt"
   - Pages: index.html, shop.html

2. **bitch-pleas-tshirt.png** (27KB)
   - Used for: "Bitch Pleas, I'm a Lawyer T-Shirt"
   - Pages: index.html, shop.html

3. **bitch-pleas-sweatshirt.png** (21KB)
   - Used for: "Bitch Pleas, I'm a Lawyer Sweatshirt"
   - Pages: shop.html

4. **billable-hours-tshirt.png** (30KB)
   - Used for: "Keep Talking I Need the Billable Hours T-Shirt"
   - Pages: index.html, shop.html

5. **billable-hours-sweatshirt.png** (22KB)
   - Used for: "Keep Talking I Need the Billable Hours Sweatshirt"
   - Pages: shop.html

6. **no-advice-tshirt.png** (24KB)
   - Used for: "No Free Advice T-Shirt"
   - Pages: shop.html

7. **no-advice-sweatshirt.png** (18KB)
   - Used for: "No Free Advice Sweatshirt"
   - Pages: shop.html

---

## Where Images Are Used

### Home Page (index.html)
- Shows 3 featured products with images
- Lines 91, 100, 109

### Shop Page (shop.html)
- Shows all 7 products with images
- Lines 53, 69, 84, 99, 114, 129, 144

---

## How to Replace/Update Product Images

If you want to change any product image:

### Option 1: Replace Existing Image File
1. Get your new image (from Amazon or create your own)
2. Save it with the SAME filename as the current image
3. Copy it to `images/` folder (it will overwrite the old one)
4. Done! The website will automatically use the new image

**Example:**
```bash
# Replace the billing t-shirt image
cp /path/to/your/new-image.png images/billing-tshirt.png
```

### Option 2: Use a Different Image File
1. Save your new image in `images/` folder with any name
2. Edit the HTML file (index.html or shop.html)
3. Find the `<img src="images/old-name.png">` tag
4. Change it to `<img src="images/new-name.png">`
5. Update the `alt` text to describe the image

**Example:**
```html
<!-- Old -->
<img src="images/billing-tshirt.png" alt="Old description">

<!-- New -->
<img src="images/my-new-image.jpg" alt="New description for accessibility">
```

---

## Image Requirements

For best results, product images should:

✅ **Format**: PNG or JPG
✅ **Size**: 300x300px to 600x600px (square)
✅ **File Size**: Keep under 100KB for faster loading
✅ **Background**: Transparent PNG or solid background

### Optimization Tips

To optimize images for web:
1. Use https://tinypng.com/ to compress PNG images
2. Use https://squoosh.app/ for JPG compression
3. Resize to 600x600px maximum
4. Convert to WebP format for even better performance (optional)

---

## Accessibility - Alt Text

Every image MUST have descriptive `alt` text for screen readers (WCAG 2.1 AA requirement).

### Good Alt Text Examples:
```html
✅ GOOD: alt="I'm Billing You For This Conversation T-Shirt - Black shirt with white text"
✅ GOOD: alt="Funny lawyer t-shirt with billable hours joke"
❌ BAD:  alt="product image"
❌ BAD:  alt="shirt"
❌ BAD:  alt="" (empty)
```

### Alt Text Guidelines:
- Describe what the product looks like
- Include the product name
- Mention color, style, or notable features
- Keep it under 125 characters
- Don't say "image of" (screen readers already announce it's an image)

---

## Current Status

✅ All 7 products have real images (no more placeholders!)
✅ All images copied from WordPress backup
✅ All alt text is descriptive and WCAG compliant
✅ Images are optimized and web-ready
✅ CSS styling applied for proper display

---

## Adding New Products

When you add a new product:

1. **Add the product image** to `images/` folder
   - Name it descriptively (e.g., `new-product-name.png`)

2. **Add the product HTML** in `shop.html`:
```html
<article class="product-card">
    <a href="https://www.amazon.com/dp/YOUR-AMAZON-ID" target="_blank" rel="noopener noreferrer" class="product-link">
        <img src="images/new-product-name.png" alt="Descriptive alt text" loading="lazy">
        <h3>Product Name</h3>
        <div class="product-description">
            <ul>
                <li>Product description point 1</li>
                <li>Product description point 2</li>
            </ul>
        </div>
        <span class="btn btn-primary" role="button">View on Amazon</span>
    </a>
</article>
```

3. **Optional**: Add to featured products on home page (index.html)

---

## Troubleshooting

### Image not showing?
1. Check the file path is correct: `images/filename.png`
2. Check the filename matches exactly (case-sensitive!)
3. Make sure image is in the `images/` folder
4. Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)

### Image looks stretched or distorted?
- Make sure the original image is square (1:1 aspect ratio)
- The CSS will automatically maintain aspect ratio

### Image file size too large?
- Compress at https://tinypng.com/
- Resize to 600x600px maximum
- Consider converting to WebP format

---

## Summary

🎉 **All product images are now live and working!**

- ✅ No more placeholders
- ✅ All images extracted from WordPress backup
- ✅ Fully accessible with proper alt text
- ✅ Optimized for web performance
- ✅ Ready for deployment

Your website is now complete and ready to deploy to GitHub Pages!
