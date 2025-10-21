# I'm Billing You For This Conversation® - Static Website

A fully accessible, static website for **I'm Billing You For This Conversation®**, selling funny legal-themed apparel on Amazon.

## Features

- ✅ **WCAG 2.1 Level AA Compliant** - Fully accessible website
- 📱 **Responsive Design** - Works on all devices
- ⚡ **Fast Loading** - No dependencies, pure HTML/CSS/JS
- 🎯 **SEO Optimized** - Semantic HTML5 markup
- ♿ **Keyboard Navigation** - Full keyboard support with skip links
- 🎨 **Modern Design** - Clean, professional appearance

## Site Structure

```
imbilling-github-pages/
├── index.html           # Home page
├── shop.html            # All products
├── about.html           # About page
├── contact.html         # Contact page
├── 404.html             # 404 error page
├── CNAME                # Custom domain configuration
├── css/
│   └── styles.css       # Main stylesheet (WCAG compliant)
├── js/
│   └── main.js          # Mobile menu & interactions
├── images/              # Site images
└── README.md           # This file
```

## Deployment to GitHub Pages

### Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and create a new repository
2. Name it anything you like (e.g., `imbilling-website`)
3. Set it to **Public** (required for free GitHub Pages)
4. **Do not** initialize with README, .gitignore, or license

### Step 2: Initialize and Push Files

Open Terminal and run:

```bash
cd /Users/nathannantais/Coding/imbillingcustomsite/imbilling-github-pages

# Initialize git repository
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit - Static site migration from WordPress"

# Add remote repository (replace USERNAME and REPO with your GitHub details)
git remote add origin https://github.com/USERNAME/REPO.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings**
3. Click **Pages** in the left sidebar
4. Under "Source", select **Deploy from a branch**
5. Choose **main** branch and **/ (root)** folder
6. Click **Save**

GitHub will deploy your site at: `https://USERNAME.github.io/REPO/`

### Step 4: Configure Custom Domain

#### A. Update DNS Settings (at your domain registrar):

1. Log into your domain registrar where you bought `imbillingyouforthisconversation.com`
2. Go to DNS Settings
3. Delete any existing A records pointing to your old WordPress host
4. Add these GitHub Pages A records:

```
Type: A     Name: @     Value: 185.199.108.153
Type: A     Name: @     Value: 185.199.109.153
Type: A     Name: @     Value: 185.199.110.153
Type: A     Name: @     Value: 185.199.111.153
```

5. Add a CNAME record for www subdomain:

```
Type: CNAME    Name: www    Value: USERNAME.github.io
```

#### B. Configure Custom Domain in GitHub:

1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `imbillingyouforthisconversation.com`
3. Click **Save**
4. Wait for DNS check to complete (can take up to 48 hours, usually 10-30 minutes)
5. Once verified, check **Enforce HTTPS**

## Contact Form Setup

The contact form on `contact.html` needs a backend service. Choose one:

### Option 1: Formspree (Recommended - Free tier available)

1. Go to [formspree.io](https://formspree.io)
2. Sign up for free account
3. Create a new form
4. Copy your form endpoint
5. In `contact.html`, replace `action="https://formspree.io/f/YOUR_FORM_ID"` with your actual endpoint

### Option 2: Netlify Forms (if hosting on Netlify instead)

1. Deploy to Netlify instead of GitHub Pages
2. Add `netlify` attribute to form tag
3. Netlify automatically handles form submissions

## Accessibility Features

This site meets **WCAG 2.1 Level AA** standards:

- ✅ Semantic HTML5 structure
- ✅ ARIA labels and roles
- ✅ Keyboard navigation support
- ✅ Skip to main content link
- ✅ Color contrast ratios ≥ 4.5:1
- ✅ Touch target sizes ≥ 44×44px
- ✅ Focus indicators
- ✅ Alt text for images
- ✅ Reduced motion support
- ✅ Screen reader compatible

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Android)

## Maintenance

### To Update Content:

1. Edit the HTML files locally
2. Commit and push changes:

```bash
git add .
git commit -m "Update content"
git push
```

GitHub Pages will automatically rebuild and deploy (usually takes 1-2 minutes).

### To Add Images:

1. Place images in the `images/` folder
2. Reference them in HTML: `<img src="images/your-image.jpg" alt="Description">`
3. Always include descriptive alt text for accessibility

## Performance Tips

- Images should be optimized (use tools like [TinyPNG](https://tinypng.com/))
- Recommended image formats: WebP (with JPG fallback), or optimized JPG/PNG
- Keep images under 200KB when possible

## Support

For issues with the website:
- Check the browser console for JavaScript errors
- Validate HTML at [validator.w3.org](https://validator.w3.org/)
- Test accessibility at [wave.webaim.org](https://wave.webaim.org/)

## License

© I'm Billing You For This Conversation® - All Rights Reserved

Registered with the U.S. Patent and Trademark Office.

---

**Note**: This is a static site. All product purchases are handled through Amazon using the links in the shop section.
