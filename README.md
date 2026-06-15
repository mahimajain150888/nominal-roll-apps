# Nominal Roll Generator Application

A web-based application to generate nominal rolls from master data with automatic data population and comprehensive reporting.

## Features

### Nominal Roll Generation
- 🔍 **Smart Search**: Type-ahead search to find sewadars from master data
- 📝 **Auto-fill**: Automatically populates all sewadar details from master database
- 📋 **Metadata Entry**: Fill in nominal roll details (dates, location, vehicle info, etc.)
- 📥 **Download**: Generate and download Excel nominal rolls instantly
- 🎨 **Modern UI**: Clean, intuitive interface with real-time updates

### Reporting & Analytics (NEW!)
- 📊 **Automatic Logging**: Every NR generation is automatically saved for reporting
- 📈 **Statistics Dashboard**: View overall statistics (total sewadars, trips, days, places)
- 🔎 **Advanced Search**: Filter by sewadar name, place, date range
- 👤 **Sewadar History**: Click any sewadar to see their complete trip history
- 📑 **Export Reports**: Export filtered data to Excel for analysis
- 📅 **Duration Tracking**: Automatically calculates trip duration in days

## Prerequisites

- Python 3.9 or higher
- Required Python packages (already installed):
  - Flask
  - pandas
  - openpyxl

## File Structure

```
Nominal_role_workspace/
├── app.py                              # Flask application backend
├── templates/
│   └── index.html                      # Web interface
├── RSSB Workflow Final.xlsx            # Master data file
├── NR_May 2026 Construction Beas.xlsx  # Template file
└── README.md                           # This file
```

## How to Use

### 1. Start the Application

Open Terminal and run:

```bash
cd /Users/mahimajain/Downloads/Nominal_role_workspace
python3 app.py
```

The application will start on `http://127.0.0.1:5000`

### 2. Access the Web Interface

Open your web browser and go to:
```
http://127.0.0.1:5000
```

### 3. Fill in Nominal Roll Details

Enter the following information:
- Satsang Place
- Area
- Zone
- Jathedar Name
- Driver Name
- Vehicle Type
- Vehicle Number
- Place of Sewa
- From Date
- To Date

### 4. Select Sewadars

1. Type a name in the search box
2. Click on the person from the search results
3. The name will be added to the selected list
4. Repeat to add more sewadars
5. Click the × button on any name tag to remove them

### 5. Generate Nominal Roll

1. Click the "Generate Nominal Roll" button
2. The Excel file will be automatically downloaded
3. The file will be named with the current date

## Data Mapping

The application automatically maps data from the master file to the nominal roll:

| Nominal Roll Column | Master Data Column |
|---------------------|-------------------|
| Name | Name |
| Father's/Husband's Name | Father/ Husband/ Mother name |
| F (Gender) | Gender |
| Age | Age |
| Aadhar No. | Aadhar (masked) |
| R/o Village/Town | Address (current) |
| Mobile No. | Contact No |
| BADGE ID | Badge No (Centre) |

## Quick Start

### 1. Start the Application
```bash
cd /Users/mahimajain/Downloads/Nominal_role_workspace
python3 app.py
```

### 2. Access the Application
- **Main Generator**: http://127.0.0.1:5001
- **Reports Dashboard**: http://127.0.0.1:5001/reports

### 3. Generate a Nominal Roll
1. Fill in the metadata (dates, jathedar, vehicle info, etc.)
2. Search and select sewadars
3. Click "Generate Nominal Roll"
4. Excel file downloads automatically

### 4. View Reports
1. Click "📊 View Reports & Analytics" in the header
2. View overall statistics
3. Search/filter sewa history
4. Click sewadar names for detailed history
5. Export reports to Excel

## Features in Detail

### Nominal Roll Generation
- Real-time search as you type
- Shows name, father's name, gender, age, and contact
- Case-insensitive search
- Searches across all 1,239+ records instantly
- Maintains original template formatting
- Preserves all styling and borders
- Auto-numbers the serial numbers
- Includes all metadata in the header

### Reporting System
- **Automatic Logging**: Every NR is saved to `sewa_history_log.xlsx`
- **Statistics Dashboard**: Real-time overview of all sewa activities
- **Search & Filter**: Find specific sewadars, places, or date ranges
- **Sewadar Profiles**: Click any name to see complete trip history
- **Export Capability**: Download filtered reports as Excel files
- **Duration Calculation**: Automatically calculates trip duration

### Data Security
- Aadhar numbers are automatically masked (shows only last 4 digits)
- All data remains on your local machine
- No internet connection required

## Troubleshooting

### Application won't start
```bash
# Check if port 5000 is already in use
lsof -i :5000

# Kill the process if needed
kill -9 <PID>

# Restart the application
python3 app.py
```

### Search not working
- Ensure `RSSB Workflow Final.xlsx` is in the same directory
- Check that the file has a sheet named "Planner Persons"

### Download not working
- Check browser download settings
- Ensure pop-ups are not blocked
- Try a different browser

## Stopping the Application

Press `Ctrl+C` in the terminal where the application is running.

## Technical Details

- **Backend**: Flask (Python web framework)
- **Frontend**: HTML, CSS, JavaScript
- **Data Processing**: pandas
- **Excel Handling**: openpyxl
- **Port**: 5000 (default)

## Support

For issues or questions, check:
1. Terminal output for error messages
2. Browser console (F12) for JavaScript errors
3. Ensure all files are in the correct location

---

**Version**: 1.0  
**Last Updated**: May 2026

## File Structure

```
Nominal_role_workspace/
├── app.py                              # Flask application backend
├── templates/
│   ├── index.html                      # Main NR generator interface
│   └── reports.html                    # Reports dashboard (NEW!)
├── RSSB Workflow Final.xlsx            # Master data file
├── NR_May 2026 Construction Beas.xlsx  # Template file
├── sewa_history_log.xlsx               # Sewa history database (AUTO-GENERATED)
├── README.md                           # This file
└── REPORTING_FEATURE_GUIDE.md          # Detailed reporting guide (NEW!)
```

## Important Files

### sewa_history_log.xlsx
- **Purpose**: Stores all sewa trip records for reporting
- **Auto-generated**: Created automatically on first NR generation
- **Backup**: Regularly backup this file to prevent data loss
- **Location**: Same directory as app.py

### REPORTING_FEATURE_GUIDE.md
- **Purpose**: Comprehensive guide for using the reporting features
- **Contents**: Detailed instructions, use cases, troubleshooting
- **Recommended**: Read this for advanced reporting features

## Reporting Use Cases

### Track Individual Sewadar
1. Go to Reports page
2. Enter sewadar name in filter
3. Click "Apply Filters"
4. Click on name for complete history

### Generate Monthly Report
1. Select date range (e.g., month start to end)
2. Click "Apply Filters"
3. View statistics
4. Export to Excel

### Find Most Active Sewadars
1. View overall statistics on Reports page
2. Check top sewadars list
3. Click names for detailed history

### Audit Trail
1. Search by reference number or sewadar
2. View complete history with timestamps
3. Export for record keeping

## What's New in This Version

### Version 2.0 - Reporting System
- ✅ Automatic sewa history logging
- ✅ Comprehensive reports dashboard
- ✅ Statistics and analytics
- ✅ Search and filter capabilities
- ✅ Sewadar-specific trip history
- ✅ Excel export for reports
- ✅ Duration calculation
- ✅ Complete audit trail

---

**Version**: 2.0  
**Last Updated**: May 2026  
**Major Feature**: Comprehensive Sewa Reporting System