# Changelog

All notable changes to OzBudget are documented here.  
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).  
Versioning follows [Semantic Versioning](https://semver.org/) — `MAJOR.MINOR.PATCH`.

---

## [1.5.0] — 2025-03-17

### Changed
- `about.html` — Updated hero tagline from "Built for backpackers, by a backpacker" to "Built for seekers, by a Reacher"

### Files changed
| File | Version |
|------|---------|
| `about.html` | 1.5.0 |

---

## [1.4.0] — 2025-03-17

### Added
- `index.html` — Combined Option B (visual bracket bar) and Option C (full reference table) to replace the plain text bracket breakdown
- Bracket bar: colour-coded stacked segments for all 4 WHV tax brackets, animated income pin marker, colour legend
- Reference table: 5-column table showing bracket range, rate pill, your slice, tax on slice, running total
- Active bracket highlights with gold left border and background tint
- Inactive (unreached) brackets faded to 45% opacity
- Medicare levy row appended to table when enabled
- New CSS classes: `.bk-bar-wrap`, `.bk-bar-track`, `.bk-seg`, `.bk-pin`, `.bk-legend`, `.bk-table`, `.bk-rate-pill`, `.bk-active`, `.bk-inactive`

### Removed
- `index.html` — Old plain `.brow` / `.brow-dot` bracket breakdown list replaced by B+C visualiser

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.4.0 |

---

## [1.3.0] — 2025-03-17

### Added
- `index.html` — Income summary bar added to all 7 secondary tabs (Superannuation, Penalty Rates, Goal, City Compare, Currency, 2nd Year Visa, Tax Return)
- Each summary bar shows contextually relevant figures pulled live from the Income & Tax tab
- New CSS class `.income-summary`, `.is-item`, `.is-label`, `.is-value`, `.is-dot`
- JS: `setIS()` helper to populate all summary bar elements on every `updateAll()` call

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.3.0 |

---

## [1.2.0] — 2025-03-17

### Changed
- `index.html` — Merged Income & Tax tab and Budget & Expenses tab into a single combined first tab ("💰 Income, Tax & Budget")
- Tab nav reduced from 9 tabs to 8 tabs
- Combined tab renders two stacked grid rows: income inputs + results on top, expenses + budget summary below

### Removed
- `index.html` — Separate `#tab-budget` page section and its nav button removed

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.2.0 |

---

## [1.1.0] — 2025-03-17

### Added
- `index.html` — 9-tab navigation layout replacing the original single-page layout
- New tabs: 💰 Income & Tax, 🧾 Budget, 🏦 Superannuation, ⏰ Penalty Rates, 🎯 Rate Goal, 📊 City Compare, 💱 Currency, 🚜 2nd Year Visa, 📋 Tax Return
- Superannuation tab: employer contribution tracker, DASP tax calculator (65% WHV rate), claim guide
- Penalty Rates tab: Hospitality, Retail, Fast Food, Farm award multipliers; rates for evenings, weekends, public holidays
- Rate Goal tab: reverse-calculates required hourly rate and hours/week to hit a savings target
- City Compare tab: side-by-side savings breakdown for Sydney, Melbourne, Brisbane, Perth, Regional
- Currency Converter tab: 16 home currencies, editable exchange rate, hourly net in home currency
- 2nd Year Visa tab: 88-day progress tracker, cost vs earnings during regional work, net financial outcome
- Tax Return tab: refund/liability estimator based on tax withheld vs ATO obligation
- Shareable URL feature: encodes all income and expense values as query parameters
- Dual-job income field (second job AUD/week)
- City preset buttons (Sydney, Melbourne, Brisbane, Perth, Regional) auto-fill expense fields
- Income summary bar on all secondary tabs showing live figures from Income & Tax tab
- `README.md` — Full project documentation including deploy guide, AdSense setup, customisation reference
- `.gitignore` — OS, editor, Node, build, environment, and Netlify entries

### Changed
- `index.html` — Full rebuild from single-page layout to tabbed multi-section app
- `about.html` — Added feature table, ATO rate table, super/DASP section, disclaimer box, CTA button
- `privacy-policy.html` — Expanded to cover Google Analytics, AdSense cookie details, GDPR rights, Netlify hosting

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.1.0 |
| `about.html` | 1.1.0 |
| `privacy-policy.html` | 1.1.0 |
| `README.md` | 1.0.0 (new) |
| `.gitignore` | 1.0.0 (new) |

---

## [1.0.1] — 2025-03-17

### Added
- `index.html` — Google AdSense `<ins class="adsbygoogle">` ad units added (top and bottom, hidden by default)
- Two ad placements: below hero section, above footer
- Ad units only revealed after user accepts cookie consent
- `loadAdsense()` function shows ad containers and pushes to `adsbygoogle` queue
- AdSense `<script>` tag added to `<head>` (commented out, ready for publisher ID)
- Nav links to About and Privacy pages added to header
- `index.html` — Cookie consent banner (fixed bottom): Accept / Decline buttons, stores preference in `localStorage`
- `privacy-policy.html` — Full GDPR-compliant privacy policy covering cookies, AdSense, Analytics, Netlify, user rights
- `about.html` — About page with feature overview, ATO rate table, disclaimer; required for AdSense approval

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.0.1 |
| `privacy-policy.html` | 1.0.0 (new) |
| `about.html` | 1.0.0 (new) |

---

## [1.0.0] — 2025-03-17

### Added
- `index.html` — Initial release of OzBudget WHV tax calculator
- Income inputs: pay period toggle (hourly / weekly / fortnightly / annual), hours per week, Medicare levy toggle
- ATO 2024–25 WHV tax brackets: 15% ≤$45k · 32.5% $45k–$135k · 37% $135k–$190k · 45% above $190k
- Tax results: annual gross, tax withheld, effective rate, Medicare levy, annual net, weekly net
- Monthly expense tracker: Rent, Food & Groceries, Eating Out, Shopping, Electricity, Water, Transport, Phone, Other
- Budget summary: donut chart (tax / expenses / savings), health status chip, savings projections (3/6/9/12 months)
- Dark theme with CSS custom properties
- Fonts: DM Serif Display + DM Sans (Google Fonts)
- Cookie consent banner with `localStorage` persistence
- Google AdSense placeholder (commented out)
- Responsive layout: 2-column grid collapsing to 1 column below 820px

### Files changed
| File | Version |
|------|---------|
| `index.html` | 1.0.0 (new) |

---

## Version summary

| File | Current version |
|------|----------------|
| `index.html` | **1.4.0** |
| `about.html` | **1.5.0** |
| `privacy-policy.html` | **1.0.1** |
| `README.md` | **1.0.0** |
| `.gitignore` | **1.0.0** |
