# LOTC Bag of Hope Pick List Form

A standalone HTML form application for "Least of These Carolinas" (LOTC) organization's "Bag of Hope" pick list system. This form collects information about children receiving bags and tracks what items need to be packed.

## 🚀 Live Demo

**Production URL:** [https://lotc-bag-of-hope-form.vercel.app](https://lotc-bag-of-hope-form.vercel.app)

## ✨ Features

### Auto-Population Intelligence
- **Birthday → Age Calculation:** Automatically calculates age from birthday
- **Readonly Age Field:** Age cannot be manually edited, only populated via birthday
- **Visual Indicators:** Helper text shows auto-populated fields

### Dynamic Detail Fields
- **Smart Input Expansion:** Checkbox items reveal detail fields when selected
- **Auto-Focus:** Detail fields automatically focus when revealed
- **Auto-Clear:** Detail fields clear when checkbox is unchecked
- **Applies to:** All clothing items (Tops, Bottoms, Underwear, Socks, Shoes, Jacket/Coat, Accessories) and Toy/Activity

### Enhanced UX/UI
- **Generous Spacing:** 50% more spacing between sections and form elements
- **Larger Touch Targets:** Bigger buttons (16px padding) and checkboxes (20px)
- **Interactive States:** Smooth hover and focus effects with red brand color glow
- **Visual Depth:** White section cards on light grey background with subtle shadows
- **Mobile Optimized:** Single-column layout, full-width buttons, adjusted padding for small screens

### Brand Compliance
- **Typography:** Poppins font family for all form elements, Georgia serif for headers
- **Colors:** Official LOTC brand palette (#c22035, #86b2d3, #a7a8a3, #060511)
- **Logo:** Authentic LOTC logo (80x80px PNG) embedded as base64 for zero external dependencies
- **Responsive:** Mobile-friendly design with CSS Grid and media queries

### Form Sections
1. **Quick View Information** - Child demographics and pickup location
   - First Name, Last Name (full name, not just initial)
   - Birthday with auto-calculated age
   - Gender, Ethnicity, Pickup Location
2. **Bag Details** - Embroidery company, order number, color preferences
3. **Non-Clothing Items** - Toy/activity selection with detail field
4. **Clothing** - Multi-select checkboxes with size/specification detail fields
5. **Notes** - Additional information and instructions

## 🛠️ Technology Stack

- Pure HTML, CSS, and JavaScript (no dependencies)
- Standalone file - no build process required
- Deployed on Vercel
- Version controlled with Git

## 📋 Form Validation

### Required Fields
- Child's First Name
- Child's Last Name (full name)
- Child's Age (0-18 years, readonly - must enter birthday)
- Gender
- Pickup Location

### Auto-Population Logic

```javascript
// Birthday → Age Calculation
// Calculates current age based on birthdate
// Age field is readonly and cannot be manually edited
// This ensures accurate age data tied to actual birthdate
```

### Detail Fields Data Collection
When checkboxes are selected, associated detail fields collect:
- **Toy/Activity:** Description/brand/specific item
- **Tops:** Size and preferences (e.g., "Size 8, short sleeve")
- **Bottoms:** Size and style details
- **Underwear:** Size information
- **Socks:** Size and quantity
- **Shoes:** Size and style
- **Jacket/Coat:** Size and seasonal needs
- **Accessories:** Specific items needed

## 🎨 Brand Guidelines

### Colors
```css
--lotc-red: #c22035      /* Primary brand red */
--lotc-blue: #86b2d3     /* Secondary blue */
--lotc-grey: #a7a8a3     /* Brand grey */
--lotc-black: #060511    /* Brand black */
```

### Typography
- **Headlines:** Georgia (awaiting Oakside font license)
- **Body/Forms:** Poppins Regular (400)
- **Labels/Buttons:** Poppins Bold (700)

## 🚀 Deployment

### Automatic Deployments
This project is connected to GitHub and Vercel. Every push to the `main` branch automatically triggers a new deployment.

### Manual Deployment
```bash
vercel --prod
```

### Local Testing
Simply open `bag-of-hope-form.html` or `index.html` in a web browser.

## 📁 Project Structure

```
LOTCPickFORM/
├── bag-of-hope-form.html          # Original form file
├── index.html                     # Vercel entry point (copy of form)
├── vercel.json                    # Vercel configuration
├── .gitignore                     # Git ignore rules
├── CLAUDE.md                      # Project guidance for AI assistance
├── README.md                      # This file
├── FORM_ANALYSIS.md               # Comprehensive specification
├── BRAND_COMPLIANCE_UPDATE.md     # Brand update tracking
├── AUTO_POPULATION_TEST_PLAN.md   # Testing checklist
├── logo.png                       # LOTC logo
├── Bag of Hope Details and Picklist - Apricot.pdf
└── LOTC Brand Guideline.pdf
```

## 🧪 Testing

### Testing the Form
1. Open the live URL or local file
2. Open browser console (F12) to see submission data
3. Test features:
   - **Birthday → Age:** Enter birthday → Watch age calculate automatically
   - **Dynamic Fields:** Check clothing item → Detail field appears and auto-focuses
   - **Auto-Clear:** Uncheck item → Detail field clears and hides
   - **Mobile View:** Resize browser → See responsive layout changes
   - **Interactive States:** Hover/focus on inputs → See visual feedback
   - **Form Validation:** Try submitting without required fields

### Key Test Scenarios
- Birthday calculation edge cases (leap years, future dates)
- Detail field data persistence in console log output
- Mobile responsiveness on various screen sizes
- Focus states and keyboard navigation
- Browser compatibility (Chrome, Safari, Firefox, Edge)

## 📝 Current Status

### ✅ Completed
- Brand-compliant design with authentic logo
- Birthday-based age calculation (readonly)
- Dynamic detail fields for all checkbox items
- Comprehensive UX improvements (spacing, interactions, mobile)
- Form validation with required fields
- Responsive mobile layout with media queries
- Vercel deployment with GitHub integration
- Base64-embedded logo (zero external dependencies)

### ⚠️ Pending
- Backend API integration for data persistence
- Server-side validation
- Database integration (Apricot system)

### 🔮 Future Enhancements
- API endpoint for form submission
- Error handling and user feedback for submission failures
- Print-friendly view for physical pick lists
- Save draft functionality
- Multi-bag bulk entry interface
- Admin dashboard for viewing submissions

## 🤝 Contributing

This is an internal LOTC project. For questions or changes, contact the development team.

## 📞 Contact

**Least of These Carolinas**
- Website: [lotcarolinas.com](https://lotcarolinas.com)
- Contact: Rebekah Estep (rebekahe@lotcarolinas.com, 702-215-4344)

## 📄 License

© 2026 Least of These Carolinas. All rights reserved.

---

**Built with ❤️ for children in need**
