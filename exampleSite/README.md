# Book Landing Hugo Theme - Example Site

This is a complete working example of the Book Landing Hugo theme, perfect for your Hugo website for your own book.

## 🚀 Quick Start - Testing This Example

```bash
# Navigate to the example site directory
cd themes/book-landing-hugo-theme/exampleSite

# Run Hugo server (note the themesDir flag)
hugo server --themesDir ../..

# Open your browser
# Visit: http://localhost:1313
```

The `--themesDir ../..` flag tells Hugo to look for themes two directories up.

---

## 📦 Installing This Theme for Your Book

### Method 1: Using Git Submodule (Recommended)

```bash
# From your site root
git submodule add https://github.com/dchucks/book-landing-hugo-theme.git themes/book-landing-hugo-theme

# Copy example files to your site
cp themes/book-landing-hugo-theme/exampleSite/config.toml .
cp -r themes/book-landing-hugo-theme/exampleSite/content .
cp -r themes/book-landing-hugo-theme/exampleSite/data .

# Create images directory
mkdir -p static/images/other-books

# Add your images
# - static/images/book-cover.png (400×600px or 2:3 ratio image recommended)
# - static/images/author-photo.jpg
# - static/images/other-books/*.jpg

# Run your site
hugo server -D
```

### Method 2: Manual Installation

```bash
# Clone the theme
git clone https://github.com/dchucks/book-landing-hugo-theme.git themes/book-landing-hugo-theme

# Copy example files
cp themes/book-landing-hugo-theme/exampleSite/config.toml .
cp -r themes/book-landing-hugo-theme/exampleSite/content .
cp -r themes/book-landing-hugo-theme/exampleSite/data .

# Add your images and customize
hugo server -D
```

---

## 📝 Customization Guide

### 1. **Site Configuration** (`config.toml`)

Edit the main config file to set your book and author details:

```toml
title = "Your Book Title"

[params]
  description = "Your book description"
  
  [params.author]
    name = "Your Name"
    image = "/images/author-photo.jpg"
    bio = "Short bio about you"
```

### 2. **Homepage Content** (`content/_index.md`)

Update the front matter and body content:

```yaml
---
title: "Your Book Title"
subtitle: "Your compelling subtitle"
bookPrice: "$19"
originalPrice: "$29"
buyLinks:
  - name: "Buy on Amazon"
    url: "https://amazon.com/your-book"
    icon: "fa-brands fa-amazon"
    category: "ebook"
---

Your book description goes here...
```

### 3. **Data Files** (`data/`)

Customize these files for your book:

- **`data/features.toml`** - Main feature cards on homepage
- **`data/testimonials.toml`** - Reader reviews
- **`data/faq.toml`** - Frequently asked questions
- **`data/whatsinside.toml`** - Benefits, bonus content, target audience
- **`data/otherbooks.toml`** - Your other books in the carousel
- **`data/buyoptions.toml`** - Format comparison (ebook vs paperback)
- **`data/author.toml`** - Extended author bio (optional)

### 4. **Images**

Add your images to `static/images/`:

```
static/images/
├── book-cover.png          # 400×600px (2:3 ratio)
├── author-photo.jpg        # Any size, will be scaled
└── other-books/
    ├── book1-cover.jpg     # 400×600px each
    ├── book2-cover.jpg
    └── book3-cover.jpg
```

**Image Size Recommendations:**
- Book covers: 400×600px (2:3 aspect ratio)
- Author photo: 500×500px or larger
- Format: JPG (optimized to <150KB)

---

## 🎨 Color Customization

The theme uses a blue/green color scheme. To customize:

Edit `themes/book-landing-hugo-theme/static/css/style.css`:

```css
:root {
    --primary-color: #0ea5e9;      /* Main color */
    --primary-dark: #0284c7;       /* Darker shade */
    --primary-light: #38bdf8;      /* Lighter shade */
    --secondary-color: #10b981;    /* Accent color */
    --accent-color: #6ee7b7;       /* Light accent */
}
```

---

## 📚 Adding Books to the Carousel

Edit `data/otherbooks.toml`:

```toml
[[books]]
title = "Your Other Book"
description = "Brief description of the book"
cover = "/images/other-books/another-book.jpg"
buyUrl = "https://amazon.com/your-other-book"
price = "$19"
```

Add as many books as you want - the carousel scrolls horizontally!

---

## 🔧 Advanced Configuration

### Custom Menu Items

Edit `config.toml`:

```toml
[[menu.main]]
  name = "Blog"
  url = "/blog"
  weight = 8
```

### Disable Newsletter Section

In `content/_index.md`:

```yaml
newsletter:
  enabled: false
```

### Add Custom CSS

Create `static/css/custom.css` and add to `layouts/partials/head.html`:

```html
<link rel="stylesheet" href="{{ "css/custom.css" | relURL }}">
```

---

## 📖 Example Data Structure

### Minimal Setup (Just the Essentials)

```
your-site/
├── config.toml                    # Site config
├── content/
│   └── _index.md                  # Homepage
├── data/
│   ├── features.toml              # 6 feature cards
│   ├── testimonials.toml          # 3-6 reviews
│   └── faq.toml                   # 5-10 questions
├── static/
│   └── images/
│       ├── book-cover.png
│       └── author-photo.jpg
└── themes/
    └── book-landing-hugo-theme/               # This theme
```

### Full Setup (All Features)

Add these optional files:

```
data/
├── whatsinside.toml               # Benefits & audience
├── otherbooks.toml                # Book carousel
├── buyoptions.toml                # Format comparison
└── author.toml                    # Extended bio
```

---

## 🚢 Deployment

### Netlify

1. Push your site to GitHub
2. Connect repository to Netlify
3. Build settings:
   - Build command: `hugo`
   - Publish directory: `public`

### Vercel

1. Import your GitHub repository
2. Vercel auto-detects Hugo
3. Deploy!

### GitHub Pages

Add `.github/workflows/deploy.yml` - see theme documentation.

---

## 📄 License

This theme is released under the GPL-3.0 License. See [../../LICENSE](LICENSE) file for details.

---

## 🆘 Support

- **Documentation:** https://github.com/yourusername/booklanding
- **Issues:** https://github.com/yourusername/booklanding/issues
- **Discussions:** https://github.com/yourusername/booklanding/discussions

---

## 🎯 Quick Checklist

Before going live, make sure you've:

- [ ] Updated `config.toml` with your book title and author
- [ ] Customized `content/_index.md` with your book description
- [ ] Added your book cover image (400×600px)
- [ ] Added your author photo
- [ ] Updated `data/features.toml` with your book's features
- [ ] Added 3-5 testimonials to `data/testimonials.toml`
- [ ] Filled out `data/faq.toml` with common questions
- [ ] Updated buy links in `content/_index.md`
- [ ] Added your other books to `data/otherbooks.toml` (optional)
- [ ] Tested on mobile and desktop
- [ ] Optimized all images (<150KB each)

---

**Happy Publishing! 📚✨**