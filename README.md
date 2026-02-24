# Eerz what's on

[eerz.com](https://eerz.com) - Events viewer for children's activities around Newry, County Down. 

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

## Tech

- Vue.js 3 (CDN)
- CSS Grid (mobile-first)
- localStorage for preferences
- Intl.DateTimeFormat for timezone
