# Render Deployment Guide for This Project

This document explains how to deploy this Flask-based Nominal Roll application to Render later.

## Why Render?

Use Render because this project is a **Python Flask app** and not just a static website.

This project needs a Python hosting platform because it:
- runs `app.py`
- serves Flask routes
- uses API endpoints like:
  - `/generate`
  - `/api/statistics`
  - `/api/generated-nrs`
- reads Excel files
- writes history to Excel
- generates downloadable Excel files

## Important Limitation

This project currently stores history in:

- `sewa_history_log.xlsx`

On Render, file changes may **not remain permanent** after restart or redeploy.

That means:
- the app can run
- generating reports can work
- but saved history may be lost later

If permanent data saving is needed in future, move history storage to a database.

---

## Files Required in GitHub Repository

Before deploying, make sure your GitHub repository contains:

- `app.py`
- `templates/index.html`
- `templates/reports.html`
- `static/`
- `RSSB Workflow Final.xlsx`
- `NR_May 2026 Construction Beas.xlsx`
- `sewa_history_log.xlsx`

If any required file is missing, deployment may fail or the app may not work correctly.

---

## Step 1: Push Project to GitHub

Create a GitHub repository and upload the full project.

Make sure these folders remain unchanged:
- `templates/`
- `static/`

---

## Step 2: Create `requirements.txt`

Create a file named:

`requirements.txt`

Put this inside it:

```txt
Flask
pandas
openpyxl
gunicorn
```

This tells Render which Python packages to install.

---

## Step 3: Update `app.py` for Render Port

Render provides its own port through an environment variable called `PORT`.

Before deploying, update the bottom of `app.py` to:

```python
if __name__ == '__main__':
    port = int(os.environ.get('PORT', 5001))
    app.run(debug=True, host='0.0.0.0', port=port)
```

This is important. Without this, the app may not start properly on Render.

---

## Step 4: Create Render Account

1. Go to: https://render.com
2. Sign up
3. Choose GitHub login for easiest setup

---

## Step 5: Create a New Web Service

After login:

1. Click **New +**
2. Click **Web Service**
3. Connect your GitHub account if asked
4. Select your repository for this project

---

## Step 6: Fill Render Service Settings

Use these values:

- **Name:** any name you want  
  Example: `nominal-roll-app`

- **Environment:** `Python 3`

- **Build Command:**
```bash
pip install -r requirements.txt
```

- **Start Command:**
```bash
gunicorn app:app
```

---

## Step 7: Deploy

Click:

**Create Web Service**

Render will now:
- pull your GitHub code
- install packages
- start the Flask app

Wait until deployment finishes.

---

## Step 8: Open the Application

After successful deployment, Render gives a public URL like:

```txt
https://your-app-name.onrender.com
```

Open that URL in the browser.

---

## If Deployment Fails

Check these first:

### 1. Missing `requirements.txt`
Render cannot install Python packages without it.

### 2. Wrong start command
Use exactly:

```bash
gunicorn app:app
```

### 3. Missing Excel files
This app depends on:
- `RSSB Workflow Final.xlsx`
- `NR_May 2026 Construction Beas.xlsx`
- `sewa_history_log.xlsx`

### 4. Port not configured in `app.py`
Make sure the `PORT` environment variable version is used.

---

## Recommended Future Improvement

For better production use, later you should move history storage from Excel to a database.

Reason:
- Excel file updates on hosting platforms are not reliable for long-term storage
- databases are better for:
  - saved history
  - edits
  - deletes
  - multiple users

---

## Quick Summary

When you are ready later, do this:

1. Push full project to GitHub
2. Add `requirements.txt`
3. Update `app.py` to use `PORT`
4. Create Render account
5. New Web Service
6. Connect GitHub repo
7. Use:
   - Build: `pip install -r requirements.txt`
   - Start: `gunicorn app:app`
8. Deploy
9. Open the Render URL

---

## Optional Next Setup Tasks Later

When you actually deploy, you may also want to add:

- `requirements.txt`
- Render-ready `app.py` port config
- better persistent storage for history
