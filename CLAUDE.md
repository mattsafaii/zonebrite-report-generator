# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Zonebrite Solutions Monthly Security System Maintenance Report Generator - a single-page web application that allows technicians to input maintenance data and generate professional PDF reports for clients.

## Architecture

This is a simple static web application with no build process:

- **index.html** - Main application file containing all HTML structure and JavaScript logic (~1745 lines)
- **styles.css** - All CSS styling including form styles and PDF-specific styles
- **logo.png** - Zonebrite Solutions logo (used in PDF generation)
- **zonebrite-logo.svg** - SVG version of the logo (alternative format)
- **wrangler.toml** - Cloudflare Pages deployment configuration
- No package.json or build tools - opens directly in browser

### Logo Handling

The logo is referenced via `<img id="logo-img" src="logo.png" style="display: none;">` in the HTML (around line 619). The logo is hidden in the web form but included in the generated PDF.

**Local Development Note**: Due to CORS restrictions, the logo image won't load when opening the HTML file directly with `file://` protocol. This is expected browser security behavior and doesn't affect functionality when the site is hosted on a web server (HTTP/HTTPS).

### Key JavaScript Components (in index.html)

- **Form Management**: Auto-save to localStorage every 30 seconds, session restore modal
- **Dynamic Sections**: `addCamera()` and `addIssue()` functions for dynamic form entries
- **PDF Generation**: Uses html2pdf.js library (loaded from CDN) with `createPDFTemplate()` function generating inline CSS + HTML
- **Date Handling**: `parseMonthString()` validates YYYY-MM format dates
- **Progress Tracking**: `updateProgress()` calculates form completion percentage

### Brand Colors (CSS Variables in styles.css)

- `--fence-green: #09332C` (primary)
- `--fiery-glow: #F0531C` (accent/CTA)
- `--norfolk-green: #2E4B3C` (secondary)
- `--pumpkin-vapor: #FFA74F` (warning/attention)
- `--venetian-lace: #F7EDDA` (light background)

## Development

Simply open `index.html` in a browser. No server or build process required.

### Testing Changes

1. Open file in browser
2. Fill out form sections
3. Test "Generate PDF" button - PDF downloads with filename format: `{ClientName}_MaintenanceReport_{MonthYear}.pdf`
4. Test auto-save by checking localStorage (key: `reportData`)

### PDF Generation Notes

The `createPDFTemplate()` function (starts around line 1059) generates a complete HTML document with inline styles for the PDF. It duplicates much of the PDF-specific CSS from styles.css to ensure proper rendering in the generated PDF. When modifying PDF appearance, update both:
1. The inline styles in `createPDFTemplate()`
2. The `.pdf-*` classes in styles.css (for consistency)

### Form Sections

The form has 10 sections:
1. Report Header (dates, client info)
2. System Health Overview (status, camera counts, storage)
3. Maintenance Activities Completed (checkboxes)
4. Individual Camera Status (dynamic)
5. Issues Identified & Resolved (dynamic)
6. Recommendations
7. Storage & Recording Details
8. System Updates
9. Summary
10. Sign-off

### Data Flow

Form data → `getFormData()` → localStorage (auto-save) → `createPDFTemplate()` → html2pdf.js → PDF download
