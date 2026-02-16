# 📘 AFL Training PWA - Complete Setup Guide

## Table of Contents
1. [Deployment Options](#deployment-options)
2. [GitHub Pages Setup](#github-pages-setup)
3. [Local Development](#local-development)
4. [Creating Icons](#creating-icons)
5. [Customizing Backgrounds](#customizing-backgrounds)
6. [Testing PWA Features](#testing-pwa-features)
7. [Troubleshooting](#troubleshooting)

---

## Deployment Options

### Option 1: GitHub Pages (Recommended)
✅ Free hosting  
✅ HTTPS enabled (required for PWA)  
✅ No server needed  
✅ Easy updates via git push  

### Option 2: Local Testing
✅ Quick development  
✅ No internet needed after first load  
⚠️ Limited PWA features (no service worker on file://)  

### Option 3: Custom Server
✅ Full control  
✅ Custom domain  
⚠️ Requires HTTPS setup  

---

## GitHub Pages Setup

### Step 1: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top menu)
3. Scroll to **Pages** (left sidebar)
4. Under "Source":
   - Select branch: `main` or `master`
   - Select folder: `/ (root)`
5. Click **Save**
6. Wait 1-2 minutes for deployment

### Step 2: Access Your App

Your app will be available at:
```
https://alexalfarosoto-source.github.io/raouls-elite-AFL-programme
```

### Step 3: Install on Mobile

**iPhone (Safari):**
1. Open the URL
2. Tap Share button (⬆️)
3. Scroll and tap "Add to Home Screen"
4. Name it "AFL Training"
5. Tap "Add"

**Android (Chrome):**
1. Open the URL
2. Tap menu (⋮)
3. Tap "Install app" or "Add to Home screen"
4. Confirm installation

---

## Local Development

### Basic Setup

1. **Clone the repository:**
```bash
git clone https://github.com/alexalfarosoto-source/raouls-elite-AFL-programme.git
cd raouls-elite-AFL-programme
```

2. **Open in browser:**
   - Double-click `index.html`, OR
   - Right-click → Open with → Browser

### With Local Server (Better PWA support)

**Option A: Python**
```bash
# Python 3
python -m http.server 8000

# Then open: http://localhost:8000
```

**Option B: Node.js (npx)**
```bash
npx serve

# Then open: http://localhost:3000
```

**Option C: VS Code Live Server**
1. Install "Live Server" extension
2. Right-click `index.html`
3. Click "Open with Live Server"

---

## Creating Icons

### Requirements
- Two PNG files: `icon-192.png` (192x192) and `icon-512.png` (512x512)
- Square images only
- Clear, simple design works best

### Quick Methods

#### Method 1: Emoji Icon (Easiest)
1. Go to https://favicon.io/emoji-favicons/
2. Choose emoji: 🏈 or 👑 or ⚡
3. Download and extract
4. Rename files to `icon-192.png` and `icon-512.png`
5. Place in root directory

#### Method 2: Custom Design (Canva)
1. Go to https://canva.com (free account)
2. Create custom size: 512x512
3. Design your icon:
   - Background: Dark purple (#1e3a8a)
   - Text: "AFL" or "ARISE"
   - Add emojis: 👑⚡🏈
4. Download as PNG
5. Resize to 192x192 for second icon

#### Method 3: AI Generation
1. Use any AI image generator
2. Prompt: "App icon for AFL training app, dark purple background, lightning and crown symbol, minimalist, square"
3. Download and resize to 192x192 and 512x512

### Color Scheme Suggestions
- Primary: #1e3a8a (dark blue)
- Secondary: #8b5cf6 (purple)
- Accent: #fbbf24 (yellow/gold)
- Dark: #0f172a (slate)

---

## Customizing Backgrounds

### Where to Find the Code

Open `index.html` and find these sections:

#### 1. Quest Backgrounds (Around line 50)
```javascript
const QUEST_BACKGROUNDS = {
    speed: 'YOUR_URL_HERE',
    kicking: 'YOUR_URL_HERE',
    handball: 'YOUR_URL_HERE',
    marks: 'YOUR_URL_HERE',
    groundballs: 'YOUR_URL_HERE',
    endurance: 'YOUR_URL_HERE'
};
```

#### 2. Main Menu Background (Around line 245)
```javascript
<div 
    className="absolute inset-0 bg-cover bg-center bg-no-repeat"
    style={{ 
        backgroundImage: "url('YOUR_URL_HERE')",
        filter: 'brightness(0.3)'
    }}
/>
```

### Getting Image URLs

#### Option 1: Imgur (Recommended)
1. Go to https://imgur.com
2. Click "New post"
3. Upload your image
4. Right-click uploaded image → "Copy image address"
5. Use this URL in the code

#### Option 2: Unsplash
1. Go to https://unsplash.com
2. Search for images
3. Click image → Copy photo URL
4. Add `?w=1600&q=80` to the end

#### Option 3: Host Your Own
If using GitHub Pages, you can:
1. Create `images` folder
2. Add your images there
3. Use relative paths: `/images/yourimage.jpg`

### Theme Ideas

**Sung Jin-Woo Themes:**
- Search: "dark warrior", "shadow king", "fantasy warrior"
- Look for: dark backgrounds, purple/blue tones, dramatic lighting

**AFL Themes:**
- Stadium shots
- Action photos
- Australian football fields
- Player silhouettes

---

## Testing PWA Features

### Checklist

✅ **Manifest Test:**
1. Open Developer Tools (F12)
2. Go to "Application" tab
3. Click "Manifest" in sidebar
4. Check if all fields load correctly

✅ **Service Worker Test:**
1. Developer Tools → Application → Service Workers
2. Should see "sw.js" registered
3. Try toggling "Offline" checkbox
4. Refresh page - should still work

✅ **Install Test:**
1. Desktop Chrome: Look for install icon (⊕) in address bar
2. Mobile: Check if "Add to Home Screen" prompt appears
3. After install: Check if app opens in standalone mode

✅ **Storage Test:**
1. Complete a quest
2. Close and reopen app
3. Stats should persist

✅ **Offline Test:**
1. Open app online once
2. Turn off WiFi/data
3. Close and reopen app
4. Should still work (except images)

---

## Troubleshooting

### PWA Not Installing

**Problem:** No install prompt appears

**Solutions:**
1. Make sure you're using HTTPS (GitHub Pages does this automatically)
2. Check manifest.json is loading (Dev Tools → Network)
3. Verify icons exist (or remove icon references from manifest)
4. Try different browser (Chrome works best)
5. Check service worker is registered

### Service Worker Not Working

**Problem:** "SW failed" in console

**Solutions:**
1. Make sure `sw.js` is in root directory
2. Check file path is correct (`/sw.js`)
3. Clear browser cache and reload
4. Check for JavaScript errors in console

### Images Not Loading

**Problem:** Backgrounds appear black or broken

**Solutions:**
1. Verify image URLs are direct links (end in .jpg, .png, etc.)
2. Check URLs are HTTPS (not HTTP)
3. Try opening URL directly in browser
4. Check for CORS issues in console
5. Use Unsplash placeholders as backup

### Stats Not Saving

**Problem:** Progress resets on reload

**Solutions:**
1. Check localStorage is enabled in browser
2. Don't use private/incognito mode
3. Check browser storage isn't full
4. Look for JavaScript errors in console

### App Not Updating

**Problem:** Changes don't appear after git push

**Solutions:**
1. Wait 1-2 minutes after push
2. Hard refresh: Ctrl+Shift+R (Cmd+Shift+R on Mac)
3. Clear browser cache
4. Unregister service worker and reload
5. Check GitHub Actions completed successfully

---

## Advanced Customization

### Changing Colors

Find Tailwind classes in `index.html` and modify:
- `bg-purple-600` → change purple to blue, green, red, etc.
- `text-yellow-400` → change text colors
- `from-slate-900` → change gradient colors

### Adding New Quests

1. Add to `QUESTS` object (around line 55)
2. Add background to `QUEST_BACKGROUNDS`
3. Follow existing quest structure
4. Set `unlocked: true` or false

### Changing Rank Names

Edit `RANKS` array (around line 40):
```javascript
{ name: 'YOUR-RANK', minXP: 0, color: 'text-gray-400' }
```

### Adjusting Difficulty

In quest definitions, change:
- `duration`: seconds for timed quests
- `targets`: reps for counter quests
- `rewards`: XP and stat gains

---

## Resources

### Learning Resources
- [PWA Documentation](https://web.dev/progressive-web-apps/)
- [React Basics](https://react.dev/learn)
- [Tailwind CSS](https://tailwindcss.com/docs)

### Image Resources
- [Unsplash](https://unsplash.com) - Free stock photos
- [Imgur](https://imgur.com) - Image hosting
- [Favicon.io](https://favicon.io) - Icon generator

### Testing Tools
- [Lighthouse](https://developers.google.com/web/tools/lighthouse) - PWA audit
- [PWA Builder](https://www.pwabuilder.com/) - PWA testing
- Chrome DevTools - Built-in debugging

---

## Support

### Common Issues
- Check existing GitHub Issues
- Review this guide's Troubleshooting section
- Test in different browsers

### Making Changes
1. Edit files locally
2. Test in browser
3. Commit and push to GitHub
4. Wait for GitHub Pages to update

---

**Good luck with your AFL training! 🏈⚡👑**
