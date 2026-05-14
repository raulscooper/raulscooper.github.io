# raulscooper.github.io

Open blueprints for India. Updated weekly.

---

## Folder structure

```
raulscooper.github.io/
│
├── index.html                  ← HOME PAGE (catalog of all ideas)
│
├── spotclean/
│   └── index.html              ← SpotClean India playbook
│
├── becoming-pm/
│   └── index.html              ← The Common Man's Road to PM
│
├── your-next-idea/             ← add a new folder for each new idea
│   └── index.html
│
└── README.md
```

Each idea lives in its own folder with its own `index.html`.  
The homepage (`index.html`) is the catalog that links to all of them.

---

## How to add a new idea each week

### Step 1 — Create a folder
Name it something short and URL-friendly (no spaces, lowercase):
```
cleaning-india/
water-crisis/
startup-india/
```

### Step 2 — Add your idea's index.html
Drop your HTML file in that folder and name it `index.html`.  
Use the PM blueprint file as a template — same design system, same fonts.

### Step 3 — Add a card to the homepage
Open `index.html` in the root folder.  
Find the comment that says `<!-- add new cards below this comment -->`.  
Copy and paste this block above that comment:

```html
<a class="card" href="YOUR-FOLDER-NAME/index.html" data-category="CATEGORY">
  <div class="card-tag">CATEGORY</div>
  <div class="card-title">YOUR TITLE</div>
  <div class="card-desc">One or two sentences describing the idea.</div>
  <div class="card-footer">
    <span class="card-date">Month Year</span>
    <span class="card-arrow">→ Read</span>
  </div>
</a>
```

Replace:
- `YOUR-FOLDER-NAME` → the folder you created in Step 1
- `CATEGORY` → one of: `politics`, `civic`, `economy`, `governance`
- `YOUR TITLE`, description, and date

### Step 4 — Commit and push
```bash
git add .
git commit -m "Add: [your idea title]"
git push
```

GitHub Pages publishes automatically within ~60 seconds.

---

## To make the first card a large "featured" card

Change `class="card"` to `class="card featured"` and add a number div:

```html
<a class="card featured" href="..." data-category="...">
  <div class="card-number">03</div>   ← increment each time
  <div class="card-body">
    ... rest of card content ...
  </div>
</a>
```

---

## Categories (for the filter buttons)

| Value | Use for |
|---|---|
| `politics` | Electoral strategy, governance, state power |
| `civic` | Community action, public spaces, citizen movements |
| `economy` | Business, jobs, economic policy |
| `governance` | Institutions, law, systems design |

To add a new category, add a filter button in `index.html`:
```html
<button class="filter-btn" data-filter="education">Education</button>
```

---

## Design system

All idea pages use the same fonts (loaded from Google Fonts — no install needed):
- `Playfair Display` — headings
- `Source Serif 4` — body text  
- `IBM Plex Mono` — labels and metadata

Color palette:
- Background: `#f5f0e8` (warm paper)
- Text: `#0f0e0c` (near-black ink)
- Accent: `#e8610a` (saffron orange)
- Muted: `#7a6e5f`

The homepage uses an inverted dark theme (same saffron accent).

---

## That's it.

No build tools. No npm. No frameworks. Pure HTML.  
Publish weekly by adding a folder and one line to the homepage.
