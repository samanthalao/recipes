# Jekyll Recipe Blog - Complete File Structure & Quick Reference

## 📁 Project Structure Overview

```
recipe-blog/
├── _config.yml                    # Jekyll configuration
├── _layouts/
│   ├── default.html              # Base layout (header, footer)
│   └── recipe.html               # Individual recipe layout
├── _includes/
│   └── recipe-card.html          # Reusable recipe card component
├── _recipes/                     # Your recipe markdown files
│   ├── baked-pork-chop-rice.md
│   ├── matcha-latte.md
│   ├── yuzu-oolong.md
│   ├── cheese-scones.md
│   ├── chocolate-souffle.md
│   └── ginger-molasses.md
├── assets/
│   ├── css/
│   │   └── style.css             # All styling
│   └── images/
│       ├── baked-pork-chop-rice.jpg
│       ├── matcha-latte.jpg
│       └── (add more images)
├── index.html                    # Homepage with carousel
├── recipe-template.md            # Template for new recipes
├── jekyll-setup-guide.md         # Detailed setup instructions
├── .gitignore                    # Git ignore file
└── README.md                     # (optional) Project readme
```

## 🚀 Quick Setup (5 Minutes)

### Step 1: Create Repository
```bash
mkdir recipe-blog
cd recipe-blog
git init
```

### Step 2: Create Folder Structure
```bash
mkdir _layouts _recipes _includes assets/css assets/images
```

### Step 3: Add All Files
Copy all provided files into their respective folders (see structure above).

### Step 4: Deploy to GitHub
```bash
git add .
git commit -m "Initial recipe blog"
git remote add origin https://github.com/YOUR_USERNAME/recipe-blog.git
git branch -M main
git push -u origin main
```

### Step 5: Enable GitHub Pages
1. Go to GitHub repo → Settings → Pages
2. Source: Deploy from a branch
3. Branch: main, folder: / (root)
4. Save

**Your site is live!** Visit: `https://YOUR_USERNAME.github.io/recipe-blog/`

---

## 📝 Adding Recipes

### Creating a New Recipe File

1. **Copy the template:**
   - Open `recipe-template.md`
   - Save as `_recipes/recipe-name.md` (use hyphens, lowercase)

2. **Fill in frontmatter** (the section between `---`):
   ```yaml
   ---
   layout: recipe
   title: Your Recipe Name
   course: dinner          # breakfast, lunch, dinner, dessert
   season: fall            # spring, summer, fall, winter
   prep_time: 30 minutes
   cook_time: 45 minutes
   servings: 4
   image: /assets/images/recipe-name.jpg
   ---
   ```

3. **Write content** in markdown:
   - `## Story` - Your introduction
   - `## Ingredients` - Use `###` for subsections
   - `## Recipe` - Numbered steps
   - `## Notes` - Tips and variations

4. **Add image:**
   - Place recipe image in `assets/images/`
   - Reference in frontmatter: `/assets/images/filename.jpg`

5. **Commit and push:**
   ```bash
   git add _recipes/your-recipe.md assets/images/recipe-image.jpg
   git commit -m "Add new recipe: Your Recipe Name"
   git push
   ```

### Recipe Naming Convention

```
✓ Good:
  baked-pork-chop-rice.md
  matcha-latte.md
  chocolate-chip-cookies.md

✗ Bad:
  Baked Pork Chop Rice.md   (spaces, capitals)
  recipe1.md                 (not descriptive)
  chocolate_cookies.md       (underscores instead of hyphens)
```

---

## 🎨 Customization Guide

### Change Site Title & Tagline

**File:** `_layouts/default.html`

Find this section:
```html
<h1 class="site-title">
  <a href="{{ '/' | relative_url }}">The Kitchen</a>
</h1>
<p class="site-tagline">Fusion recipes blending eastern and western flavors</p>
```

Change to your desired title and tagline.

### Update Footer

**File:** `_layouts/default.html`

Find:
```html
<p>&copy; 2025 The Kitchen. All rights reserved.</p>
```

Customize as needed.

### Modify Colors

**File:** `assets/css/style.css`

Look for the `:root` color variables at the top:
```css
:root {
  --cream-bg: #f5fafe;           /* Background */
  --primary-blue: #2563eb;       /* Main accent */
  --light-blue: #b8def8;         /* Lighter accent */
  --medium-blue: #389be4;        /* Medium accent */
  /* ... more colors ... */
}
```

