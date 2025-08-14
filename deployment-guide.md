# Deployment Guide - Kelly's Cookbook PWA

## For Alon: How to Deploy Kelly's Cookbook

### Quick Start (5 minutes)

1. **Get the Files**
   - The `cookbook-pwa` folder contains everything
   - Required files:
     - cookbook.html
     - manifest.json
     - service-worker.js
     - icon-192.png (generate from generate-icons.html)
     - icon-512.png (generate from generate-icons.html)
     - recipes.json (optional, for initial data)

2. **Generate Icons** (one-time)
   - Open `generate-icons.html` in any browser
   - Right-click each canvas → Save Image As
   - Save as `icon-192.png` and `icon-512.png`
   - Place in same folder as cookbook.html

3. **Host the Files**
   You have several options:

### Option A: GitHub Pages (Recommended - Free)
```bash
1. Create new GitHub repository
2. Upload all files from cookbook-pwa folder
3. Go to Settings → Pages
4. Source: Deploy from branch (main)
5. Visit: https://[username].github.io/[repo-name]/cookbook.html
```

### Option B: Netlify (Easy - Free)
```bash
1. Go to netlify.com
2. Drag cookbook-pwa folder to browser
3. Get instant URL like: https://amazing-site-123.netlify.app
4. Share URL with Kelly
```

### Option C: Local Network (Testing)
```bash
# Python (if installed)
cd cookbook-pwa
python -m http.server 8000

# Node.js (if installed)
npx http-server

# Access at: http://[your-ip]:8000/cookbook.html
```

## Installing on Kelly's iPhone

### Step-by-Step Instructions for Kelly:

1. **Open the Link**
   - Open Safari (must be Safari, not Chrome)
   - Go to the cookbook URL
   - Wait for page to load completely

2. **Install the App**
   - Tap the Share button (box with arrow)
   - Scroll down and tap "Add to Home Screen"
   - Name it "Kelly's Cookbook" 
   - Tap "Add"

3. **First Time Setup**
   - Open from home screen icon
   - The app works offline after first visit
   - Any existing recipes will load automatically

4. **Using the App**
   - **Add recipes**: Tap green "Add New Recipe" button
   - **Search**: Type in the search box
   - **View recipes**: Tap recipe names to expand
   - **Categories**: Tap category tabs to filter

5. **Backup Your Recipes**
   - Tap "💾 Backup Recipes" button
   - File saves to iPhone Files app
   - Name shows date and recipe count
   - Keep backups regularly!

6. **Restore from Backup**
   - Tap "📂 Restore Backup" button
   - Choose your backup file
   - Confirm to replace current recipes
   - All recipes restored instantly

## Troubleshooting

### App Won't Install
- **Issue**: No "Add to Home Screen" option
- **Fix**: Must use Safari, not Chrome or other browsers

### Icons Not Showing
- **Issue**: Generic icon on home screen
- **Fix**: Generate and upload icon PNG files

### Offline Not Working
- **Issue**: App needs internet after install
- **Fix**: Clear Safari cache, reinstall app

### Backup Not Downloading
- **Issue**: File doesn't save on iPhone
- **Fix**: Check iPhone storage, try different browser

### Can't Restore Backup
- **Issue**: Error when restoring
- **Fix**: Ensure backup file is valid JSON format

## Important URLs
Once deployed, Kelly needs these URLs:

```
Main App: https://[your-domain]/cookbook.html
Manifest: https://[your-domain]/manifest.json
Service Worker: https://[your-domain]/service-worker.js
```

## Technical Requirements
- **HTTPS required** for PWA features (except localhost)
- Modern browser (Safari 14+, Chrome 90+)
- ~10MB storage for recipes
- No server or database needed

## Maintenance

### Updating the App
1. Make changes to files
2. Update service worker version
3. Re-upload files
4. App auto-updates on next use

### Monitoring Usage
- Check browser console for errors
- Test backup/restore monthly
- Keep backup of Kelly's recipes

## Security Notes
- All data stored locally on device
- No server = no data breaches
- Backups are plain JSON files
- No passwords or accounts needed

## Support Contact
If Kelly has issues:
1. First try the troubleshooting steps
2. Test in another browser
3. Check iPhone has storage space
4. Create fresh backup before any fixes

## Success Checklist
- [ ] Icons generated and uploaded
- [ ] Site accessible via HTTPS
- [ ] Tested on iPhone Safari
- [ ] Kelly can install to home screen
- [ ] Backup/restore working
- [ ] Offline mode confirmed
- [ ] Kelly trained on usage

## Final Notes
- The app is simple by design
- No updates needed unless bugs found
- Kelly owns all her recipe data
- Backups are human-readable JSON

**Deployment Time: ~15 minutes**
**Kelly Training: ~10 minutes**
**Total Setup: ~25 minutes**