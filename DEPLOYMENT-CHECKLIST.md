# Deployment Checklist for imbillingyouforthisconversation.com

## Pre-Deployment Tasks

### ✅ Completed
- [x] WordPress content extracted
- [x] Static HTML pages created (index, shop, about, contact, 404)
- [x] WCAG 2.1 AA compliant CSS implemented
- [x] JavaScript for mobile menu and interactions
- [x] All 7 products with Amazon links included
- [x] Semantic HTML5 with ARIA labels
- [x] Keyboard navigation and skip links
- [x] Color contrast ratios meet 4.5:1 minimum
- [x] Responsive design for all screen sizes
- [x] GitHub Pages structure ready
- [x] CNAME file created
- [x] README with full instructions

### ⏳ Before Going Live

- [ ] **Add Product Images**: Currently using placeholders. You need to add actual product images to `images/` folder
- [ ] **Set up Contact Form**: Update `contact.html` with Formspree or Netlify Forms endpoint
- [ ] **Update Social Media Links**: Add real URLs in `contact.html` footer (currently placeholder "#")
- [ ] **Test all Amazon links**: Verify all 7 product URLs work
- [ ] **Add favicon**: Create and add `favicon.ico` to root directory
- [ ] **Optional**: Add Google Analytics or tracking code

---

## Deployment Steps

### 1. Initialize Git Repository
```bash
cd /Users/nathannantais/Coding/imbillingcustomsite/imbilling-github-pages
git init
git add .
git commit -m "Initial commit - WordPress to static site migration"
```

### 2. Create GitHub Repository
1. Go to https://github.com/new
2. Repository name: `imbilling-website` (or any name)
3. Set to **Public**
4. Do NOT initialize with README
5. Click "Create repository"

### 3. Push to GitHub
```bash
# Replace USERNAME/REPO with your GitHub username and repository name
git remote add origin https://github.com/USERNAME/REPO.git
git branch -M main
git push -u origin main
```

### 4. Enable GitHub Pages
1. Go to repository **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main**, Folder: **/ (root)**
4. Click **Save**
5. Wait 1-2 minutes for initial deployment

### 5. Configure Custom Domain

#### A. DNS Configuration (at your domain registrar)

**IMPORTANT**: Before changing DNS, make note of current settings in case you need to revert.

1. Log into your domain registrar (where you bought the domain)
2. Find DNS settings/DNS management
3. **Delete** old WordPress hosting records
4. **Add** these GitHub Pages A records:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 3600 |
| A | @ | 185.199.109.153 | 3600 |
| A | @ | 185.199.110.153 | 3600 |
| A | @ | 185.199.111.153 | 3600 |
| CNAME | www | USERNAME.github.io | 3600 |

5. Save DNS changes
6. **Wait 10-30 minutes** (can take up to 48 hours for full propagation)

#### B. GitHub Custom Domain Setup

1. In repository: **Settings** → **Pages**
2. Under "Custom domain", enter: `imbillingyouforthisconversation.com`
3. Click **Save**
4. Wait for DNS check (green checkmark)
5. Once verified, check ✅ **Enforce HTTPS**

---

## Post-Deployment Testing

### Accessibility Testing
- [ ] Test with screen reader (VoiceOver on Mac, NVDA on Windows)
- [ ] Navigate entire site using only keyboard (Tab, Enter, Escape)
- [ ] Run [WAVE accessibility checker](https://wave.webaim.org/)
- [ ] Verify skip link works
- [ ] Test with browser zoom at 200%

### Functionality Testing
- [ ] Click all 7 Amazon product links
- [ ] Test mobile menu on phone
- [ ] Submit contact form (after configuring form service)
- [ ] Test on multiple browsers (Chrome, Firefox, Safari, Edge)
- [ ] Test on mobile devices (iOS, Android)
- [ ] Verify 404 page works
- [ ] Check all internal links work

### SEO & Performance
- [ ] Verify meta descriptions on all pages
- [ ] Test page load speed with [PageSpeed Insights](https://pagespeed.web.dev/)
- [ ] Submit sitemap to Google Search Console
- [ ] Verify HTTPS is working (green padlock)

---

## Cancelling Old WordPress Hosting

**⚠️ IMPORTANT: Only do this AFTER confirming new site works perfectly**

### Before Cancelling:
1. ✅ New site live and working for at least 7 days
2. ✅ All Amazon links verified working
3. ✅ Email forwarding set up (if you had WordPress email)
4. ✅ Download final WordPress backup (just in case)

### When Cancelling:
- Cancel WordPress hosting subscription
- You may want to keep the domain registration active (if through same provider)
- Verify you're only cancelling hosting, not the domain name

---

## Troubleshooting

### Site Not Loading After DNS Change
- **Problem**: Domain shows old WordPress site or error
- **Solution**: DNS propagation takes time. Wait 24-48 hours. Check DNS with: https://dnschecker.org/

### HTTPS Not Working
- **Problem**: "Not Secure" warning in browser
- **Solution**:
  1. Ensure DNS is fully propagated
  2. GitHub Pages settings → verify domain
  3. Check "Enforce HTTPS"
  4. Wait 10-15 minutes

### 404 Errors on GitHub Pages
- **Problem**: Pages showing 404
- **Solution**:
  1. Ensure `index.html` is in root directory
  2. File names must match exactly (case-sensitive)
  3. Check GitHub Pages build status in Actions tab

### Mobile Menu Not Working
- **Problem**: Menu doesn't open on mobile
- **Solution**:
  1. Check browser console for JavaScript errors
  2. Verify `js/main.js` is loading
  3. Clear browser cache

---

## Maintenance

### Regular Updates
- Update copyright year annually (done automatically via JavaScript)
- Review and update product listings as needed
- Monitor Amazon links for changes
- Keep contact information current

### Adding New Products
1. Edit `shop.html`
2. Copy existing product card HTML structure
3. Update product title, description, and Amazon link
4. Commit and push changes:
```bash
git add shop.html
git commit -m "Add new product"
git push
```

### Updating Content
1. Edit HTML files locally
2. Test changes in browser
3. Commit and push:
```bash
git add .
git commit -m "Update content"
git push
```
4. Changes go live in 1-2 minutes

---

## Support Resources

- **GitHub Pages Docs**: https://docs.github.com/en/pages
- **WCAG Guidelines**: https://www.w3.org/WAI/WCAG21/quickref/
- **Formspree Setup**: https://formspree.io/
- **DNS Help**: Contact your domain registrar support

---

## Contact Form Services (Choose One)

### Formspree (Recommended)
- Free tier: 50 submissions/month
- https://formspree.io
- Easy setup, no coding required

### Netlify Forms
- Free tier: 100 submissions/month
- Requires hosting on Netlify instead of GitHub Pages
- https://www.netlify.com/products/forms/

### Alternative: Google Forms
- Completely free
- Embed Google Form instead of contact form
- Less professional appearance

---

## Estimated Costs After Migration

| Service | Cost |
|---------|------|
| **GitHub Pages Hosting** | **FREE** ✅ |
| **Domain Name** | ~$15/year (varies by registrar) |
| **SSL Certificate** | **FREE** (included with GitHub Pages) ✅ |
| **Contact Form** | **FREE** (Formspree free tier) ✅ |
| **Total Annual Cost** | **~$15/year** |

**Savings**: Approximately **$200-400/year** compared to WordPress hosting!

---

## Need Help?

If you encounter issues during deployment, check:
1. GitHub repository Actions tab for build errors
2. Browser console for JavaScript errors
3. GitHub Pages documentation
4. Stack Overflow for specific error messages

Good luck with your deployment! 🚀
