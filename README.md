# Welcome to our Platform

A comprehensive AI search and advertising platform featuring multiple search variants, sponsored content integration, and brand agent chatbots. Built with HTML5, CSS3, and vanilla JavaScript—no external dependencies required.

## Platform Overview

This platform showcases three distinct AI search page variants, each with unique content delivery and sponsorship strategies:

1. **Variant 1 (Original)** - Bottom-positioned search bar with sponsored prompt pills at the top
2. **Variant 2** - Top search bar with sponsored content block embedded mid-answer
3. **Variant 3** - Top search bar with Nike brand agent chatbot integrated in answers

## Core Features

- **Dynamic AI Search** - Conversational search interface with auto-generated answers
- **Sponsored Content** - Multiple sponsorship integration patterns (pills, mid-content blocks, brand agents)
- **Brand Agent Chatbots** - Interactive agents representing advertisers with product recommendations
- **Responsive Design** - Mobile-first approach with media queries for screens ≤700px
- **CSS Animations** - Marquee scrolling for prompt pills (28-34 second infinite loop)
- **Interactive Conversations** - User questions and AI responses in a chat-like interface
- **Product Recommendations** - Integrated product cards with "Buy now" call-to-action buttons
- **Query Parameter Routing** - URL-based navigation using `?q=` encoded prompts

## File Structure

### Landing Page
- **`index.html`** - Main demo page with 2 text advertisements (CloudHost Pro, CodeAcademy), gradient header, and content section

### Variant 1: Original Search (Bottom Bar)
- **`ai_search.html`** - Search page with sticky bottom search bar and 2 rows of sponsored prompt pills
- **`ai_result.html`** - Result page with conversational answer, "Actionable steps" section, and related questions (top 3 sponsored)

### Variant 2: Sponsored Content (Mid-Answer)
- **`ai_search2.html`** - Search page with top search bar and 2 rows of prompt pills (no "Sponsored" labels)
- **`ai_results2.html`** - Result page with CloudHost Pro sponsored block inserted between summary and actionable steps
- **`sponsored_info.html`** - Advertiser details page showing CloudHost Pro plans with 2 product cards

### Variant 3: Brand Agent (Nike)
- **`ai_search3.html`** - Search page identical to ai_search2.html, all pills route to ai_results3.html
- **`ai_results3.html`** - Result page with clickable Nike agent chat bubble positioned under actionable steps
- **`nike_agent.html`** - Brand agent conversational page with:
  - "I am the brand agent for Nike. Ask your question" greeting
  - AI-generated answer tailored to user question
  - "Recommended Products" section with 2 product cards
  - Persistent "Is there anything I can help with?" follow-up chat

### Advertiser Pages
- **`advertiser.html`** - Display ad page with mountain image (mountain.svg) linking from ai_copilot.html
- **`ai_copilot.html`** - Copilot variant with top search bar ("I am your copilot"), 2 rows of prompt pills, and display ad

### Documentation
- **`README.md`** - This file

## Visual Design

