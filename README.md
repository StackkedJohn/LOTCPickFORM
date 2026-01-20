# LOTC Bag of Hope Pick List Form

A standalone HTML form application for "Least of These Carolinas" (LOTC) organization's "Bag of Hope" pick list system. This form collects information about children receiving bags and tracks what items need to be packed.

## 🚀 Live Demo

**Production URL:** [https://lotc-bag-of-hope-form.vercel.app](https://lotc-bag-of-hope-form.vercel.app)

## ✨ Features

### Auto-Population Intelligence
- **Birthday → Age Calculation:** Automatically calculates age from birthday
- **Age → Age Group:** Auto-fills age group based on entered age
- **Color Matching:** Suggests toiletry bag color based on embroidery color (child's favorite)
- **Visual Indicators:** "auto" badges and subtle backgrounds show auto-populated fields
- **Manual Override:** All auto-filled fields can be manually changed

### Brand Compliance
- **Typography:** Poppins font family (Oakside pending for headlines)
- **Colors:** Official LOTC brand palette (#c22035, #86b2d3, #a7a8a3, #060511)
- **Logo:** Authentic LOTC logo with children silhouettes
- **Responsive:** Mobile-friendly design with CSS Grid

### Form Sections
1. **Quick View Information** - Child demographics and pickup location
2. **Bag Details** - Embroidery company, order number, color preferences
3. **Non-Clothing Items** - Toy/activity selection ($25 value)
4. **Clothing** - Multi-select checkboxes for needed items
5. **Notes** - Additional information and instructions

## 🛠️ Technology Stack

- Pure HTML, CSS, and JavaScript (no dependencies)
- Standalone file - no build process required
- Deployed on Vercel
- Version controlled with Git

## 📋 Form Validation

### Required Fields
- Child's First Name
- Child's Last Initial (single character)
- Child's Age (0-18 years)
- Gender
- Pickup Location

### Auto-Population Logic

```javascript
// Age Groups
0-2 years   → "0-2 Years"
3-5 years   → "3-5 Years"
6-11 years  → "6-11 Years"
12+ years   → "12 Years and Older"
```

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
3. Test auto-population features:
   - Enter birthday → Watch age calculate → Watch age group fill
   - Enter age directly → Watch age group auto-fill
   - Select embroidery color → Watch toiletry bag color suggest

### Test Scenarios
See `AUTO_POPULATION_TEST_PLAN.md` for comprehensive test cases.

## 📝 Current Status

### ✅ Completed
- Brand-compliant design (87.5% - Oakside font pending)
- Auto-population features (100%)
- Form validation
- Visual feedback system
- Responsive mobile layout
- Vercel deployment
- GitHub integration

### ⚠️ Pending
- Oakside font implementation (requires license purchase)
- Record ID field addition
- Neon CRM API integration

### 🔮 Future Enhancements
- Backend API integration for data persistence
- Print-friendly view
- Save draft functionality
- Multi-bag bulk entry

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
