# Jekyll Recipe Blog Setup Guide

## Project Structure

```
recipe-blog/
├── _config.yml
├── _layouts/
│   ├── default.html
│   └── recipe.html
├── _recipes/
│   ├── baked-pork-chop-rice.md
│   ├── matcha-latte.md
│   └── (add more recipes here)
├── _includes/
│   └── recipe-card.html
├── assets/
│   ├── css/
│   │   └── style.css
│   └── images/
│       └── (recipe images go here)
├── index.html
├── about.md
└── .gitignore
```

## Setup Instructions

### 1. Create GitHub Repository

```bash
mkdir recipe-blog
cd recipe-blog
git init
```

### 2. Create _config.yml

This file tells Jekyll how to process your site. Copy the provided `_config.yml` into your root directory.

### 3. Create Folder Structure

```bash
mkdir _layouts
mkdir _recipes
mkdir _includes
mkdir -p assets/css
mkdir -p assets/images
```

### 4. Add Layout Files

- Copy `default.html` to `_layouts/default.html`
- Copy `recipe.html` to `_layouts/recipe.html`
- Copy `recipe-card.html` to `_includes/recipe-card.html`

### 5. Add Recipe Files

- Copy all `.md` files into `_recipes/` folder
- Add your recipe images to `assets/images/` folder

### 6. Add Style

- Copy `style.css` to `assets/css/style.css`

### 7. Create index.html

Copy the provided `index.html` to your root directory.

### 8. Deploy to GitHub Pages

```bash
git add .
git commit -m "Initial recipe blog setup"
git remote add origin https://github.com/yourusername/recipe-blog.git
git branch -M main
git push -u origin main
```

Then in your GitHub repository settings:
- Go to Settings → Pages
- Source: Deploy from a branch
- Branch: main, folder: / (root)
- Save

Your site will be live at `https://yourusername.github.io/recipe-blog/` in 1-2 minutes.

## Adding Recipes

1. Create a new `.md` file in `_recipes/` folder
2. Use the frontmatter from the sample recipe
3. Write your recipe content in markdown
4. Commit and push to GitHub
5. Your recipe automatically appears on the site!

## Frontmatter Metadata

Each recipe file must have frontmatter (the section between `---`):

```yaml
---
layout: recipe
title: Recipe Name
course: dinner  # breakfast, lunch, dinner, dessert
season: fall    # spring, summer, fall, winter
prep_time: 30 minutes
cook_time: 45 minutes
servings: 4
image: /assets/images/recipe-name.jpg
---
```

## Image Optimization

- Keep images under 200KB
- Use JPG or PNG format
- Recommended size: 800x600px or 1200x900px
- Name images with hyphens: `baked-pork-chop-rice.jpg`

## CommentBox.io Integration

The recipe layout template includes a placeholder for CommentBox.io. To enable comments:

1. Sign up at commentbox.io
2. Get your project ID
3. In `_layouts/recipe.html`, replace `YOUR_PROJECT_ID` with your actual ID
4. Comments will appear on all recipe pages

## Local Testing (Optional)

To test locally before pushing to GitHub:

```bash
# Install Ruby and Jekyll
gem install bundler jekyll

# Create Gemfile
bundle init

# Add gem "github-pages" to Gemfile
# Then run:
bundle exec jekyll serve

# Visit http://localhost:4000
```

## Troubleshooting

**Recipes not showing**: Check frontmatter syntax (dashes, spacing)
**Images not loading**: Verify image paths start with `/assets/images/`
**Site not updating**: Clear browser cache, wait 2-3 minutes for GitHub to rebuild
**YAML errors**: Use this site to validate: https://www.yamllint.com/

## Tips for Success

- Use consistent filenames (kebab-case: `recipe-name.md`)
- Keep image filenames matching recipe filenames
- Test markdown formatting at https://markdownlivepreview.com/
- Use descriptive alt text for images
- Group similar recipes together with consistent metadata
