# 🇦🇺 OzBudget — Australia Working Holiday Visa Calculator
<!-- v1.0.0 · 2025-03-17 -->

A free, fully client-side financial toolkit built for Working Holiday Visa holders (subclass 417 & 462) working in Australia. No backend, no database — everything runs in the browser.

**Live demo:** [your-site.netlify.app](https://your-site.netlify.app)

---

## Features

| Tab | Description |
|-----|-------------|
| 💰 Income & Tax | ATO 2024–25 WHV tax brackets, dual job income, Medicare levy toggle, shareable URL |
| 🧾 Budget & Expenses | 9 expense categories, city presets, donut chart, savings projections |
| 🏦 Superannuation | Employer contribution tracker, DASP tax calculator (65% WHV rate), claim guide |
| ⏰ Penalty Rates | Hospitality, Retail, Fast Food & Farm award multipliers for evenings/weekends/public holidays |
| 🎯 Rate Goal | Reverse-calculates the hourly rate or hours/week needed to hit a savings goal |
| 📊 City Compare | Side-by-side savings breakdown for Sydney, Melbourne, Brisbane, Perth, and Regional |
| 💱 Currency Converter | 16 home currencies with editable exchange rate, hourly rate in your currency |
| 🚜 2nd Year Visa | 88-day regional work progress tracker, cost vs earnings, net financial outcome |
| 📋 Tax Return | Estimates refund or liability based on tax withheld vs actual ATO obligation |

---

## Tax Rates Used (ATO 2024–25 WHV)

| Taxable Income | Rate |
|----------------|------|
| $0 – $45,000 | 15% |
| $45,001 – $135,000 | 32.5% |
| $135,001 – $190,000 | 37% |
| Over $190,000 | 45% |

> No tax-free threshold applies to Working Holiday Makers.

---

## Project Structure

```
ozbudget/
├── index.html          # Main calculator app (single-page, all tabs)
├── about.html          # About page (required for AdSense approval)
├── privacy-policy.html # Privacy policy (GDPR / AdSense compliant)
├── README.md           # This file
└── .gitignore
```

---

## Deploy to Netlify

### Option 1 — Drag & Drop (quickest)

1. Go to [netlify.com](https://netlify.com) and sign in
2. Click **Add new site → Deploy manually**
3. Drag the entire project folder into the drop zone
4. Done — live in seconds

### Option 2 — Git (recommended for updates)

```bash
# 1. Create a new repo on GitHub and push
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/YOUR_USERNAME/ozbudget.git
git push -u origin main

# 2. In Netlify: Add new site → Import from Git → select your repo
# 3. Build settings: leave blank (static site, no build command needed)
# 4. Click Deploy
```

After connecting Git, every `git push` to `main` will auto-deploy.

---

## Google AdSense Setup

The site is AdSense-ready. To activate ads:

### Step 1 — Get approved
1. Deploy the site to Netlify
2. Go to [adsense.google.com](https://adsense.google.com) and submit your Netlify URL
3. Wait for approval (1–14 days)

### Step 2 — Add your publisher ID
In `index.html`, find and uncomment this line near the top of `<head>`:

```html
<!-- <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXXXXX" crossorigin="anonymous"></script> -->
```

Replace `ca-pub-XXXXXXXXXXXXXXXX` with your real publisher ID.

### Step 3 — Add ad slot IDs
Search `index.html` for both `<ins class="adsbygoogle">` tags and update:

```html
data-ad-client="ca-pub-YOUR_PUBLISHER_ID"
data-ad-slot="YOUR_AD_SLOT_ID"
```

Create ad units in **AdSense → Ads → By ad unit → Display ads** to get slot IDs.

Ad units are hidden by default and only shown after a user accepts the cookie consent banner.

---

## Cookie Consent

A GDPR-compliant cookie banner is included. It:

- Shows on first visit
- Stores consent in `localStorage` (key: `oz_consent`)
- Only loads AdSense after the user clicks **Accept all**
- Respects **Decline** — ads stay hidden permanently for that user

---

## City Presets (Monthly Estimates)

| Category | Sydney | Melbourne | Brisbane | Perth | Regional |
|----------|--------|-----------|----------|-------|----------|
| Rent | $1,800 | $1,600 | $1,400 | $1,300 | $200 |
| Food | $450 | $420 | $380 | $360 | $280 |
| Eating out | $200 | $180 | $160 | $150 | $80 |
| Shopping | $120 | $110 | $100 | $100 | $60 |
| Electricity | $90 | $85 | $100 | $95 | $60 |
| Water | $50 | $45 | $50 | $45 | $30 |
| Transport | $160 | $150 | $130 | $120 | $80 |
| Phone | $30 | $30 | $30 | $30 | $30 |
| Other | $120 | $110 | $100 | $90 | $60 |
| **Total** | **$3,020** | **$2,730** | **$2,450** | **$2,290** | **$880** |

---

## Shareable URLs

The Income & Tax tab generates a shareable URL encoding all income and expense values as query parameters. Example:

```
https://your-site.netlify.app/?p=hourly&i=28&h=38&j2=0&ml=0&e_rent=1600&e_food=400...
```

This lets users bookmark or share their exact budget setup.

---

## Tech Stack

- **Pure HTML / CSS / JavaScript** — zero dependencies, zero build step
- **Google Fonts** — DM Serif Display + DM Sans
- **No frameworks, no npm, no bundler**

---

## Customisation

### Update tax rates
Edit the `TAX_BRACKETS` array in `index.html`:

```js
const TAX_BRACKETS = [
  { min: 0,      max: 45000,   rate: 0.15  },
  { min: 45000,  max: 135000,  rate: 0.325 },
  { min: 135000, max: 190000,  rate: 0.37  },
  { min: 190000, max: Infinity, rate: 0.45 },
];
```

### Add a currency
Add to `FX_RATES` and `FX_SYMBOLS`, then add an `<option>` to the currency select dropdown:

```js
const FX_RATES   = { ..., IDR: 10500 };
const FX_SYMBOLS = { ..., IDR: 'Rp'  };
```

### Change city presets
Edit the `CITY_PRESETS` object in `index.html`.

---

## Disclaimer

OzBudget is a guide only. Tax laws change and individual circumstances vary. This tool does not constitute financial or tax advice. For personalised advice consult a registered tax agent or visit [ato.gov.au](https://www.ato.gov.au).

---

## License

This project is open source. Feel free to fork, modify, and deploy your own version.
