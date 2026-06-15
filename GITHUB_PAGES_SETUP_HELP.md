# GitHub Pages Setup - Troubleshooting

## Issue: "Save" Button is Disabled

This is a common issue. Here are the solutions:

### Solution 1: Make Sure You Have Files in Your Repository

The Save button is disabled if your repository is empty or doesn't have the right branch.

**Steps:**
1. Go to your repository main page
2. Check if you see files listed
3. If empty, upload files first (see below)
4. Then go back to Settings → Pages

### Solution 2: Upload Files First

**Before enabling GitHub Pages, upload your files:**

1. On your repository page, click "Add file" → "Upload files"
2. Drag and drop these files:
   ```
   standalone_app.html
   master_data_manager.html
   ```
3. Create a folder structure by typing in the file path:
   - Type: `static/master_data.json` and upload the file
   - Repeat for other static files:
     - `static/icon-192.png`
     - `static/icon-512.png`
     - `static/manifest.json`
     - `static/service-worker.js`
4. Click "Commit changes"
5. Wait 10 seconds for GitHub to process

### Solution 3: Enable GitHub Pages After Upload

**Now enable GitHub Pages:**

1. Go to **Settings** (top menu)
2. Scroll down to **Pages** (left sidebar)
3. Under "Source":
   - Select **"Deploy from a branch"**
4. Under "Branch":
   - Select **"main"** (or "master" if that's your branch name)
   - Select **"/ (root)"**
5. Click **"Save"** (should now be enabled!)

### Solution 4: Alternative - Use GitHub Actions

If the above doesn't work, try GitHub Actions deployment:

1. In Settings → Pages
2. Under "Source", select **"GitHub Actions"**
3. Click "Configure" on "Static HTML"
4. Click "Commit changes"
5. Your site will deploy automatically

### Solution 5: Check Repository Settings

Make sure:
- ✅ Repository is **Public** (or you have GitHub Pro for private repos)
- ✅ You have **admin access** to the repository
- ✅ Repository has at least one commit with files

### Solution 6: Create index.html

GitHub Pages works better with an index.html file:

1. Create a new file called `index.html`
2. Add this content:
```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Nominal Roll Generator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
            text-align: center;
        }
        .btn {
            display: inline-block;
            padding: 15px 30px;
            margin: 10px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-decoration: none;
            border-radius: 8px;
            font-size: 18px;
        }
        .btn:hover {
            opacity: 0.9;
        }
    </style>
</head>
<body>
    <h1>📋 Nominal Roll Generator</h1>
    <p>Choose an application:</p>
    
    <a href="standalone_app.html" class="btn">
        🚀 Nominal Roll Generator
    </a>
    
    <a href="master_data_manager.html" class="btn">
        📊 Master Data Manager
    </a>
</body>
</html>
```
3. Commit the file
4. Now try enabling GitHub Pages again

## After Enabling GitHub Pages

Once you click Save:
1. Wait 1-2 minutes for deployment
2. A green box will appear with your URL
3. Click "Visit site" or copy the URL
4. Your apps will be live!

## Your URLs Will Be:
- **Home:** `https://YOUR_USERNAME.github.io/REPO_NAME/`
- **Nominal Roll:** `https://YOUR_USERNAME.github.io/REPO_NAME/standalone_app.html`
- **Data Manager:** `https://YOUR_USERNAME.github.io/REPO_NAME/master_data_manager.html`

## Still Having Issues?

### Check These:
1. **Repository visibility:** Settings → General → Danger Zone → Change visibility → Public
2. **Branch name:** Make sure you're selecting the correct branch (main or master)
3. **File location:** Files should be in the root directory, not in a subfolder
4. **Wait time:** Sometimes it takes 2-3 minutes for the first deployment

### Common Errors:
- **404 Error:** Files not in the right location
- **Save disabled:** Repository is empty or no branch selected
- **No branch option:** No commits in repository yet

## Quick Start (Recommended Order):

1. ✅ Create repository
2. ✅ Upload ALL files (including index.html)
3. ✅ Wait 10 seconds
4. ✅ Go to Settings → Pages
5. ✅ Select "Deploy from a branch"
6. ✅ Select "main" branch and "/ (root)"
7. ✅ Click Save
8. ✅ Wait 1-2 minutes
9. ✅ Visit your site!

## Need More Help?

If you're still stuck, share:
- Screenshot of the Settings → Pages screen
- Your repository URL
- Any error messages you see

I can provide more specific guidance!