# Vera North Group - Professional Website

A McKinsey-style professional consulting website built with modern HTML, CSS, and JavaScript.

## Features

- **Professional Design**: Refined minimalism with luxury aesthetics
- **Distinctive Typography**: Cormorant Garamond (display) paired with Work Sans (body)
- **Sophisticated Color Palette**: Deep navy, blue, and gold accents
- **Smooth Animations**: Fade-in effects and micro-interactions
- **Fully Responsive**: Works beautifully on all devices
- **Performance Optimized**: Fast loading, minimal dependencies

## Deployment to GitHub Pages

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the "+" icon and select "New repository"
3. Name it `veranorthgroup` (or your preferred name)
4. Make it public
5. Don't initialize with README (we'll push this one)
6. Click "Create repository"

### Step 2: Push Your Code

From your project directory (where index.html is):

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit: Professional McKinsey-style website"

# Set main branch
git branch -M main

# Add remote (replace YOUR-USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR-USERNAME/veranorthgroup.git

# Push to GitHub
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" in the left sidebar
4. Under "Source", select `main` branch
5. Click "Save"
6. Your site will be live at: `https://YOUR-USERNAME.github.io/veranorthgroup/`

## Connect Your Namecheap Domain

### Step 1: Configure DNS in Namecheap

1. Log in to [Namecheap](https://www.namecheap.com)
2. Go to "Domain List" and click "Manage" next to your domain
3. Navigate to "Advanced DNS" tab
4. Delete any existing A Records and CNAME Record for `www`
5. Add these new records:

**A Records** (all pointing to GitHub's servers):
```
Type: A Record
Host: @
Value: 185.199.108.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.109.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.110.153
TTL: Automatic

Type: A Record
Host: @
Value: 185.199.111.153
TTL: Automatic
```

**CNAME Record**:
```
Type: CNAME Record
Host: www
Value: YOUR-USERNAME.github.io
TTL: Automatic
```

6. Click "Save All Changes"

### Step 2: Configure Custom Domain in GitHub

1. Go to your repository on GitHub
2. Click "Settings" → "Pages"
3. Under "Custom domain", enter: `yourdomain.com` (e.g., `veranorthgroup.com`)
4. Click "Save"
5. Wait for DNS check to complete (can take 10 minutes to 48 hours)
6. Once verified, check "Enforce HTTPS" (recommended)

### Step 3: Create CNAME File

Create a file named `CNAME` (no extension) in your project root:

```
yourdomain.com
```

Then push to GitHub:

```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

## Customization Guide

### Change Colors

Edit the CSS variables in `index.html`:

```css
:root {
    --primary-navy: #0A2540;      /* Main dark blue */
    --secondary-blue: #1E4D7B;    /* Secondary blue */
    --accent-gold: #C9A961;       /* Gold accent */
    --text-primary: #1A1A1A;      /* Main text */
    --text-secondary: #5A5A5A;    /* Secondary text */
}
```

### Change Images

Replace the Unsplash URLs with your own images:

```html
<!-- Example: Change service card image -->
<img src="https://images.unsplash.com/photo-..." alt="...">
<!-- Replace with: -->
<img src="images/your-image.jpg" alt="...">
```

### Update Content

Simply edit the HTML text:
- Hero headline: Line ~670
- Service descriptions: Lines ~720-750
- About section: Lines ~780-800
- Footer: Lines ~870-900

### Add Your Own Images

1. Create an `images` folder in your project
2. Add your images there
3. Update image paths in HTML:
   ```html
   <img src="images/your-photo.jpg" alt="Description">
   ```
4. Commit and push:
   ```bash
   git add images/
   git commit -m "Add custom images"
   git push
   ```

## File Structure

```
veranorthgroup/
├── index.html          # Main website file (HTML + CSS + JS)
├── README.md           # This file
└── CNAME              # Custom domain configuration
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Tips

1. **Compress Images**: Use [TinyPNG](https://tinypng.com) before uploading
2. **Image Format**: Use WebP for better compression (with JPG fallback)
3. **Lazy Loading**: Images load as user scrolls (already implemented)
4. **Caching**: GitHub Pages automatically caches static assets

## Troubleshooting

### DNS Not Propagating
- DNS changes can take up to 48 hours
- Check status: [WhatsMyDNS](https://www.whatsmydns.net)
- Clear browser cache and try incognito mode

### HTTPS Not Working
- Wait for DNS to fully propagate
- Make sure "Enforce HTTPS" is checked in GitHub Pages settings
- Certificate provisioning can take 15-30 minutes

### Custom Domain Shows 404
- Verify CNAME file exists in repository root
- Check that DNS records are correct
- Try removing and re-adding custom domain in GitHub

### Images Not Loading
- Check image URLs are correct
- Verify images are committed to repository
- Check browser console for errors (F12)

## License

This website template is free to use and modify for your business.

## Support

For issues or questions:
- GitHub Issues: Create an issue in your repository
- Email: contact@veranorthgroup.com

---

Built with modern web technologies. No frameworks, just clean code.
