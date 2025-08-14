# PWA Requirements & Implementation Plan

## Project Goal
Convert Kelly's Cookbook desktop version into a Progressive Web App for iPhone

## Core Requirements

### 1. PWA Installation
- ✅ Must install on iPhone home screen
- ✅ Full-screen standalone mode
- ✅ App icon and splash screen
- ✅ Works offline after installation

### 2. Data Storage Migration
**Current State:**
- Server stores recipes in recipes.json
- Client fetches via API calls
- LocalStorage only for UI preferences

**Target State:**
- All recipes stored in browser localStorage
- No server dependency after initial load
- Offline-first architecture

### 3. Backup System
- One-button backup to JSON file
- Auto-naming: `kellys-recipes-YYYY-MM-DD.json (X recipes)`
- One-button restore from JSON file
- Must work on iPhone (Files app integration)

## Files to Modify

### New Files to Create:
1. `manifest.json` - PWA manifest for installation
2. `service-worker.js` - Offline caching and functionality
3. `icons/` directory - App icons (192x192, 512x512)

### Files to Update:
1. `cookbook.html` - Add PWA integration, backup/restore, localStorage

### Files to Copy (unchanged):
1. `recipes.json` - Initial data seed

## Implementation Steps

### Phase 1: PWA Foundation
1. Create manifest.json with app metadata
2. Generate app icons
3. Create service worker for offline caching
4. Update HTML with PWA registration

### Phase 2: Data Storage Migration
1. Remove server dependency from cookbook.html
2. Implement localStorage for recipes
3. Add data migration from recipes.json
4. Update all CRUD operations for localStorage

### Phase 3: Backup/Restore System
1. Add backup button to UI
2. Implement JSON export with auto-naming
3. Add restore button to UI
4. Implement file import with validation
5. Test on iPhone Safari

### Phase 4: Mobile Optimization
1. Ensure responsive design works on iPhone
2. Test touch interactions
3. Optimize for mobile viewport
4. Fix any UI issues

## Technical Specifications

### Manifest.json Requirements:
```json
{
  "name": "Kelly's Cookbook",
  "short_name": "Cookbook",
  "display": "standalone",
  "orientation": "portrait",
  "theme_color": "#d4a574",
  "background_color": "#faf6f0"
}
```

### Service Worker Strategy:
- Cache-first for static assets
- Network-first for dynamic content (during development)
- Version management for updates

### localStorage Schema:
```javascript
{
  "cookbook_recipes": [/* array of recipe objects */],
  "cookbook_version": "1.0.0",
  "cookbook_lastBackup": "2025-08-14"
}
```

## Security Considerations
1. Sanitize all inputs before storage
2. Validate JSON structure on restore
3. Add Content Security Policy
4. No external dependencies

## Success Metrics
- [ ] Installs on iPhone home screen
- [ ] Works completely offline
- [ ] Backup downloads file successfully
- [ ] Restore loads and validates data
- [ ] All CRUD operations work
- [ ] Security scan passes