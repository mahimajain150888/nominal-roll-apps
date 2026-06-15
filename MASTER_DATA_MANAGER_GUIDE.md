# 📊 Master Data Manager - Complete Guide

## 🎯 Overview

The Master Data Manager is a standalone web application that allows you to:
- ✅ View all 1,239+ sewadar records
- ✅ Add new records
- ✅ Edit existing records
- ✅ Delete records
- ✅ Search and filter data
- ✅ Export updated master_data.json
- ✅ Import data from JSON files
- ✅ Works completely offline

## 📱 Features

### 1. **View Records**
- Paginated table view (20 records per page)
- Shows: Name, Father's name, Gender, Age, Contact, Badge ID
- Real-time statistics (Total records, Filtered records)

### 2. **Search & Filter**
- Search by: Name, Father's name, Contact, Badge ID, Address
- Real-time filtering as you type
- Shows filtered count

### 3. **Add New Records**
- Click "➕ Add New Record" button
- Fill in the form:
  - Name (required)
  - Father/Husband/Mother Name
  - Gender (required)
  - Age
  - Aadhar Number (12 digits)
  - Address
  - Contact Number (required, 10 digits)
  - Badge ID
- Click "Save Record"

### 4. **Edit Records**
- Click "✏️ Edit" button on any record
- Modify the fields
- Click "Save Record"

### 5. **Delete Records**
- Click "🗑️ Delete" button
- Confirm deletion
- Record removed permanently

### 6. **Export Data**
- Click "💾 Export JSON" button
- Downloads: `master_data_YYYY-MM-DD.json`
- Use this file to update your apps

### 7. **Import Data**
- Click "📁 Import JSON" button
- Select a JSON file
- Confirms before replacing current data

## 🚀 How to Use

### Local Usage (Offline)

1. **Open the app:**
   - Double-click `master_data_manager.html`
   - Or open in browser: `file:///path/to/master_data_manager.html`

2. **Make changes:**
   - Add, edit, or delete records
   - Search and filter as needed

3. **Export updated data:**
   - Click "💾 Export JSON"
   - Save the file as `master_data.json`

4. **Update your apps:**
   - Replace `static/master_data.json` in both apps:
     - `standalone_app.html` (Nominal Roll Generator)
     - `master_data_manager.html` (this app)

### Deploy to GitHub Pages

Follow these steps to host the Master Data Manager online:

## 📦 GitHub Pages Deployment

### Step 1: Prepare Your Repository

If you already have a repository from the Nominal Roll Generator:

1. **Add the manager to existing repo:**
   ```bash
   # Navigate to your repo folder
   cd nominal-roll-generator
   
   # Copy the manager file
   cp /path/to/master_data_manager.html .
   
   # Commit and push
   git add master_data_manager.html
   git commit -m "Add master data manager"
   git push
   ```

2. **Access it at:**
   `https://YOUR_USERNAME.github.io/nominal-roll-generator/master_data_manager.html`

### Step 2: Create New Repository (If Starting Fresh)

1. **Go to GitHub.com**
   - Click "+" → "New repository"
   - Name: `master-data-manager`
   - Make it Public
   - Click "Create repository"

2. **Upload Files:**
   - Click "uploading an existing file"
   - Upload:
     - `master_data_manager.html`
     - Create `static` folder
     - Upload `static/master_data.json`
   - Commit changes

3. **Enable GitHub Pages:**
   - Go to Settings → Pages
   - Source: "Deploy from a branch"
   - Branch: "main" → "/ (root)"
   - Save

4. **Access Your App:**
   `https://YOUR_USERNAME.github.io/master-data-manager/master_data_manager.html`

### Step 3: Update Master Data on GitHub

When you make changes:

1. **Export from the app:**
   - Click "💾 Export JSON"
   - Download the updated file

2. **Upload to GitHub:**
   - Go to your repository
   - Navigate to `static/master_data.json`
   - Click "Edit" (pencil icon)
   - Paste new content
   - Commit changes

