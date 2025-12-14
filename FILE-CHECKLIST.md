# Complete File Checklist & Organization Guide

## ✅ All Files You Received

```
📦 Your Complete Recipe Blog Package
│
├── 🔧 CONFIGURATION FILES (Copy to root)
│   ├── _config.yml                 ✓ Jekyll configuration
│   └── .gitignore                  ✓ Git ignore file
│
├── 🎨 LAYOUT TEMPLATES (Copy to _layouts/ folder)
│   ├── default.html                ✓ Site wrapper (header, footer)
│   └── recipe.html                 ✓ Individual recipe page
│
├── 🧩 COMPONENTS (Copy to _includes/ folder)
│   └── recipe-card.html            ✓ Recipe grid card component
│
├── 🎨 STYLING (Copy to assets/css/ folder)
│   └── style.css                   ✓ Complete responsive CSS
│
├── 📄 HOMEPAGE (Copy to root)
│   └── index.html                  ✓ Homepage with carousel
│
├── 🍳 SAMPLE RECIPES (Copy to _recipes/ folder)
│   ├── baked-pork-chop-rice.md    ✓ Your featured recipe
│   ├── matcha-latte.md            ✓ Breakfast recipe
│   ├── yuzu-oolong.md             ✓ Beverage recipe
│   ├── cheese-scones.md           ✓ Breakfast recipe
│   ├── chocolate-souffle.md       ✓ Dessert recipe
│   └── ginger-molasses.md         ✓ Dessert recipe
│
├── 📋 REFERENCE GUIDES (Keep for reference)
│   ├── README.md                   ✓ Overview & getting started
│   ├── quick-reference.md          ✓ Complete reference guide
│   ├── jekyll-setup-guide.md       ✓ Detailed setup instructions
│   └── recipe-template.md          ✓ Template for new recipes
│
└── 📁 FOLDER STRUCTURE TO CREATE
    ├── _layouts/                   ← Create this folder
    ├── _recipes/                   ← Create this folder
    ├── _includes/                  ← Create this folder
    └── assets/
        ├── css/                    ← Create this folder
        └── images/                 ← Create this folder for recipe photos
```

---

## 🗂️ Step-by-Step File Organization

