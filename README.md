# Nayalab

Open blueprints for India. Updated weekly.

**Live site:** https://raulscooper.github.io

---

## Folder structure

```
raulscooper.github.io/
│
├── index.html                  ← Homepage (catalog of all ideas)
│
├── spotclean/
│   └── index.html              ← SpotClean India playbook
│
├── becoming-pm/
│   └── index.html              ← The Common Man's Road to PM
│
├── your-next-idea/             ← One folder per new idea
│   └── index.html
│
└── README.md
```

---

## How to add a new idea

### Step 1 — Create a folder
Short, lowercase, no spaces:
```
water-crisis/
startup-india/
fix-schools/
```

### Step 2 — Add your index.html
Drop your HTML file in the folder. Use the existing idea pages as a design template.

### Step 3 — Add a card to the homepage
Open the root `index.html`. Find the comment:
```
<!-- ADD NEW CARDS BELOW THIS LINE -->
```

Copy and paste this block above it:

```html
<a class="card" href="YOUR-FOLDER/index.html" data-category="CATEGORY">
  <div class="card-tag">CATEGORY</div>
  <div class="card-title">YOUR TITLE</div>
  <div class="card-desc">One or two sentence description.</div>
  <div class="card-footer">
    <span class="card-date">Month Year</span>
    <span class="card-arrow">→ Read</span>
  </div>
</a>
```

Replace `YOUR-FOLDER`, `CATEGORY`, `YOUR TITLE`, description, and date.

### Step 4 — Push
```bash
git add .
git commit -m "Add: Your idea title"
git push
```

GitHub Pages publishes within ~60 seconds.

---

## To make a card featured (large, spans 2 columns)

```html
<a class="card featured" href="..." data-category="...">
  <div class="card-number">03</div>
  <div class="card-body">
    <div class="card-tag">...</div>
    <div class="card-title">...</div>
    <div class="card-desc">...</div>
    <div class="card-footer">...</div>
  </div>
</a>
```

Increment the number each time: 01, 02, 03...

---

## Categories

| Value | Use for |
|---|---|
| `politics` | Electoral strategy, power, statecraft |
| `civic` | Community action, public spaces, citizen movements |
| `economy` | Business, jobs, economic policy |
| `governance` | Institutions, law, systems design |

To add a new category, add one button in `index.html`:
```html
<button class="filter-btn" data-filter="education">Education</button>
```

---

## Language switcher

The Google Translate widget is already embedded in the homepage header. It covers all 22 scheduled Indian languages automatically. No setup needed.

---

## Design system

Fonts (Google Fonts, no install):
- `Bebas Neue` — display headings
- `Crimson Pro` — body text
- `IBM Plex Mono` — labels, metadata

Colours:
- Background: `#0a0a08`
- Text: `#f2ede4`
- Accent: `#f07b1f` (saffron)
- Muted: `#6b6560`

---

No build tools. No npm. No frameworks. Pure HTML.
One folder, one file, one card. That's it.

---

## Copyright

© Nayalab 2026. All rights reserved.

All content on this site — articles, strategies, playbooks, and toolkits — is the intellectual property of Nayalab. No part of this content may be reproduced, distributed, adapted, or used for commercial purposes without prior written permission.

Viewing and sharing links to the site is permitted. Reproducing or commercialising the content is not.