3. **Changes go live immediately!**
   - All users see updated data
   - No need to re-deploy

## 🔄 Workflow: Update Master Data

### Complete Update Process:

```
1. Open Master Data Manager
   ↓
2. Make changes (Add/Edit/Delete)
   ↓
3. Export JSON (💾 Export JSON button)
   ↓
4. Upload to GitHub (replace static/master_data.json)
   ↓
5. Both apps now use updated data!
   - Nominal Roll Generator
   - Master Data Manager
```

## 📱 Mobile Usage

### On Android/iOS:

1. **Access via URL:**
   - Open browser
   - Go to your GitHub Pages URL
   - Works like a native app!

2. **Add to Home Screen:**
   - Chrome: Menu → "Add to Home screen"
   - Safari: Share → "Add to Home Screen"

3. **Use offline:**
   - After first load, works without internet
   - Make changes offline
   - Export when back online

## 🔒 Data Security

- ✅ All data stays in browser (no server)
- ✅ Changes only saved when you export
- ✅ No automatic cloud sync
- ✅ You control all data
- ✅ Aadhar numbers visible (for editing)

## 💡 Pro Tips

### 1. **Regular Backups**
```bash
# Export data regularly
# Name files with dates: master_data_2026-05-03.json
# Keep multiple versions
```

### 2. **Bulk Updates**
- Export JSON
- Edit in text editor (for bulk changes)
- Import back

### 3. **Data Validation**
- Contact: Must be 10 digits
- Aadhar: Must be 12 digits
- Gender: M or F only
- Age: 0-150

### 4. **Search Tips**
- Search works on: Name, Father's name, Contact, Badge, Address
- Case-insensitive
- Partial matches work

### 5. **Pagination**
- 20 records per page
- Use pagination buttons to navigate
- Search resets to page 1

## 🆘 Troubleshooting

### "Error loading data"
- Check `static/master_data.json` exists
- Verify JSON format is valid
- Try importing a backup

### "Can't export"
- Check browser download settings
- Allow downloads from the site
- Try different browser

### "Changes not saving"
- Changes only save when you export
- Must download the JSON file
- Replace old file with new one

### "Import not working"
- Check JSON file format
- Must be valid JSON array
- Each record needs required fields

## 📊 Data Structure

Each record must have this structure:

```json
{
  "name": "John Doe",
  "father_name": "Father Name",
  "gender": "M",
  "age": 45,
  "aadhar": "123456789012",
  "address": "Full Address",
  "contact": "9876543210",
  "badge": "BADGE123"
}
```

Required fields:
- `name`
- `gender`
- `contact`

## 🌐 Integration with Nominal Roll Generator

Both apps use the same `master_data.json`:

```
Your GitHub Repository:
├── standalone_app.html (Nominal Roll Generator)
├── master_data_manager.html (This app)
└── static/
    └── master_data.json (Shared data)
```

**Update workflow:**
1. Edit data in Manager
2. Export JSON
3. Upload to GitHub
4. Both apps use updated data!

## 📈 Statistics

The app shows:
- **Total Records:** All records in database
- **Showing:** Currently filtered/displayed records

## 🎨 Mobile Responsive

- ✅ Works on phones (portrait/landscape)
- ✅ Works on tablets
- ✅ Works on desktop
- ✅ Touch-friendly buttons
- ✅ Scrollable tables

## ⚡ Performance

- Handles 1,000+ records smoothly
- Instant search (< 100ms)
- Pagination for better performance
- Lightweight (< 50KB HTML)

---

## 🎉 Quick Start Checklist

- [ ] Open `master_data_manager.html` in browser
- [ ] Verify data loads (1,239 records)
- [ ] Try searching for a name
- [ ] Add a test record
- [ ] Edit a record
- [ ] Delete the test record
- [ ] Export JSON
- [ ] Upload to GitHub Pages
- [ ] Share URL with team

**You're all set! 🚀**