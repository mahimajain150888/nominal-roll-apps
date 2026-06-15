# 🚀 Deploy to GitHub Pages (Free Hosting)

## Why GitHub Pages?
- ✅ Free forever
- ✅ Works from any device via URL
- ✅ No download needed
- ✅ Automatic HTTPS
- ✅ Fast global CDN

## Quick Setup (5 minutes)

### Step 1: Create GitHub Account
1. Go to https://github.com
2. Sign up (free)

### Step 2: Create Repository
1. Click "+" → "New repository"
2. Name: `nominal-roll-generator`
3. Make it Public
4. Click "Create repository"

### Step 3: Upload Files
1. Click "uploading an existing file"
2. Drag and drop these files:
   - `standalone_app.html` (Main app)
   - `master_data_manager.html` (Data management)
   - `static/master_data.json` (create static folder first)
   - `static/icon-192.png`
   - `static/icon-512.png`
   - `static/manifest.json`
   - `static/service-worker.js`
3. Click "Commit changes"

### Step 4: Enable GitHub Pages
1. Go to Settings → Pages
2. Source: "Deploy from a branch"
3. Branch: "main" → "/ (root)"
4. Click Save

### Step 5: Access Your Apps
Your apps will be live at:
- **Nominal Roll Generator:** `https://YOUR_USERNAME.github.io/nominal-roll-generator/standalone_app.html`
- **Master Data Manager:** `https://YOUR_USERNAME.github.io/nominal-roll-generator/master_data_manager.html`

## Share with Team
Just share the URLs! Everyone can:
- Open in any browser
- Use immediately
- No download needed
- Works on phone/tablet/computer

## Using Master Data Manager
The Master Data Manager allows you to:
- View all sewadar records
- Search and filter data
- Add new records
- Edit existing records
- Delete records
- Export updated data as JSON
- Import data from JSON files

**Important:** After making changes in the Master Data Manager:
1. Click "💾 Export JSON" to download the updated file
2. Upload the new `master_data.json` to GitHub (replace the old one)
3. Changes will be live immediately for all users

## Update Master Data
**Method 1: Via Master Data Manager (Recommended)**
1. Open the Master Data Manager URL
2. Make your changes (add/edit/delete records)
3. Export the updated JSON
4. Upload to GitHub

**Method 2: Direct Edit on GitHub**
1. Go to your repository
2. Navigate to `static/master_data.json`
3. Click "Edit" (pencil icon)
4. Make changes
5. Commit changes

Changes are live immediately after upload!

