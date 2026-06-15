# Sewa Reporting Feature Guide

## Overview

The Nominal Roll Generator now includes a comprehensive reporting system that automatically tracks all sewa trips and provides detailed analytics about sewadar participation.

## Features

### 1. Automatic Data Logging
Every time you generate a Nominal Roll, the system automatically saves:
- Sewadar names and details
- Place of sewa
- Duration (from date to date)
- Jathedar and driver information
- Vehicle details
- Reference number
- Timestamp of generation

### 2. Reports Dashboard
Access the reports dashboard at: `http://127.0.0.1:5001/reports`

### 3. Overall Statistics
View at-a-glance statistics:
- **Total Sewadars**: Unique sewadars who have participated
- **Total Trips**: Total number of sewa trips recorded
- **Total Days**: Cumulative days of sewa
- **Unique Places**: Number of different sewa locations

### 4. Search & Filter
Filter sewa history by:
- **Sewadar Name**: Find specific sewadar's trips
- **Place of Sewa**: See all trips to a specific location
- **Date Range**: Filter by from/to dates
- **Combined Filters**: Use multiple filters together

### 5. Sewadar-Specific Reports
Click on any sewadar name to see:
- Total number of trips
- Total days of sewa
- All places visited
- Complete trip history with details

### 6. Export Functionality
Export filtered reports to Excel for:
- Further analysis
- Sharing with team
- Record keeping
- Audit purposes

## How to Use

### Accessing Reports

1. **From Main Page**: Click "📊 View Reports & Analytics" button in the header
2. **Direct URL**: Navigate to `http://127.0.0.1:5001/reports`

### Viewing Overall Statistics

The dashboard automatically displays:
- Total sewadars who have participated
- Total trips recorded
- Total days of sewa
- Number of unique places visited

### Searching for Specific Data

1. **By Sewadar Name**:
   - Enter name in "Sewadar Name" field
   - Click "Apply Filters"
   - View all trips for that sewadar

2. **By Place**:
   - Enter place name in "Place of Sewa" field
   - Click "Apply Filters"
   - See all trips to that location

3. **By Date Range**:
   - Select "From Date" and "To Date"
   - Click "Apply Filters"
   - View trips within that period

4. **Combined Search**:
   - Fill multiple filter fields
   - Click "Apply Filters"
   - Get precise results

### Viewing Sewadar Details

1. Click on any sewadar name in the results table
2. A popup will show:
   - Summary statistics (trips, days, places)
   - Complete trip history
   - Details of each trip

### Exporting Reports

1. Apply desired filters (or leave empty for all data)
2. Click "Export to Excel" button
3. Excel file will download automatically
4. File includes all filtered records

### Clearing Filters

Click "Clear Filters" button to reset all filters and view complete history.

## Data Storage

### Location
All sewa history is stored in: `sewa_history_log.xlsx`

### Structure
The log file contains these columns:
- **Timestamp**: When the NR was generated
- **Reference_No**: NR reference number
- **Sewadar_Name**: Name of sewadar
- **Father_Name**: Father/Husband/Mother name
- **Gender**: M/F
- **Age**: Age of sewadar
- **Contact**: Contact number
- **Badge_No**: Badge number
- **Place_of_Sewa**: Destination
- **From_Date**: Start date
- **To_Date**: End date
- **Duration_Days**: Number of days (calculated)
- **Jathedar**: Jathedar name
- **Driver**: Driver name
- **Vehicle_Type**: Type of vehicle
- **Vehicle_No**: Vehicle number

### Backup
**Important**: Regularly backup `sewa_history_log.xlsx` to prevent data loss.

## Use Cases

### 1. Track Individual Sewadar Participation
**Scenario**: Want to know how many times a sewadar has participated

**Steps**:
1. Go to Reports page
2. Enter sewadar name in filter
3. Click "Apply Filters"
4. Click on sewadar name for detailed summary

### 2. Analyze Place-wise Participation
**Scenario**: See how many sewadars went to a specific place

**Steps**:
1. Enter place name in "Place of Sewa" filter
2. Click "Apply Filters"
3. View all trips to that location
4. Export to Excel for detailed analysis

### 3. Monthly/Yearly Reports
**Scenario**: Generate report for specific time period

**Steps**:
1. Select date range (e.g., Jan 1 to Dec 31)
2. Click "Apply Filters"
3. View statistics and records
4. Export to Excel

### 4. Identify Most Active Sewadars
**Scenario**: Find sewadars with most participation

**Steps**:
1. View overall statistics
2. Check "Top Sewadars" section (shows top 10)
3. Click on names for detailed history

### 5. Audit Trail
**Scenario**: Verify when and where sewadars were sent

**Steps**:
1. Search by sewadar name or reference number
2. View complete history with timestamps
3. Export for record keeping

## Tips & Best Practices

### 1. Regular Monitoring
- Check reports weekly to track participation
- Identify sewadars who haven't participated recently
- Plan future trips based on historical data

### 2. Data Accuracy
- Ensure all fields are filled correctly when generating NRs
- Double-check dates and places
- Verify sewadar names match master data

### 3. Backup Strategy
- Backup `sewa_history_log.xlsx` weekly
- Keep backups in multiple locations
- Consider cloud storage for safety

### 4. Report Generation
- Export reports before major events
- Share statistics with team regularly
- Use data for planning and coordination

### 5. Performance
- For large datasets, use filters to narrow results
- Export filtered data for offline analysis
- Clear browser cache if page loads slowly

## Troubleshooting

### No Data Showing
**Problem**: Reports page shows 0 records

**Solution**:
1. Generate at least one Nominal Roll first
2. Check if `sewa_history_log.xlsx` exists
3. Refresh the reports page

### Filter Not Working
**Problem**: Filters don't show expected results

**Solution**:
1. Check spelling of names/places
2. Ensure date format is correct
3. Clear filters and try again
4. Refresh the page

### Export Not Working
**Problem**: Excel file not downloading

**Solution**:
1. Check browser download settings
2. Disable popup blockers
3. Try different browser
4. Check disk space

### Sewadar Details Not Loading
**Problem**: Clicking sewadar name doesn't show popup

**Solution**:
1. Refresh the page
2. Check browser console for errors
3. Ensure JavaScript is enabled
4. Try different browser

## API Endpoints (For Developers)

### Get Sewa History
```
GET /api/sewa-history
Parameters: sewadar_name, place, from_date, to_date
```

### Get Sewadar Summary
```
GET /api/sewadar-summary/<sewadar_name>
```

### Get Statistics
```
GET /api/statistics
```

### Export Report
```
POST /api/export-report
Body: {sewadar_name, place, from_date, to_date}
```

## Future Enhancements

Potential features for future versions:
- Dashboard charts and graphs
- Email notifications for reports
- Automated monthly summaries
- Mobile app integration
- Advanced analytics (trends, predictions)
- Multi-user access with roles

## Support

For issues or questions:
1. Check this guide first
2. Review error messages in browser console
3. Verify data file integrity
4. Contact system administrator

---

**Version**: 1.0  
**Last Updated**: May 2026  
**Feature Added**: Comprehensive Sewa Reporting System