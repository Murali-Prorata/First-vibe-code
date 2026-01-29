# Text Ads Webpage

A modern, responsive webpage featuring a gradient header, content section, and two professionally styled text advertisements.

## Features

- **Gradient Header** - Eye-catching purple gradient background with welcome messaging
- **Content Section** - Placeholder text describing the platform and services
- **Responsive Grid Layout** - 2 text ads that adapt seamlessly to all screen sizes
- **Professional Ad Design** - Each ad includes:
  - "Sponsored" label
  - Clickable headline (styled in blue)
  - Display URL (styled in green)
  - Description text
  - Call-to-action button
- **Interactive Hover Effects** - Border color changes and shadow effects on hover
- **Modern Styling** - Clean, professional design with smooth transitions

## Page Structure

### Header
- Large gradient background (purple shades)
- Welcome title and subtitle
- Prominent visual presence

### Content Section
- Descriptive heading and paragraph
- Platform introduction
- Sets context for featured ads

### Text Advertisements
1. **CloudHost Pro** - Cloud hosting service with 50% discount offer
2. **CodeAcademy** - Free web development courses

### Footer
- Copyright information
- Professional footer styling

## Files

- `index.html` - Main webpage file with all HTML, CSS, and styling
- `README.md` - This documentation file

## How to Use

1. Open `index.html` in your web browser
2. View the gradient header and welcome message
3. Read the content section description
4. Browse the two featured text advertisements
5. Click on ad headlines or call-to-action buttons to interact

## Customization

### Editing Ad Content
- Modify ad headlines in the `<h3>` tags
- Update display URLs in `.display-url` divs
- Change descriptions in `.ad-description` paragraphs
- Update button text and links in `.ad-link` elements

### Changing Colors
- **Gradient Header**: Edit the `background: linear-gradient()` in the `header` style
- **Link Colors**: Modify the color values in `.text-ad h3` (blue) and `.display-url` (green)
- **Buttons**: Change `background-color` in `.ad-link` and `.ad-link:hover`

### Adjusting Layout
- **Grid Columns**: Modify `grid-template-columns` in `.ads-container` to change ad count per row
- **Gap Between Ads**: Adjust the `gap` value in `.ads-container`
- **Content Width**: Change `max-width` values to make sections wider or narrower

### Hover Effects
- Border color and shadow changes are defined in `.text-ad:hover`
- Modify `border-color` and `box-shadow` values to customize effects

## Browser Support

Works on all modern browsers:
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## Responsive Design

The webpage is fully responsive with:
- Mobile-first approach
- Flexible grid layout that adapts to screen size
- Touch-friendly button sizes
- Readable font sizes on all devices

## Notes

- All links currently point to "#" as placeholders - replace with actual URLs as needed
- The gradient header color scheme can be customized to match your brand
- Additional ads can be added by copying the text-ad div structure
