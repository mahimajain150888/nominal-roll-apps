# Master Data Manager - Troubleshooting Guide

## Error: "Error loading data"

This error occurs when the Master Data Manager cannot load the `master_data.json` file. Here are the solutions:

### Solution 1: Use a Local Web Server (RECOMMENDED)

The Master Data Manager needs to be served through a web server due to browser security restrictions (CORS policy). You cannot simply open the HTML file directly in your browser.

#### Option A: Using Python (Easiest)

1. Open Terminal/Command Prompt
2. Navigate to your project folder:
   ```bash
   cd /Users/mahimajain/Downloads/Nominal_role_workspace
   ```
3. Start a simple web server:
   ```bash
   # Python 3
   python3 -m http.server 8000
   
   # OR Python 2
   python -m SimpleHTTPServer 8000
   ```
4. Open your browser and go to:
   ```
   http://localhost:8000/master_data_manager.html
   ```

#### Option B: Using Node.js

1. Install http-server globally:
   ```bash
   npm install -g http-server
   ```
2. Navigate to your project folder and run:
   ```bash
   http-server -p 8000
   ```
3. Open your browser and go to:
   ```
   http://localhost:8000/master_data_manager.html
   ```

#### Option C: Using VS Code Live Server Extension

1. Install "Live Server" extension in VS Code
2. Right-click on `master_data_manager.html`
3. Select "Open with Live Server"

### Solution 2: Use the Flask App

If you're already running the Flask app for the Nominal Roll Generator:

1. Start the Flask app:
   ```bash
   python app.py
   ```
2. Open your browser and go to:
   ```
   http://localhost:5000/master_data_manager.html
   ```

### Solution 3: Check File Paths

Make sure the file structure is correct:
```
Nominal_role_workspace/
├── master_data_manager.html
└── static/
    └── master_data.json
```

## Common Issues

### Issue: "Failed to fetch"
**Cause:** Opening HTML file directly in browser (file:// protocol)
**Solution:** Use one of the web server methods above

### Issue: "404 Not Found"
**Cause:** Incorrect file path or missing file
**Solution:** 
- Verify `static/master_data.json` exists
- Check file permissions
- Ensure you're in the correct directory

### Issue: "Invalid JSON"
**Cause:** Corrupted or malformed JSON file
**Solution:**
- Validate JSON at https://jsonlint.com/
- Re-export from the original Excel file

## Testing the Fix

1. Start a web server using any method above
2. Open the Master Data Manager in your browser
3. You should see:
   - Total Records count (should show the number of records)
   - The data table populated with records
   - Green success message: "Data loaded successfully!"

## Still Having Issues?

If you're still experiencing problems:

1. Open browser Developer Tools (F12)
2. Check the Console tab for error messages
3. Check the Network tab to see if the JSON file is being loaded
4. Verify the exact error message and path being used

## Alternative: Use Standalone App

If you need offline functionality without a web server, use `standalone_app.html` instead, which has the data embedded or uses a different loading mechanism.