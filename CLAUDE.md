# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This repository contains a standalone HTML form application for "Least of These Carolinas" (LOTC) organization's "Bag of Hope" pick list system. The form is used to collect information about children receiving bags and track what items need to be packed.

## File Structure

- `bag-of-hope-form.html` - Main form file (standalone HTML with embedded CSS and JavaScript)
- `Bag of Hope Details and Picklist - Apricot.pdf` - Source reference document for form requirements
- `LOTC Brand Guideline.pdf` - Brand colors, logo, and design guidelines

## Design System

### Brand Colors
- **Primary Red**: `#c22035` - Used for headings, buttons, and accents
- **Secondary Blue**: `#86b2d3` - Used for input borders and subtle backgrounds
- **Logo**: Circular red background (`#c22035`) with white symbol

### Typography
- **Headers**: Georgia serif font family
- **Body/Form**: Arial sans-serif font family

### Key Design Principles
- Clean, professional form layout with subtle gradient background
- Clear visual hierarchy with color-coded sections
- Accessible form inputs with focus states and proper labeling
- Mobile-responsive grid layout using CSS Grid

## Form Architecture

The form is organized into five main sections:
1. **Quick View Information** - Child demographics and pickup location (required fields)
2. **Bag Details** - Embroidery company, order number, color preferences
3. **Non-Clothing Items** - Toy/activity selection ($25 value)
4. **Clothing** - Multi-select checkboxes for clothing items needed
5. **Notes** - Free-form text area for additional information

### Form Validation
- Required fields: firstName, lastInitial, age, gender, pickupLocation
- Age validation: 0-18 years
- Last initial: single character max

### Form Submission
Current implementation:
- Prevents default form submission
- Collects all form data including checked items
- Logs to console (no backend integration yet)
- Shows temporary success message for 3 seconds
- Form data is NOT persisted or sent to a server

## Development Notes

Since this is a standalone HTML file with no build process:
- Open `bag-of-hope-form.html` directly in a browser to view/test
- All styles are embedded in `<style>` tag
- All JavaScript is embedded in `<script>` tag
- No external dependencies or package managers

## Future Integration Considerations

The form currently logs data to console. For production use, the submit handler (line 438-465 in bag-of-hope-form.html) will need to be updated to:
- Send data to a backend API endpoint
- Handle submission errors
- Store data in a database (likely Apricot system based on PDF reference)
- Potentially integrate with existing LOTC systems
