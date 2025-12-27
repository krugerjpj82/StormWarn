# Deployment Guide

## Quick Deploy Options

### 1. GitHub Pages (Recommended)

**Steps:**
1. Push your code to GitHub
2. Go to repository Settings → Pages
3. Select `main` branch as source
4. Click Save
5. Your site will be live at `https://yourusername.github.io/stormwarn`

**Advantages:**
- ✅ Free hosting
- ✅ Automatic SSL
- ✅ Custom domain support
- ✅ Fast CDN delivery

### 2. Netlify

**Method 1: Drag & Drop**
1. Go to [Netlify Drop](https://app.netlify.com/drop)
2. Drag `index.html` onto the page
3. Done! Instant deployment

**Method 2: Git Integration**
1. Sign up at [Netlify](https://netlify.com)
2. Click "New site from Git"
3. Connect your GitHub repository
4. Deploy!

**Advantages:**
- ✅ Instant deploys
- ✅ Automatic SSL
- ✅ Custom domains
- ✅ Preview deployments

### 3. Vercel

**Steps:**
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
vercel
```

**Advantages:**
- ✅ Fast edge network
- ✅ Automatic SSL
- ✅ Easy custom domains

### 4. Cloudflare Pages

**Steps:**
1. Sign up at [Cloudflare Pages](https://pages.cloudflare.com)
2. Connect GitHub repository
3. Deploy automatically

**Advantages:**
- ✅ Global CDN
- ✅ DDoS protection
- ✅ Analytics included

### 5. Custom Server

**Apache:**
```apache
# .htaccess (if needed)
<IfModule mod_rewrite.c>
    RewriteEngine On
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteRule ^(.*)$ index.html [L]
</IfModule>
```

**Nginx:**
```nginx
server {
    listen 80;
    server_name stormwarn.yourdomain.com;
    
    root /var/www/stormwarn;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

## Custom Domain Setup

### GitHub Pages
1. Add `CNAME` file with your domain
2. Update DNS records:
   ```
   CNAME: www → yourusername.github.io
   A: @ → 185.199.108.153
   ```

### Netlify
1. Go to Domain Settings
2. Add custom domain
3. Update DNS to Netlify nameservers

### Cloudflare
1. Add site to Cloudflare
2. Update nameservers
3. Deploy to Cloudflare Pages

## Performance Optimization

### Enable Compression
Most hosting platforms enable this automatically, but for custom servers:

**Apache:**
```apache
<IfModule mod_deflate.c>
    AddOutputFilterByType DEFLATE text/html text/css application/javascript
</IfModule>
```

**Nginx:**
```nginx
gzip on;
gzip_types text/html text/css application/javascript;
```

### Enable Caching

**Apache:**
```apache
<IfModule mod_expires.c>
    ExpiresActive On
    ExpiresByType text/html "access plus 1 hour"
</IfModule>
```

**Nginx:**
```nginx
location ~* \.(html)$ {
    expires 1h;
}
```

## SSL/HTTPS

All recommended hosting platforms provide free SSL certificates automatically via Let's Encrypt.

For custom servers:
```bash
# Install Certbot
sudo apt-get install certbot

# Get certificate
sudo certbot --nginx -d yourdomain.com
```

## Monitoring

### Uptime Monitoring
- [UptimeRobot](https://uptimerobot.com) - Free uptime monitoring
- [StatusCake](https://statuscake.com) - Free tier available

### Analytics
Add to `index.html` before `</head>`:

**Google Analytics:**
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

**Plausible Analytics (Privacy-focused):**
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

## Troubleshooting

### Site Not Loading
1. Check DNS propagation: [whatsmydns.net](https://whatsmydns.net)
2. Verify file is named `index.html` (lowercase)
3. Check browser console for errors

### API Issues
1. Verify browser supports CORS
2. Check API endpoints are reachable
3. Look for rate limiting errors

### Geolocation Not Working
1. Must be served over HTTPS
2. User must grant permission
3. Falls back to Cape Town automatically

## Support

Need help deploying? Open an issue on GitHub!
