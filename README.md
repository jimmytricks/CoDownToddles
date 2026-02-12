# Co Down Events

Events viewer for children's activities around County Down, Northern Ireland.

## Features

- Day-by-day navigation
- UK timezone (Europe/London) with automatic BST/GMT handling
- Toggle between toddler and adult events
- Card or timeline view
- Live open/closed status
- Mobile responsive
- Preferences saved in browser

## Adding Events

Edit `index.html` and find the `events` array (around line 800). Add a new entry:

```javascript
{
  name: 'Venue Name',
  url: 'https://example.com',
  category: 'toddler', // or 'adult'
  schedule: [
    // Days: 0=Sun, 1=Mon, 2=Tue, 3=Wed, 4=Thu, 5=Fri, 6=Sat
    { days: [1, 3, 5], times: [{ start: '09:00', end: '17:00' }] },
    { days: [6], times: [{ start: '10:00', end: '16:00' }] }
  ]
}
```

For split hours:
```javascript
{ days: [0], times: [
  { start: '10:00', end: '12:00' },
  { start: '14:00', end: '16:00' }
]}
```

## Current Events

Toddler Events:
- Newry Leisure Swimming (Learner Pool)
- Newry Soft Play
- Tiddly Town Newry
- Cheeky Monkeys (Sheepbridge)
- Cheeky Monkeys Parent & Toddler
- Infinity Adventure Park (Toddler Mornings)

Adult Events:
- Newry Health Suite

## Tech

- Vue.js 3 (CDN)
- CSS Grid (mobile-first)
- localStorage for preferences
- Intl.DateTimeFormat for timezone

## Deployment

Works on GitHub Pages. Push to a public repo, enable Pages in Settings.

Site will be at: `https://username.github.io/repo-name/`

## Customization

Colors are in CSS variables at line 17:
```css
:root {
  --toddler-bg: linear-gradient(135deg, #ff6b35 0%, #f7931e 100%);
  --adult-bg: linear-gradient(135deg, #00c9ff 0%, #92fe9d 100%);
}
```