### 1. Create New GitHub Repository
- Go to github.com/new
- Name: `recipe-blog`
- Public: Yes
- Initialize: No (we'll add files manually)

### 2. Create Local Folder Structure

```bash
recipe-blog/
├── _config.yml
├── _layouts/
│   ├── default.html
│   └── recipe.html
├── _includes/
│   └── recipe-card.html
├── _recipes/
│   ├── baked-pork-chop-rice.md
│   ├── matcha-latte.md
│   ├── yuzu-oolong.md
│   ├── cheese-scones.md
│   ├── chocolate-souffle.md
│   └── ginger-molasses.md
├── assets/
│   ├── css/
│   │   └── style.css
│   └── images/
│       └── (your recipe photos here)
├── index.html
├── .gitignore
├── README.md
├── recipe-template.md
├── jekyll-setup-guide.md
└── quick-reference.md
```

### 3. Copy Files to Correct Locations

| File | Destination |
|------|-------------|
| `_config.yml` | Root folder |
| `default.html` | `_layouts/` |
| `recipe.html` | `_layouts/` |
| `recipe-card.html` | `_includes/` |
| `style.css` | `assets/css/` |
| `index.html` | Root folder |
| `*.md` (recipes) | `_recipes/` |
| `.gitignore` | Root folder |
| Reference files | Root folder |

### 4. Add Images

Place your recipe photos in `assets/images/`:

```
assets/images/
├── baked-pork-chop-rice.jpg
├── matcha-latte.jpg
├── yuzu-oolong.jpg
├── cheese-scones.jpg
├── chocolate-souffle.jpg
└── ginger-molasses.jpg
```

### 5. Commit & Push to GitHub

```bash
git add .
git commit -m "Initial recipe blog setup"
git push origin main
```

---

## 📋 Verification Checklist

Before pushing to GitHub, verify:

- [ ] `_config.yml` is in root folder
- [ ] `.gitignore` is in root folder
- [ ] `index.html` is in root folder
- [ ] `_layouts/default.html` exists
- [ ] `_layouts/recipe.html` exists
- [ ] `_includes/recipe-card.html` exists
- [ ] `assets/css/style.css` exists
- [ ] All 6 recipe `.md` files in `_recipes/` folder
- [ ] All 6 recipe images in `assets/images/` folder
- [ ] Filenames match between recipes and images (mostly)
  - `baked-pork-chop-rice.md` → `baked-pork-chop-rice.jpg` ✓
  - `matcha-latte.md` → `matcha-latte.jpg` ✓
- [ ] No typos in folder names (`_recipes`, `_layouts`, `_includes`)
- [ ] Recipe markdown frontmatter has correct format
- [ ] All references to `{{ site.baseurl }}` in files are consistent

---

## 🔑 Key File Purposes

### Configuration
- **`_config.yml`** - Tells Jekyll about your site structure, collections, and defaults

### Templates (Liquid + HTML)
- **`default.html`** - Wraps every page (header, footer)
- **`recipe.html`** - Individual recipe page template
- **`recipe-card.html`** - Reusable card for recipe grid

### Content
- **`index.html`** - Homepage with carousel (uses Liquid to iterate recipes)
- **Recipe markdown files** - Your actual recipes written in markdown

### Styling
- **`style.css`** - All colors, fonts, spacing, layouts, responsive design

---

## 📝 File Format Details

### Recipe Markdown Files (`_recipes/*.md`)
```markdown
---
layout: recipe
title: Recipe Name
course: dinner
season: fall
prep_time: 30 minutes
cook_time: 45 minutes
servings: 4
image: /assets/images/recipe-name.jpg
---

## Story
Introduction...

## Ingredients
...

## Recipe
1. Step one
...

## Notes
Tips...
```

### Config File (`_config.yml`)
```yaml
title: The Kitchen
description: Fusion recipes
markdown: kramdown
collections:
  recipes:
    output: true
    permalink: /:collection/:name/
```

### Layout Files (Liquid HTML)
Uses Liquid templating:
- `{{ page.title }}` - Variables
- `{% for recipe in site.recipes %}` - Loops
- `{{ content }}` - Page content insertion
- `{% include recipe-card.html %}` - Component reuse

---

## 🚀 Deployment Verification

After pushing to GitHub:

1. **Go to repository settings** → Pages
2. **Source:** Branch: main, folder: / (root)
3. **Wait 1-2 minutes** for deployment
4. **Visit** `https://YOUR_USERNAME.github.io/recipe-blog/`
5. **Verify:**
   - [ ] Homepage loads with carousel
   - [ ] Recipe grid displays 6 recipes
   - [ ] Click a recipe → recipe page loads
   - [ ] Images display correctly
   - [ ] Site is responsive (test on mobile)
   - [ ] Navigation works

---

## 🔄 Adding More Recipes

For each new recipe:

1. **Create file:** `_recipes/recipe-name.md`
2. **Use template** from `recipe-template.md`
3. **Add image:** `assets/images/recipe-name.jpg`
4. **Push to GitHub:**
   ```bash
   git add _recipes/recipe-name.md assets/images/recipe-name.jpg
   git commit -m "Add recipe: Recipe Name"
   git push
   ```

---

## 🎯 Common File Locations to Remember

| Need to... | Edit file... | Location |
|-----------|-------------|----------|
| Change site title | `default.html` | `_layouts/` |
| Change colors | `style.css` | `assets/css/` |
| Add recipe | Create `*.md` | `_recipes/` |
| Add images | Place in folder | `assets/images/` |
| Change carousel speed | `index.html` | Root |
| Configure Jekyll | `_config.yml` | Root |
| Add CommentBox ID | `recipe.html` | `_layouts/` |

---

## 💾 Git Commands Quick Reference

```bash
# After making changes:
git status                    # See what changed
git add .                    # Stage all files
git commit -m "Message"      # Commit with message
git push origin main         # Push to GitHub

# Add specific files:
git add _recipes/new-recipe.md
git add assets/images/photo.jpg
git commit -m "Add new recipe"
git push

# View history:
git log                      # See all commits
git diff                     # See changes
```

---

## ✨ You're All Set!

You have everything needed to:
- ✅ Set up your recipe blog
- ✅ Publish it to GitHub Pages
- ✅ Add unlimited recipes
- ✅ Customize colors and styling
- ✅ Enable comments
- ✅ Scale as you grow

**Start with Step 1 in the README.md file!**
