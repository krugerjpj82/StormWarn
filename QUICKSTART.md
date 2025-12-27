# Quick Start Guide - Upload to GitHub

## Extract the Archive

**If you downloaded `.zip`:**
```bash
unzip stormwarn-github.zip
cd stormwarn-github
```

**If you downloaded `.tar.gz`:**
```bash
tar -xzf stormwarn-github.tar.gz
cd stormwarn-github
```

## Upload to GitHub

### Method 1: GitHub Web Interface (Easiest)

1. Go to [GitHub.com](https://github.com) and sign in
2. Click "+" in top right → "New repository"
3. Name it `stormwarn` (or any name you prefer)
4. Choose "Public" or "Private"
5. **Don't** initialize with README (we have one)
6. Click "Create repository"
7. Click "uploading an existing file"
8. Drag all files from the extracted folder
9. Click "Commit changes"

### Method 2: Git Command Line

```bash
# Initialize git repository
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit - StormWarn v1.0.0"

# Add your GitHub repository as remote (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/stormwarn.git

# Push to GitHub
git push -u origin main
```

If you get an error about the default branch name:
```bash
git branch -M main
git push -u origin main
```

## Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in the left sidebar
4. Under "Source", select "main" branch
5. Click "Save"
6. Wait 1-2 minutes
7. Your site will be live at: `https://YOUR-USERNAME.github.io/stormwarn`

## Update with Your Information

### Update README.md
Replace the following placeholders:
- `yourusername` → Your GitHub username
- `stormwarn.manus.space` → Your domain (if applicable)

### Update index.html (Optional)
If you want to change the default location from Cape Town:
- Find line ~450: `fetchWeather(-33.9249, 18.4241);`
- Replace with your city's coordinates

## Test Your Deployment

1. Visit your GitHub Pages URL
2. Allow location access (or it will use Cape Town)
3. Verify weather loads correctly
4. Test search functionality
5. Test saving locations
6. Test WhatsApp sharing

## Troubleshooting

### Site Not Loading
- Wait a few minutes (GitHub Pages can take time)
- Check Settings → Pages for deployment status
- Clear browser cache

### 404 Error
- Make sure file is named `index.html` (lowercase)
- Check branch is set to `main` in Pages settings

### Weather Not Loading
- Check browser console (F12) for errors
- Verify you have internet connection
- Try a different browser

## Next Steps

1. ✅ Star the repository
2. ✅ Add a screenshot (replace `screenshot.md` with `screenshot.png`)
3. ✅ Customize for your region
4. ✅ Share with friends
5. ✅ Consider contributing improvements

## Support

Need help? 
- Open an issue on GitHub
- Check existing issues for solutions
- Read the full documentation in README.md

---

**Congratulations! Your weather app is now live! 🎉**

Share the URL: `https://YOUR-USERNAME.github.io/stormwarn`
