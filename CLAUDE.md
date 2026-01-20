# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a standalone HTML form application for "Least of These Carolinas" (LOTC) organization's "Bag of Hope" pick list system. The form is used to collect information about children receiving bags and track what items need to be packed.

**Deployment**: Live on Vercel with automatic deployment from GitHub main branch.

## File Structure

- `index.html` - Main deployment file (standalone HTML with embedded CSS and JavaScript)
- `bag-of-hope-form.html` - Mirror of index.html for consistency
- `logo.png` - Official LOTC logo (34KB PNG, embedded as base64 in HTML)
- `vercel.json` - Vercel deployment configuration
- `Bag of Hope Details and Picklist - Apricot.pdf` - Source reference document for form requirements
- `LOTC Brand Guideline.pdf` - Brand colors, logo, and design guidelines

**Note**: Both HTML files must be kept in sync. All changes should be applied to both files.

## Design System

### Brand Colors
- **Primary Red**: `#c22035` - Used for headings, buttons, logo background, and accents
- **Secondary Blue**: `#86b2d3` - Used for input borders and subtle backgrounds
- **Grey Backgrounds**: `#f8f9fa` (form card), `rgba(134, 178, 211, 0.08)` (checkbox groups)
- **Text Colors**: `#060511` (primary), `#6c757d` (helper text)

### Logo Implementation
- **Format**: PNG file (logo.png) embedded as base64 data URI
- **Dimensions**: 80x80 pixels
- **Location**: Left side of header
- **Technical**: Base64-encoded directly in HTML for zero external dependencies
- **Design**: Circular with red background, white children silhouettes, and curved text

### Typography
- **Primary Font**: Poppins (Google Fonts) - Used for all form elements, labels, inputs, buttons
- **Header Font**: Georgia serif - Used for page title and section titles
- **Font Weights**: 400 (regular), 500 (medium), 700 (bold)

### Key Design Principles
- Comprehensive spacing for readability (sections: 48px margins, inputs: 28px gaps)
- Clear visual hierarchy with generous white space and depth (subtle shadows)
- Accessible form inputs with focus states (red border glow) and proper labeling
- Mobile-responsive grid layout using CSS Grid with single-column mobile view
- Interactive hover and focus states for better user feedback
- Larger touch targets (20px checkboxes, 16px button padding)

## Form Architecture

The form is organized into five main sections:
1. **Quick View Information** - Child demographics and pickup location (required fields)
   - First Name, Last Name (changed from Last Initial)
   - Birthday (auto-calculates age)
   - Age (readonly, auto-populated from birthday)
   - Gender, Ethnicity, Pickup Location
2. **Bag Details** - Embroidery company, order number, color preferences
3. **Non-Clothing Items** - Toy/activity selection
   - Dynamic detail field appears when checkbox is selected
   - Auto-focuses on detail input when opened
   - Auto-clears when unchecked
4. **Clothing** - Multi-select checkboxes for clothing items needed
   - Each checkbox has a dynamic detail field for size/specifications
   - Items: Tops, Bottoms, Underwear, Socks, Shoes, Jacket/Coat, Accessories
5. **Notes** - Free-form text area for additional information

### Form Validation
- Required fields: firstName, lastName, age, gender, pickupLocation
- Age validation: 0-18 years, readonly (only populated via birthday)
- Birthday auto-calculates age when entered
- Last Name: full name field (changed from single initial)

### Dynamic Detail Fields
All checkbox items (Toy/Activity, Tops, Bottoms, etc.) have associated detail fields:
- Hidden by default
- Show when checkbox is checked (`.checkbox-detail.show`)
- Auto-focus on input when revealed
- Auto-clear value when checkbox is unchecked
- Implemented with JavaScript event listeners on `data-detail` attributes

### Form Submission
Current implementation:
- Prevents default form submission
- Collects all form data including checked items and detail fields
- Logs to console (no backend integration yet)
- Shows temporary success message for 3 seconds
- Form data is NOT persisted or sent to a server

## UX Improvements Applied

### Spacing Enhancements
- Section spacing increased 50% (32px → 48px)
- Form grid gaps increased 40% (20px → 28px)
- Input padding increased 40% (10px 12px → 14px 16px)
- Checkbox item spacing doubled (8px → 16px)
- Button padding increased 33% (12px 24px → 16px 32px)

### Visual Hierarchy
- Section titles: 22px (was 20px)
- Input/select font: 15px (was 14px)
- Helper text: 13px (was 11px)
- Form card background: Light grey (#f8f9fa) for contrast
- Sections have white backgrounds with subtle shadows for depth

### Interactive States
- Focus states: Red border (#c22035) with subtle shadow glow
- Hover states: Checkboxes and buttons have subtle lift effects
- Transitions: 0.2s ease on all interactive elements
- Button hover: translateY(-2px) with enhanced shadow

### Mobile Responsiveness
- Single column layout on screens < 768px
- Adjusted padding for smaller screens (40px → 24px)
- Full-width buttons on mobile
- Flexible button group layout (column direction)

## Development Notes

Since this is a standalone HTML file with no build process:
- Open `index.html` directly in a browser to view/test
- All styles are embedded in `<style>` tag (lines 12-380)
- All JavaScript is embedded in `<script>` tag (lines 770+)
- Logo embedded as base64 data URI (no external file loading)
- Google Fonts loaded via CDN (Poppins font family)

### Local Development
```bash
open index.html  # macOS
# or just double-click the file in file explorer
```

### Vercel Deployment
- Automatic deployment on push to GitHub main branch
- Configuration in `vercel.json`
- Live URL: https://lotc-pick-form.vercel.app (or similar)

## Future Integration Considerations

The form currently logs data to console. For production use, the submit handler will need to be updated to:
- Send data to a backend API endpoint
- Handle submission errors with user feedback
- Store data in a database (likely Apricot system based on PDF reference)
- Include detail field data from dynamic checkbox fields
- Potentially integrate with existing LOTC systems
- Add server-side validation for age calculation and required fields
