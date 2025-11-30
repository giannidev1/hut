# AriRent Professional Flyer

A stunning, professionally designed flyer for AriRent - connecting international students with premium San Diego beach housing.

## Features

- **Professional Designer Aesthetic**: Clean, modern layout with premium typography (Playfair Display + Inter)
- **Stock Photography**: High-quality Unsplash images throughout
- **Interactive Map**: Leaflet.js map showing Mission Beach, Pacific Beach, USD, and SDSU with custom pins
- **Fully Responsive**: Looks beautiful on desktop, tablet, and mobile
- **Print Ready**: Optimized for PDF conversion and printing

## What's Included

### Sections

1. **Hero Section**: Stunning header with San Diego apartment stock photo overlay
2. **Stats Bar**: Key metrics (properties managed, occupancy rate, universities served)
3. **About Section**: Professional photo placeholder + compelling copy
4. **Interactive Map**: Shows universities (🎓 red pins) and rental properties (🏠 teal pins)
5. **Services**: Two cards with stock photos explaining value for property owners and students
6. **Features**: Four-point value proposition with icon badges
7. **Gallery**: Three beautiful San Diego beach photos
8. **Contact Section**: All contact information beautifully displayed with CTA button

### Design Details

- **Color Palette**: Sophisticated teal/ocean blues (#0e7490, #2a9d8f)
- **Typography**:
  - Headlines: Playfair Display (serif, elegant)
  - Body: Inter (sans-serif, modern, clean)
- **Stock Photos**: All from Unsplash (high-quality, free to use)
- **Map**: Interactive Leaflet.js map with custom markers

## Customization Guide

### 1. Add Ari's Photo

Find this section in the HTML (around line 559-563):

```html
<div class="profile-image">
    <div class="profile-placeholder">
        <p><strong>Replace with Ari's professional photo</strong>...
```

Replace it with:

```html
<div class="profile-image">
    <img src="path/to/ari-photo.jpg" alt="Ari">
</div>
```

**Photo Tips**:
- Use a professional headshot or lifestyle photo
- Recommended dimensions: At least 800x1000px
- Format: JPG or PNG
- Ensure good lighting and professional appearance

### 2. Update Contact Information

Search and replace these placeholders in the HTML:

- **Phone**: `(619) 555-0123` → Ari's real phone number
- **Email**: `ari@arirent.com` → Ari's real email (appears twice - contact section and CTA button)
- **Instagram**: `@arirent_sd` → Ari's real Instagram handle
- **Website**: `www.arirent.com` → Ari's real website (or remove this contact item if not needed)

### 3. Update Map Pins (Rental Properties)

In the JavaScript section at the bottom (lines 748-758), update the rental property locations:

```javascript
// Replace these coordinates and addresses with actual rental properties
L.marker([32.7701, -117.2528], {icon: rentalIcon})
    .bindPopup('<strong>Property 1</strong><br>Mission Beach Area<br><em>Replace with actual address</em>')
    .addTo(map);
```

**To find coordinates**:
1. Go to Google Maps
2. Right-click on the property location
3. Click the coordinates to copy them
4. Replace the `[latitude, longitude]` values

**Current placeholder locations**:
- Property 1: Mission Beach area (32.7701, -117.2528)
- Property 2: Pacific Beach area (32.7969, -117.2530)
- Property 3: Beach area (32.7845, -117.2345)

### 4. Update Stats (Optional)

In the Stats Bar section (lines 543-555), update:
- Number of properties managed (currently "3+")
- Occupancy rate (currently "100%")
- Major universities served (currently "2")

### 5. Change Stock Photos (Optional)

If you want different stock photos, replace the Unsplash URLs:

**Current Images**:
- Hero background: San Diego apartments
- Property owners card: Modern home exterior
- Students card: Students studying together
- Gallery: 3 beach/lifestyle photos

**How to replace**:
1. Go to [Unsplash.com](https://unsplash.com)
2. Search for your desired image (e.g., "san diego beach", "modern apartment")
3. Copy the image URL (use the download URL for best quality)
4. Replace the `src` attribute in the HTML

Example:
```html
<img src="https://images.unsplash.com/photo-YOUR-NEW-PHOTO-ID?w=800&q=80" alt="Description">
```

## Converting to PDF

### Method 1: Browser Print (Recommended)

1. Open `flyer.html` in Chrome, Safari, or Edge
2. Press `Cmd + P` (Mac) or `Ctrl + P` (Windows)
3. Settings:
   - **Destination**: Save as PDF
   - **Layout**: Portrait
   - **Margins**: Default
   - **Scale**: 100%
   - **Background graphics**: ✓ ON (very important!)
4. Click "Save"

### Method 2: Online Converter

1. Visit [CloudConvert](https://cloudconvert.com/html-to-pdf)
2. Upload `flyer.html`
3. Convert and download

### Method 3: Command Line (Advanced)

If you have `wkhtmltopdf` installed:

```bash
cd AriRent
wkhtmltopdf --enable-local-file-access flyer.html flyer.pdf
```

Or using Chrome headless:

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --headless --disable-gpu --print-to-pdf=flyer.pdf flyer.html
```

## Distribution

### Digital
- Email as PDF attachment to prospective landlords
- Share on social media
- Add to website
- Include in email signature

### Print
- **Paper**: Use high-quality cardstock (80-100 lb)
- **Size**: Standard letter (8.5" × 11")
- **Color**: Full color (CMYK)
- **Finish**: Matte or glossy coating (optional but recommended)

## Technical Details

### Dependencies
- **Leaflet.js**: 1.9.4 (for interactive map)
- **Google Fonts**: Inter & Playfair Display
- **Unsplash**: Stock photography

### Browser Support
- Chrome/Edge (latest)
- Safari (latest)
- Firefox (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

### File Size
- HTML file: ~25 KB
- Images loaded from CDN (Unsplash)
- Total page load: ~2-3 MB

## Tips for Best Results

1. **Professional Photo**: Invest in a professional headshot if you don't have one. Good lighting and a genuine smile go a long way.

2. **Test Print**: Print one copy on regular paper first to check colors and layout before mass printing.

3. **Update Regularly**: Keep property count and stats current to maintain credibility.

4. **Mobile View**: The flyer is fully responsive - it looks great on phones and tablets too!

5. **Map Accuracy**: Make sure rental property pins are in the correct locations. Landlords will appreciate the geographic transparency.

## Customization Beyond Basics

### Change Color Scheme

The current teal/ocean theme uses:
- Primary: `#0e7490`
- Secondary: `#2a9d8f`

To change, search and replace these hex codes in the CSS.

### Adjust Typography

Fonts are loaded from Google Fonts. To change:

1. Visit [Google Fonts](https://fonts.google.com)
2. Select new fonts
3. Replace the font link in the `<head>` section
4. Update `font-family` in CSS

### Modify Layout

The flyer uses CSS Grid for most layouts. Key sections:
- `.services-grid`: 2 columns
- `.features-grid`: 4 columns
- `.gallery-grid`: 3 columns
- `.contact-grid`: 4 columns

Adjust `grid-template-columns` values to change layouts.

## Need Help?

The HTML is well-organized with comments marking each section. The CSS is grouped by section for easy editing.

## Version

Current Version: 2.0 (Professional Designer Edition)
Last Updated: 2025

---

**Pro Tip**: Before sending to landlords, save specific versions with their property highlighted on the map!
