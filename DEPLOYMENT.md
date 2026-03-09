# Deployment Guide for AlgoTX Portfolio

## Quick Start
Simply open `index.html` in any modern web browser to view the portfolio locally.

## Deployment Options

### 1. GitHub Pages (Recommended - Free)
1. Create a new repository on GitHub
2. Push all files to the repository
3. Go to Settings > Pages
4. Select branch (main/master) and root folder
5. Your site will be live at `https://yourusername.github.io/repository-name`

### 2. Netlify (Free with Custom Domain)
1. Sign up at [netlify.com](https://netlify.com)
2. Drag and drop your project folder
3. Site will be live instantly
4. Optional: Add custom domain in settings

**Netlify Deploy Command:**
```bash
# Install Netlify CLI
npm install -g netlify-cli

# Deploy
netlify deploy --prod
```

### 3. Vercel (Free with Automatic Deployments)
1. Sign up at [vercel.com](https://vercel.com)
2. Import your GitHub repository
3. Automatic deployments on every push

**Vercel Deploy Command:**
```bash
# Install Vercel CLI
npm install -g vercel

# Deploy
vercel --prod
```

### 4. Firebase Hosting (Free Tier Available)
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login
firebase login

# Initialize
firebase init hosting

# Deploy
firebase deploy
```

### 5. Traditional Web Hosting (cPanel/FTP)
1. Compress all files into a ZIP
2. Upload to your hosting via FTP or File Manager
3. Extract in public_html or www directory
4. Access via your domain

## Pre-Deployment Checklist

- [ ] Update contact information in index.html
- [ ] Replace placeholder links with actual URLs
- [ ] Test all website demos
- [ ] Verify all forms work correctly
- [ ] Check mobile responsiveness
- [ ] Test in multiple browsers (Chrome, Firefox, Safari, Edge)
- [ ] Optimize images (if you add any)
- [ ] Update sitemap.xml with your actual domain
- [ ] Update robots.txt if needed
- [ ] Test 404 page
- [ ] Verify all internal links work

## Custom Domain Setup

### For GitHub Pages:
1. Add CNAME file with your domain
2. Configure DNS with your domain provider:
   - Add A records pointing to GitHub IPs
   - Or add CNAME record pointing to yourusername.github.io

### For Netlify/Vercel:
1. Go to domain settings in dashboard
2. Add your custom domain
3. Update DNS records as instructed

## Performance Optimization

### Already Implemented:
- Minified CSS and JavaScript
- Lazy loading for images
- Service Worker for offline support
- Optimized animations
- Efficient DOM manipulation

### Additional Optimizations (Optional):
```bash
# Minify HTML
npm install -g html-minifier
html-minifier --collapse-whitespace --remove-comments index.html -o index.min.html

# Optimize images (if you add any)
npm install -g imagemin-cli
imagemin images/* --out-dir=images/optimized
```

## SEO Optimization

### Already Included:
- Meta tags for SEO
- Open Graph tags for social sharing
- Twitter Card tags
- Sitemap.xml
- Robots.txt
- Semantic HTML structure

### Submit to Search Engines:
1. **Google Search Console**: https://search.google.com/search-console
2. **Bing Webmaster Tools**: https://www.bing.com/webmasters

## Analytics Setup (Optional)

### Google Analytics:
Add before closing `</head>` tag:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## Security Headers (For Production)

Add these headers in your hosting configuration:

```
X-Frame-Options: SAMEORIGIN
X-Content-Type-Options: nosniff
X-XSS-Protection: 1; mode=block
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: geolocation=(), microphone=(), camera=()
```

## Monitoring

### Uptime Monitoring:
- [UptimeRobot](https://uptimerobot.com) - Free
- [Pingdom](https://www.pingdom.com)

### Performance Monitoring:
- [Google PageSpeed Insights](https://pagespeed.web.dev)
- [GTmetrix](https://gtmetrix.com)
- [WebPageTest](https://www.webpagetest.org)

## Troubleshooting

### Issue: Styles not loading
- Check file paths are correct
- Ensure styles.css is in the same directory as index.html

### Issue: JavaScript not working
- Check browser console for errors
- Verify script.js is loading correctly
- Ensure Font Awesome CDN is accessible

### Issue: 404 errors on deployed site
- Verify all file paths are relative, not absolute
- Check file names match exactly (case-sensitive on Linux servers)

## Maintenance

### Regular Updates:
- Update contact information as needed
- Add new projects to showcase
- Keep dependencies (Font Awesome) up to date
- Monitor and fix broken links
- Update copyright year annually

## Support

For issues or questions:
- Email: ukasha@algotx.dev
- LinkedIn: linkedin.com/in/ukasha-ahmed

## License
© 2026 AlgoTX - Ukasha Ahmed. All rights reserved.
