# Lanka Explorer

**Live link:** _(add your Netlify / GitHub Pages link here if you deployed)_

**Group name:** _(your group name)_
**Tagline:** Lanka Explorer – Discover the Pearl of the Indian Ocean

## Project description

Lanka Explorer is a front-end web app for planning a trip around Sri Lanka. Visitors can browse 10 destinations, check live weather, see entry fees in US dollars and Sri Lankan rupees, view places on a map, and build a trip with a total budget.

## Members and roles

| Member | Role |
|--------|------|
| _(name)_ | Project Lead |
| _(name)_ | Content Lead |
| _(name)_ | Data Lead |
| _(name)_ | UI Lead |

## Features

- Five semantic, responsive pages with a shared header, navigation and footer
- Destinations loaded from `data/destinations.json` with `fetch()`; cards generated with JavaScript
- Search, category filter and sort that work together, with a result counter
- Details page driven by the URL (`details.html?id=3`)
- Live weather and 3-day forecast, fee conversion to rupees, and interactive maps
- Loading spinners and friendly error messages for every API
- My Trip planner saved in `localStorage`, with traveller count and total budget in USD and LKR
- Dark mode that remembers the user's choice
- Enquiry form with JavaScript validation
- Mobile menu for phones and tablets

## APIs used

- **Open-Meteo**: current weather and 3-day forecast
- **Frankfurter**: USD to LKR exchange rate
- **Leaflet + OpenStreetMap**: interactive maps

See `API-NOTES.md` for details.

## How to run

1. Open the `lanka-explorer` folder in VS Code.
2. Install the **Live Server** extension (Ritwick Dey).
3. Right-click `index.html` and choose **Open with Live Server**.
4. The address bar should show `http://127.0.0.1:5500/`. Opening the files straight from disk will not work, because `fetch()` needs a web server.

## Lighthouse scores

| Page | Performance | Accessibility | Best practices | SEO |
|------|-------------|---------------|----------------|-----|
| Home | _(score)_ | _(score)_ | _(score)_ | _(score)_ |
| Details | _(score)_ | _(score)_ | _(score)_ | _(score)_ |

## Project structure

```
lanka-explorer/
├── index.html
├── destinations.html
├── details.html
├── trip.html
├── about.html
├── README.md
├── API-NOTES.md
├── css/style.css
├── js/app.js
├── data/destinations.json
├── images/
└── screenshots/
```

## Week 02: Specificity answer

**Why does the checkbox label rule need to be `#enquiry-form fieldset label` rather than just `fieldset label`?**

The earlier rule `#enquiry-form label` sets `font-weight: 600` on every label in the form, including the checkbox labels inside the fieldset. Its specificity is one id plus one element. The shorter selector `fieldset label` is only two elements, so it is less specific and loses even though it is written later; the checkbox labels stay bold. Writing `#enquiry-form fieldset label` (one id plus two elements) is more specific than `#enquiry-form label`, so `font-weight: 400` wins and the checkbox labels become normal weight.