### Color Scheme
- **Primary Gradient**: Linear gradient from #667eea (blue) to #764ba2 (purple)
- **User Messages**: Light blue background (#eaf1ff)
- **AI Messages**: Light gray background (#f3f4f8)
- **Sponsored Content**: Yellow/gold accent (#fff3cd, #ffc107)
- **Buttons**: Primary blue (#667eea) with purple hover (#764ba2)

### Typography
- **Font Family**: System fonts (-apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif)
- **Font Weights**: Regular (400), Semi-bold (600), Bold (700)
- **Responsive Sizing**: Adjusts for mobile (max-width: 700px)

### Layout Components
- **Header**: Full-width gradient background with centered title
- **Container**: Max-width 900px, centered with responsive padding
- **Cards**: Rounded corners (12px), shadow effects, white backgrounds
- **Buttons**: Padded, rounded, with hover effects and smooth transitions
- **Grid**: 2-column product grid, responsive to single column on mobile

## Assets

### SVG Files
- **`favicon.svg`** - Gradient rounded square with "WP" initials (purple gradient)
- **`mountain.svg`** - Mountain landscape image for display ads (ai_copilot.html, advertiser.html)
- **`product1.svg`** - Green-themed product card (Mountain Tent) for sponsored_info.html
- **`product2.svg`** - Blue-themed product card (All-Weather Jacket) for sponsored_info.html

## JavaScript Features

### Dynamic Answer Generation
```javascript
generateAnswer(prompt)
```
- Extracts topic keywords from user prompt
- Creates multi-section answer including:
  - Summary of topic
  - Actionable steps (4-item list)
  - Suggested resources
  - Example checklist
- Returns formatted text with newline separators for HTML conversion

### Query Parameter Handling
```javascript
getQueryParam(name)
```
- Extracts encoded prompt from URL `?q=` parameter
- Uses URLSearchParams API for decoding
- Enables seamless navigation between search and result pages

### Conversation DOM Management
- Creates `.msg.user` and `.msg.ai` divs for conversation bubbles
- Inserts HTML content with line break conversion (`\n` → `<br>`)
- Supports smooth scrolling to latest message

### Chat Bubble Integration
- Clickable chat bubbles link to brand agent pages
- Preserves user question via query parameters
- Enables agent pages to display tailored responses

### Follow-up Chat Handler
- Form submission prevents default and captures input
- Regenerates answer with new question
- Maintains persistent chat interface

## Navigation Flow

### Variant 1 Flow
```
ai_search.html 
  ↓ (pill/form with ?q=prompt)
ai_result.html 
  ↓ (related questions or back link)
ai_search.html
```

### Variant 2 Flow
```
ai_search2.html 
  ↓ (pill/form with ?q=prompt)
ai_results2.html (with CloudHost Pro sponsored block)
  ↓ (sponsored link)
sponsored_info.html
```

### Variant 3 Flow
```
ai_search3.html 
  ↓ (pill/form with ?q=prompt)
ai_results3.html (with Nike chat bubble)
  ↓ (chat bubble click with ?q=prompt)
nike_agent.html (with brand agent + products + follow-up chat)
  ↓ (follow-up form submission)
nike_agent.html (regenerated with new ?q=prompt)
```

### Copilot Flow
```
ai_copilot.html (top search, display ad)
  ↓ (pill/form with ?q=prompt)
ai_result.html
  ↓ (display ad link)
advertiser.html
```

## How to Use

1. **Start at Landing**: Open `index.html` to see featured advertisements
2. **Choose a Variant**:
   - `ai_search.html` - Traditional bottom-bar search
   - `ai_search2.html` - Mid-content sponsored integration
   - `ai_search3.html` - Brand agent chatbot experience
3. **Enter or Select a Prompt**: Type a question or click a sponsored pill
4. **View AI Answer**: Conversational result page with answer and features
5. **Interact with Sponsorships**:
   - **Variant 1**: Click related questions (top 3 are sponsored)
   - **Variant 2**: Click CloudHost Pro block to visit advertiser page
   - **Variant 3**: Click Nike agent chat bubble to open brand agent page
6. **Follow-up (Variant 3)**: Ask brand agent follow-up questions in the persistent chat

## CSS Animations

### Marquee Scroll
- Animation duration: 28-34 seconds per row (varies by row)
- Direction: Left-to-right on first row, right-to-left on second row
- Iteration: Infinite, continuous loop
- Transform: Horizontal translateX from 0% to -50% (duplicated content)
- Performance: Uses `will-change: transform` for optimization

## Technical Stack

- **HTML5**: Semantic structure, SVG support
- **CSS3**: Flexbox layouts, gradients, animations, media queries
- **JavaScript (Vanilla)**: ES5+ compatible
  - URLSearchParams API for query parsing
  - DOM manipulation via `createElement`, `appendChild`, `innerHTML`
  - Event handling: form submission, click handlers
  - setTimeout for animation delays
- **No External Dependencies**: Self-contained with inline CSS and JS

## Browser Compatibility

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Mobile responsive (tested at 700px breakpoint)
- SVG support required for favicon and images

## Performance Considerations

- Minimal DOM operations
- CSS animations use GPU-accelerated transforms
- Smooth scrolling with `behavior: smooth`
- Lazy answer generation (700ms delay for UI feel)

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
