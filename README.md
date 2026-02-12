# 🎈 Co Down Toddler Events

A colorful, mobile-friendly web app for viewing children's activities and events around County Down, Northern Ireland.

## Features

- 📅 **Day-by-day navigation** - View events for any day with easy prev/next buttons
- 🇬🇧 **UK timezone aware** - Automatically highlights today based on Europe/London timezone (handles BST/GMT)
- 👶 **Category filtering** - Toggle between toddler-only events and all events
- 🕐 **Live status** - Shows "Open Now" or "Closed Now" based on current UK time
- 📱 **Mobile-first design** - Fully responsive, works great on phones and tablets
- ♿ **Accessible** - WCAG AA compliant with keyboard navigation, screen reader support
- 🎨 **Fun & colorful** - Quirky design with gradients and playful typography
- 💾 **Remembers preferences** - Filter choice saved in browser localStorage

## Quick Start

### View Locally

1. Simply open `index.html` in any modern web browser
2. No build tools, dependencies, or server required!

### Deploy to GitHub Pages

1. Create a new public repository on GitHub
2. Push this code to the repository:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
   git push -u origin main
   ```
3. Go to repository **Settings** → **Pages**
4. Under "Source", select branch `main` and folder `/` (root)
5. Click **Save**
6. Your site will be available at: `https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/`

Note: First deployment takes up to 10 minutes. Subsequent updates deploy automatically on each push.

## Adding New Events

To add a new event, edit `index.html` and find the `events` array (around line 500). Add a new object following this structure:

```javascript
{
  name: 'Event Name Here',
  url: 'https://example.com', // Leave empty '' if not available yet
  category: 'toddler', // or 'adult'
  schedule: [
    // Days: 0=Sunday, 1=Monday, 2=Tuesday, 3=Wednesday, 4=Thursday, 5=Friday, 6=Saturday
    { days: [1, 3, 5], times: [{ start: '09:00', end: '17:00' }] }, // Mon, Wed, Fri
    { days: [6], times: [{ start: '10:00', end: '16:00' }] }, // Saturday different hours
    // Multiple time slots for split days:
    { days: [0], times: [
      { start: '10:00', end: '12:00' },
      { start: '14:00', end: '16:00' }
    ]}
  ]
}
```

### Example: Adding a New Venue

```javascript
{
  name: 'PlayZone Banbridge',
  url: 'https://playzone-banbridge.co.uk',
  category: 'toddler',
  schedule: [
    { days: [1, 2, 3, 4, 5], times: [{ start: '09:00', end: '18:00' }] }, // Mon-Fri
    { days: [6, 0], times: [{ start: '10:00', end: '17:00' }] } // Sat-Sun
  ]
}
```

## Current Events

### Toddler Events (7)
1. Newry Leisure Swimming (Learner Pool)
2. Newry Soft Play
3. Tiddly Town Newry
4. Cheeky Monkeys (Sheepbridge)
5. Cheeky Monkeys Parent & Toddler
6. Infinity Adventure Park (Toddler Mornings)

### Adult/Family Events (1)
1. Newry Health Suite

## Tech Stack

- **Vue.js 3** (ES Module via CDN) - Reactive UI framework
- **Vanilla CSS** - Mobile-first responsive design with CSS Grid
- **Google Fonts** (Fredoka) - Fun, friendly typography
- **localStorage API** - Remember user preferences
- **Intl.DateTimeFormat** - UK timezone handling

## Browser Support

Works on all modern browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Android)

## Accessibility Features

- Semantic HTML5 elements
- ARIA labels and live regions
- Keyboard navigation support
- 4.5:1 color contrast ratios
- 44px minimum touch targets
- Skip-to-content link
- Reduced motion support
- Screen reader friendly

## Customization

### Change Colors

Edit CSS variables in the `:root` section (around line 15):

```css
:root {
  --toddler-bg: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  --adult-bg: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);
  /* etc... */
}
```

### Change Font

Replace the Google Fonts link in the `<head>` and update `font-family` in CSS.

### Update Last Modified Date

Find `lastUpdated` in the JavaScript (around line 740) and update the string.

## License

Free to use and modify for personal or commercial purposes.

## Support

For issues or questions, please open an issue on GitHub.

---

Made with 💜 for Co Down families
