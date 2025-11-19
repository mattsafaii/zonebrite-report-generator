# Zonebrite Solutions - Monthly Security System Maintenance Report Generator

A professional, web-based HTML form that allows Zonebrite Solutions technicians to input monthly maintenance data and generate professional PDF reports for clients.

## Features

- **Single HTML File** - No installation required, works offline after initial load
- **Auto-Save** - Automatically saves form data every 30 seconds to prevent data loss
- **Session Recovery** - Restore previous incomplete reports
- **PDF Generation** - Creates professional, branded PDF reports with multi-page support
- **Responsive Design** - Works on desktop, tablet, and mobile devices
- **Progress Tracking** - Visual progress indicator shows form completion status
- **Dynamic Sections** - Add/remove cameras and issues as needed
- **Professional Branding** - Consistent Zonebrite Solutions branding throughout

## How to Use

### Getting Started

1. **Open the File**
   - Simply open `maintenance-report-generator.html` in any modern web browser (Chrome, Firefox, Safari, Edge)
   - No internet connection required after initial load (jsPDF library loads from CDN)

2. **Fill Out the Form**
   - Complete all required fields (marked with red asterisk *)
   - The form is organized into 10 logical sections:
     1. Report Header
     2. System Health Overview
     3. Maintenance Activities Completed
     4. Individual Camera Status
     5. Issues Identified & Resolved
     6. Recommendations
     7. Storage & Recording Details
     8. System Updates
     9. Summary
     10. Sign-off

3. **Add Dynamic Content**
   - Use "Add Camera" button to add camera entries (as many as needed)
   - Use "Add Issue" button to document problems found and resolved
   - Use "Remove" buttons to delete unwanted entries

4. **Monitor Progress**
   - Progress bar at top shows completion percentage
   - Auto-save indicator confirms data is being saved
   - Last saved timestamp shows when data was last stored

5. **Generate PDF**
   - Click "Generate PDF" button when form is complete
   - PDF will download automatically with filename: `[ClientName]_MaintenanceReport_[MonthYear].pdf`
   - Example: `AcmeRetail_MaintenanceReport_Nov2024.pdf`

### Key Features

#### Auto-Save
- Form data automatically saves every 30 seconds
- Data also saves when you leave any field (blur event)
- All data stored locally in browser's localStorage
- No data sent to any server

#### Session Recovery
- If you close the browser before completing the form, your data is preserved
- Next time you open the file, you'll see a prompt to restore your previous session
- Choose "Restore" to continue where you left off, or "Start Fresh" to begin a new report

#### Form Validation
- Required fields are validated before PDF generation
- Error messages appear for missing or invalid data
- First error field is automatically scrolled into view

#### Smart Calculations
- "Cameras Requiring Attention" auto-calculates (Total - Operational)
- "Next Scheduled Maintenance" defaults to 30 days from today
- Report date defaults to today

## PDF Report Features

### Professional Layout
- Zonebrite Solutions branding on every page
- Company tagline: "Protecting What Matters Most"
- Client information in header
- Page numbers and contact info in footer

### Color-Coded Status
- **Green** - Excellent/Operational
- **Blue** - Good/Stable
- **Orange** - Needs Attention/Intermittent
- **Red** - Critical/Offline

### Comprehensive Sections
- All 10 form sections included in PDF
- Tables for structured data
- Proper text wrapping for long content
- Multi-page support with consistent formatting

## Technical Specifications

### Technology Stack
- **HTML5** - Form structure
- **CSS3** - Professional styling and responsive design
- **JavaScript (ES6)** - Form logic and PDF generation
- **jsPDF Library** - PDF creation (loaded from CDN)
- **Google Fonts** - Barlow font family

### Browser Compatibility
- Chrome/Edge (recommended)
- Firefox
- Safari
- Modern mobile browsers

### Data Storage
- All data stored in browser's localStorage
- No external server required
- No data transmission to third parties
- Data persists until manually cleared

### File Size
- HTML file: ~68KB
- Generated PDF: Typically < 500KB
- No external dependencies except jsPDF CDN

## Buttons & Actions

### Generate PDF
- Validates all required fields
- Creates professional multi-page PDF
- Auto-downloads with smart filename
- Shows loading spinner during generation

### Save Progress
- Manually triggers save to localStorage
- Shows confirmation indicator
- Updates "Last Saved" timestamp

### Clear Form
- Requires double confirmation
- Removes all form data
- Clears localStorage
- Resets to initial state

## Form Sections Explained

### 1. Report Header
Basic information about the report, client, and service dates.

### 2. System Health Overview
High-level metrics about the security system:
- Overall system status
- Camera counts and operational status
- Uptime percentage
- Storage usage (interactive slider)
- Network connectivity

### 3. Maintenance Activities Completed
Checklist of 15 standard maintenance tasks with checkboxes.

### 4. Individual Camera Status
Dynamic section for documenting each camera:
- Location/Name
- Operational status
- Issues found
- Actions taken
- Notes

### 5. Issues Identified & Resolved
Dynamic section for documenting problems:
- Issue description
- Severity level (Low/Medium/High/Critical)
- Resolution details
- Parts replaced

### 6. Recommendations
Forward-looking suggestions:
- Maintenance recommendations
- Upgrade opportunities
- Optimization suggestions
- Cost estimates
- Priority levels

### 7. Storage & Recording Details
Technical specifications:
- Storage capacity and usage
- Retention period
- Video quality settings
- Backup status

### 8. System Updates
Version tracking and updates:
- Firmware version
- Software version
- Updates applied
- Updates recommended

### 9. Summary
Overall assessment:
- General assessment narrative
- Critical items requiring attention
- Next month's focus areas

### 10. Sign-off
Final acknowledgments:
- Technician signature
- Client acknowledgment (optional)
- Client feedback (optional)

## Privacy & Security

- **No Data Transmission** - All data stays on your device
- **Local Storage Only** - Uses browser's localStorage API
- **No Tracking** - No analytics or tracking scripts
- **Offline Capable** - Works without internet (after initial load)
- **Clear Data Option** - Easy to wipe all stored data

## Tips for Best Results

1. **Use Descriptive Camera Names** - "Front Entrance" is better than "Camera 1"
2. **Be Specific in Issues** - Detail helps clients understand the work done
3. **Include Recommendations** - Show proactive service and build trust
4. **Complete Summary Section** - Provides valuable overview for clients
5. **Save Regularly** - Although auto-save is active, manual saves provide peace of mind
6. **Review Before Generating** - Check all data for accuracy before creating PDF

## Troubleshooting

### PDF Not Generating
- Check that all required fields (*) are filled
- Look for error messages on required fields
- Ensure browser allows pop-ups/downloads

### Data Not Saving
- Check browser localStorage is enabled
- Ensure you're not in private/incognito mode
- Try manually clicking "Save Progress"

### Session Not Restoring
- Verify localStorage wasn't cleared
- Check you're using the same browser
- Try checking browser console for errors

### Styling Issues
- Ensure browser is up to date
- Clear browser cache
- Try a different modern browser

## Contact & Support

**Zonebrite Solutions**
- Website: www.zonebrite.com
- Email: info@zonebrite.com

For technical issues with this tool, contact your system administrator.

## Version

**Version:** 1.0
**Last Updated:** November 19, 2024
**Created by:** Claude Code for Zonebrite Solutions

## License

Proprietary - For use by Zonebrite Solutions staff only.