Change hex codes to your preferred colors. Tools like [Coolors.co](https://coolors.co) help generate palettes.

### Adjust Fonts

**File:** `assets/css/style.css`

The site uses:
- **Serif (titles):** Cormorant Garamond
- **Sans-serif (body):** Lato

To change, modify the font import in `_layouts/default.html` and update the `font-family` CSS variables.

---

## 💬 Enable CommentBox.io

1. **Sign up** at [commentbox.io](https://commentbox.io)
2. **Get your Project ID** from the dashboard
3. **Update recipe layout:**

**File:** `_layouts/recipe.html`

Find this line:
```javascript
commentBox('5637-PROJECT_ID', {
```

Replace `PROJECT_ID` with your actual ID, e.g.:
```javascript
commentBox('5637-ABCD1234', {
```

Comments will now appear on every recipe page.

---

## 🖼️ Image Optimization Tips

- **Format:** JPG or PNG
- **Size:** Keep under 200KB per image
- **Dimensions:** 800x600px or 1200x900px recommended
- **Naming:** Use hyphens: `recipe-name.jpg`
- **Tools:** Compress with [TinyPNG](https://tinypng.com) or ImageOptim

---

## 🔍 Featured Recipes & Carousel

The homepage carousel automatically pulls from **all recipes in `_recipes/` folder** and rotates every 5 seconds.

To manually control which recipes appear or change rotation speed:

**File:** `index.html`

Find this JavaScript section:
```javascript
setInterval(() => {
  currentIndex = (currentIndex + 1) % recipes.length;
  updateCarousel();
}, 5000);  // ← 5000ms = 5 seconds
```

Change `5000` to your desired milliseconds (e.g., `3000` = 3 seconds).

---

## ✅ Troubleshooting

| Problem | Solution |
|---------|----------|
| Recipes not showing | Check frontmatter YAML syntax (dashes, spacing) |
| Images not loading | Verify path: `/assets/images/filename.jpg` |
| Site not updating | Clear cache, wait 2-3 min for GitHub rebuild |
| Markdown formatting off | Check heading levels (`##`, `###`, etc.) |
| Layout looks broken | Check `assets/css/style.css` loads (no 404 errors) |
| Comments not showing | Verify CommentBox.io Project ID is correct |

---

## 📚 File Reference

### Configuration Files
- **`_config.yml`** - Jekyll settings, collections, defaults
- **`.gitignore`** - Files to exclude from git

### Layout Templates (in `_layouts/`)
- **`default.html`** - Header, footer, navigation structure
- **`recipe.html`** - Individual recipe page with comments

### Components (in `_includes/`)
- **`recipe-card.html`** - Grid card component for recipe list

### Styling
- **`assets/css/style.css`** - All CSS (responsive, colors, animations)

### Homepage
- **`index.html`** - Homepage with carousel and recipe grid

### Recipes (in `_recipes/`)
- **`*.md`** - Individual recipe files in markdown

### Reference Files
- **`recipe-template.md`** - Template for new recipes
- **`jekyll-setup-guide.md`** - Detailed setup instructions

---

## 🌐 Deployment Checklist

Before pushing to GitHub:
- [ ] All recipe markdown files in `_recipes/` folder
- [ ] All recipe images in `assets/images/` folder
- [ ] Recipe filenames match image filenames
- [ ] Frontmatter in all recipe files is valid YAML
- [ ] Site title updated in `_layouts/default.html`
- [ ] Footer text updated (optional)
- [ ] Colors customized in `assets/css/style.css` (optional)
- [ ] CommentBox.io ID added to `_layouts/recipe.html` (optional)

---

## 📖 Useful Resources

- **Jekyll Docs:** https://jekyllrb.com/docs/
- **Markdown Guide:** https://www.markdownguide.org/
- **Color Picker:** https://coolors.co
- **Image Compressor:** https://tinypng.com
- **Emoji Reference:** https://www.emojidb.org/
- **GitHub Pages Help:** https://docs.github.com/en/pages

---

## 💡 Pro Tips

1. **Batch add recipes:** Create all markdown files at once, commit together
2. **Use image alt text:** Helps with SEO and accessibility
3. **Keep recipes organized:** Use consistent formatting and metadata
4. **Test locally:** Use `jekyll serve` to preview before pushing
5. **Version your recipes:** Git tracks all changes, easy to revert
6. **Use descriptive filenames:** Makes management easier as you scale

---

**Everything is set up and ready to go. Happy blogging! 🍳**
