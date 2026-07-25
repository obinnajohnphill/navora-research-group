# Deployment Guide - Navora Research Group Website

## 🚀 GitHub Pages Deployment

Your website is now live on GitHub! Here's how to enable GitHub Pages:

### Quick Setup (5 minutes)

1. **Go to your repository on GitHub:**
   - https://github.com/obinnajohnphill/navora-research-group

2. **Enable GitHub Pages:**
   - Click on **Settings** (gear icon)
   - Scroll down to **Pages** in the left sidebar
   - Under **Source**, select **main** branch
   - Click **Save**

3. **Your website will be live at:**
   - `https://obinnajohnphill.github.io/navora-research-group/`
   - Usually takes 1-2 minutes to deploy

### Custom Domain Setup (navoraresearch.org)

Once you're ready to use your custom domain:

#### 1. Add Custom Domain on GitHub

1. In **Settings → Pages**
2. Under **Custom domain**, enter: `www.navoraresearch.org`
3. Click **Save**
4. Enable **Enforce HTTPS** (after DNS propagates)

#### 2. Configure DNS Records

Add these records to your domain registrar (where you bought navoraresearch.org):

**A Records (for root domain):**
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**CNAME Record (for www subdomain):**
```
Type: CNAME
Name: www
Value: obinnajohnphill.github.io
```

#### 3. Add CNAME file to repository

Create a file named `CNAME` (no extension) in the root with:
```
www.navoraresearch.org
```

Then commit and push:
```bash
cd "/Users/obinnajohnphill/Desktop/Navora Research Group (NRG)/navora-research-group"
echo "www.navoraresearch.org" > CNAME
git add CNAME
git commit -m "Add custom domain configuration"
git push
```

---

## 🌐 Alternative Hosting Options

### Netlify (Recommended for Advanced Features)

1. Go to [netlify.com](https://netlify.com)
2. Click "Add new site" → "Import an existing project"
3. Connect to GitHub and select `navora-research-group`
4. Build settings:
   - Build command: (leave empty)
   - Publish directory: `.`
5. Click "Deploy site"
6. Your site will be live instantly with a netlify URL
7. Add custom domain in Site settings → Domain management

### Vercel

1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Import from GitHub: `navora-research-group`
4. Click "Deploy"
5. Add custom domain in Settings → Domains

---

## 📝 Post-Deployment Checklist

- [ ] Verify all pages load correctly
- [ ] Test navigation and smooth scrolling
- [ ] Check mobile responsiveness
- [ ] Test contact form
- [ ] Verify all research areas are displayed
- [ ] Check footer links
- [ ] Test on different browsers (Chrome, Safari, Firefox)
- [ ] Run Google Lighthouse audit for performance
- [ ] Add Google Analytics (optional)
- [ ] Submit to Google Search Console

---

## 🔧 Making Updates

### Local Development

1. Make changes to HTML/CSS/JS files
2. Test locally by opening `index.html` in browser
3. Commit changes:
   ```bash
   cd "/Users/obinnajohnphill/Desktop/Navora Research Group (NRG)/navora-research-group"
   git add .
   git commit -m "Description of changes"
   git push
   ```
4. Changes will auto-deploy to GitHub Pages (takes 1-2 minutes)

### Quick Edits on GitHub

1. Go to your repository
2. Click on the file you want to edit
3. Click the pencil icon (Edit)
4. Make changes
5. Scroll down, add commit message
6. Click "Commit changes"

---

## 📊 Analytics & Monitoring

### Add Google Analytics

Add this code before `</head>` in index.html:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR-GA-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR-GA-ID');
</script>
```

### Performance Monitoring

- Use [Google Lighthouse](https://developers.google.com/web/tools/lighthouse)
- Check [GTmetrix](https://gtmetrix.com)
- Monitor with [UptimeRobot](https://uptimerobot.com)

---

## 🆘 Troubleshooting

**Site not loading?**
- Check if GitHub Pages is enabled
- Verify the branch is set to `main`
- Wait 2-3 minutes for deployment

**Custom domain not working?**
- Verify DNS records are correct
- DNS can take 24-48 hours to propagate
- Use [DNS Checker](https://dnschecker.org) to verify

**Styles not loading?**
- Check file paths in index.html
- Verify CSS file is committed to repository
- Clear browser cache (Cmd+Shift+R on Mac)

---

## 📧 Support

For questions or issues:
- Email: info@navoraresearch.org
- GitHub Issues: https://github.com/obinnajohnphill/navora-research-group/issues

---

**Last Updated:** July 25, 2026
