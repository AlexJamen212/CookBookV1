# Test Checklist - Kelly's Cookbook PWA

## Pre-Deployment Testing

### 🌐 Server Setup
- [ ] Navigate to cookbook-pwa folder
- [ ] Run a local server (Python: `python -m http.server 8000` or Node: `npx http-server`)
- [ ] Open http://localhost:8000/cookbook.html
- [ ] Verify page loads without errors

### 📱 PWA Installation
- [ ] Open site in Chrome/Safari on iPhone
- [ ] Look for "Add to Home Screen" prompt
- [ ] Install the app to home screen
- [ ] Verify app icon appears correctly
- [ ] Launch app from home screen
- [ ] Confirm full-screen mode (no browser UI)

### 🔌 Offline Functionality
- [ ] With app installed, add some recipes
- [ ] Turn on Airplane Mode
- [ ] Close and reopen the app
- [ ] Verify app loads without internet
- [ ] Check all recipes are still accessible
- [ ] Try adding a new recipe offline
- [ ] Turn internet back on and verify sync

### 🍳 Recipe Management
- [ ] **Add Recipe**
  - [ ] Click "Add New Recipe"
  - [ ] Fill in all fields
  - [ ] Add multiple video links
  - [ ] Save recipe
  - [ ] Verify recipe appears in correct category
  
- [ ] **View Recipe**
  - [ ] Click recipe to expand
  - [ ] Verify all content displays correctly
  - [ ] Check video links open TikTok
  - [ ] Collapse recipe
  
- [ ] **Edit Recipe**
  - [ ] Click Edit on a recipe
  - [ ] Modify all fields
  - [ ] Save changes
  - [ ] Verify updates saved
  
- [ ] **Delete Recipe**
  - [ ] Click Delete on a recipe
  - [ ] Confirm deletion prompt appears
  - [ ] Accept deletion
  - [ ] Verify recipe removed

### 🔍 Search Functionality
- [ ] Type in search box
- [ ] Verify real-time filtering
- [ ] Search by recipe name
- [ ] Search by ingredient
- [ ] Clear search and verify all recipes return

### 📂 Categories
- [ ] Click each category tab
- [ ] Verify correct recipes display
- [ ] Check recipe counts are accurate
- [ ] Verify "Mains" is default category

### 💾 Backup System
- [ ] **Create Backup**
  - [ ] Click "💾 Backup Recipes"
  - [ ] Verify file downloads
  - [ ] Check filename format: `kellys-recipes-YYYY-MM-DD.json (X recipes)`
  - [ ] Open file and verify JSON structure
  
- [ ] **Restore Backup**
  - [ ] Click "📂 Restore Backup"
  - [ ] Select backup file
  - [ ] Verify confirmation dialog shows recipe counts
  - [ ] Confirm restore
  - [ ] Check success message
  - [ ] Verify recipes replaced correctly

### 📱 Mobile Experience
- [ ] **Touch Targets**
  - [ ] All buttons easy to tap (44px minimum)
  - [ ] No accidental taps
  - [ ] Smooth scrolling
  
- [ ] **Responsive Layout**
  - [ ] No horizontal scrolling
  - [ ] Text readable without zooming
  - [ ] Forms usable on small screen
  - [ ] Modal dialogs fit screen
  
- [ ] **iOS Specific**
  - [ ] No zoom on input focus
  - [ ] Keyboard doesn't cover inputs
  - [ ] Status bar color matches theme

### 🔒 Security Testing
- [ ] Try entering HTML in recipe fields
- [ ] Verify no script execution
- [ ] Check localStorage data is sanitized
- [ ] Test with special characters in names
- [ ] Verify backup files don't contain sensitive data

### ⚡ Performance
- [ ] App loads quickly (< 3 seconds)
- [ ] Smooth scrolling with many recipes
- [ ] No lag when typing in search
- [ ] Quick recipe expansion/collapse
- [ ] Fast category switching

### 🐛 Edge Cases
- [ ] Add recipe with empty videos
- [ ] Try very long recipe names
- [ ] Test with 100+ recipes
- [ ] Restore corrupted backup file
- [ ] Use special characters/emojis
- [ ] Test on different browsers

## Browser Testing Matrix

| Browser | Desktop | Mobile | PWA Install | Offline |
|---------|---------|--------|-------------|---------|
| Safari iOS | N/A | ✅ | ✅ | ✅ |
| Chrome iOS | N/A | ✅ | ✅ | ✅ |
| Chrome Desktop | ✅ | N/A | ✅ | ✅ |
| Safari Desktop | ✅ | N/A | ❌ | ✅ |
| Firefox | ✅ | ✅ | ❌ | ✅ |
| Edge | ✅ | ✅ | ✅ | ✅ |

## Known Limitations
- PWA install only on Chromium browsers and iOS Safari
- File download names may vary by browser
- Video links require TikTok app for best experience

## Test Data
Use this sample recipe for testing:

```json
{
  "name": "Test Recipe",
  "category": "Mains",
  "ingredients": "1 cup test\n2 tbsp testing\n3 validation checks",
  "instructions": "1. Test the app\n2. Find bugs\n3. Fix and repeat",
  "videos": [
    {
      "link": "https://www.tiktok.com/@test",
      "name": "Test Video"
    }
  ]
}
```

## Sign-off
- [ ] All critical features working
- [ ] No security vulnerabilities
- [ ] Mobile experience smooth
- [ ] Backup/restore reliable
- [ ] Ready for Kelly to use!