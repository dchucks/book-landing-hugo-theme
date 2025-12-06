# BookLanding Hugo Theme

A modern, responsive Hugo theme designed specifically for book landing pages. Perfect for authors, publishers, and self-publishers who want a professional single-page site to showcase and sell their books.

![BookLanding Theme Preview](images/screenshot.jpg)

## ✨ Features

- 📱 **Fully Responsive** - Looks great on mobile, tablet, and desktop
- 🎨 **Blue/Green Color Scheme** - Professional and modern (easily customizable)
- 📚 **Book Carousel** - Showcase your other books with a horizontal scrolling carousel
- 🎯 **Content-Driven** - All content in Markdown and data files (no code changes needed)
- ⚡ **Fast & Lightweight** - Minimal JavaScript, optimized CSS
- 🔧 **Modular Design** - Each section is a separate partial for easy customization
- 💳 **Multiple Buy Options** - Support for multiple retailers (Amazon, Kindle, PDF, etc.)
- ⭐ **Testimonials Section** - Display reader reviews with star ratings
- ❓ **FAQ Section** - Answer common reader questions
- 📧 **Newsletter Integration** - Optional newsletter signup section
- 🎭 **Font Awesome Icons** - Beautiful icons throughout
- 🌐 **SEO Optimized** - Proper meta tags and semantic HTML

## 🎯 Perfect For

- Fiction and non-fiction authors
- Self-published authors
- eBook launches
- Book pre-orders
- Author portfolios
- Publishing houses

## 📸 Demo

**Live Demo:** [View Demo](https://agile-field-guide.netlify.app/)

**Example Site:** See `exampleSite/` directory for a complete working example.

## 🚀 Quick Start

### Prerequisites

- Hugo Extended v0.80.0 or higher
- Git

### Installation

#### Method 1: Git Submodule (Recommended)

```bash
# From your Hugo site root
git submodule add https://github.com/dchucks/book-landing-hugo-theme.git themes/book-landing-hugo-theme

# Copy example site files
cp themes/book-landing-hugo-theme/exampleSite/config.toml .
cp -r themes/book-landing-hugo-theme/exampleSite/content .
cp -r themes/book-landing-hugo-theme/exampleSite/data .

# Create images directory
mkdir -p static/images/other-books

# Run Hugo
hugo server -D
```

#### Method 2: Clone

```bash
# Clone the theme
git clone https://github.com/dchucks/book-landing-hugo-theme.git themes/book-landing-hugo-theme

# Copy example files
cp themes/book-landing-hugo-theme/exampleSite/config.toml .
cp -r themes/book-landing-hugo-theme/exampleSite/content .
cp -r themes/book-landing-hugo-theme/exampleSite/data .

# Run Hugo
hugo server -D
```

## 📝 Configuration

### 1. Site Configuration (`config.toml`)

```toml
baseURL = "https://yourbook.com/"
languageCode = "en-us"
title = "Your Book Title"
theme = "book-landing-hugo-theme"

[params]
  description = "Your book description"
  
  [params.author]
    name = "Your Name"
    image = "/images/author-photo.jpg"
    bio = "Short bio"
    
    [params.author.social]
      website = "https://yourwebsite.com"
      newsletter = "https://yournewsletter.com"
```

### 2. Homepage Content (`content/_index.md`)

```yaml
---
title: "Your Book Title"
subtitle: "Compelling subtitle"
bookPrice: "$19"
originalPrice: "$29"

buyLinks:
  - name: "Buy on Amazon"
    url: "https://amazon.com/your-book"
    icon: "fa-brands fa-amazon"
    category: "ebook"

newsletter:
  enabled: true
  title: "Stay Updated"
  url: "https://newsletter.com"

heroImage: "/images/book-cover.png"
---

Your book description here...
```

### 3. Data Files (`data/`)

Customize these data files:

- `features.toml` - Main feature cards
- `testimonials.toml` - Reader reviews
- `faq.toml` - Frequently asked questions
- `whatsinside.toml` - Benefits and target audience
- `otherbooks.toml` - Your other books in carousel
- `buyoptions.toml` - Format comparison
- `author.toml` - Extended author bio (optional)

## 🎨 Customization

### Colors

Edit `themes/book-landing-hugo-theme/static/css/style.css`:

```css
:root {
    --primary-color: #0ea5e9;      /* Main blue */
    --primary-dark: #0284c7;       /* Dark blue */
    --secondary-color: #10b981;    /* Green accent */
    --accent-color: #6ee7b7;       /* Light green */
}
```

### Sections

All sections are modular partials in `layouts/partials/`:

- `hero.html` - Hero section
- `features.html` - Feature cards
- `whats-inside.html` - Benefits
- `testimonials.html` - Reviews
- `author.html` - Author bio
- `author-books-carousel.html` - Book carousel
- `buy-now.html` - Purchase options
- `faq.html` - FAQ
- `newsletter.html` - Newsletter signup

Remove or rearrange sections by editing `layouts/index.html`.

## 📚 Adding Books to Carousel

Edit `data/otherbooks.toml`:

```toml
[[books]]
title = "Your Other Book"
description = "Brief description"
cover = "/images/other-books/book-cover.jpg"
buyUrl = "https://amazon.com/your-book"
price = "$19"
```

**Image recommendations:**
- Size: 400×600px (2:3 aspect ratio)
- Format: JPG, optimized to <150KB
- Consistent dimensions for all books

## 🖼️ Images Guide

### Book Cover (`static/images/book-cover.png`)
- **Size:** 400×600px (2:3 ratio)
- **Format:** PNG or JPG
- **Quality:** High resolution for hero section

### Author Photo (`static/images/author-photo.jpg`)
- **Size:** 500×500px minimum
- **Format:** JPG
- **Style:** Professional headshot

### Other Books (`static/images/other-books/`)
- **Size:** 400×600px each
- **Format:** JPG
- **Naming:** `book-name-cover.jpg`

## 📱 Sections Included

1. **Hero** - Book title, subtitle, description, and cover
2. **Features** - Key benefits and features (6 cards)
3. **What's Inside** - Benefits, bonus content, target audience
4. **Testimonials** - Reader reviews with ratings
5. **Author** - Bio with social links and book carousel
6. **Buy Now** - Purchase options for ebook and paperback
7. **FAQ** - Common questions
8. **Newsletter** - Optional signup section
9. **Footer** - Links and copyright

## 🌐 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📦 What's Included

```
book-landing-hugo-theme/
├── layouts/
│   ├── index.html              # Homepage template
│   ├── _default/
│   │   └── baseof.html        # Base template
│   └── partials/
│       ├── hero.html
│       ├── features.html
│       ├── testimonials.html
│       ├── author.html
│       ├── author-books-carousel.html
│       ├── buy-now.html
│       ├── faq.html
│       └── ...
├── static/
│   ├── css/
│   │   └── style.css          # Theme styles
│   └── js/
│       └── main.js            # Theme JavaScript
├── exampleSite/               # Complete working example
└── theme.toml                 # Theme metadata
```

## 🚢 Deployment

### Netlify

1. Push to GitHub
2. Connect repo to Netlify
3. Build command: `hugo`
4. Publish directory: `public`

### Vercel

1. Import GitHub repository
2. Vercel auto-detects Hugo
3. Deploy!

### GitHub Pages

Use Hugo's GitHub Actions workflow. See [Hugo documentation](https://gohugo.io/hosting-and-deployment/hosting-on-github/).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This theme is released under the GPL-3.0 License. See [LICENSE](LICENSE) file for details.

## 🙏 Credits

- Built with [Hugo](https://gohugo.io/)
- Icons by [Font Awesome](https://fontawesome.com/)
- Fonts by [Google Fonts](https://fonts.google.com/)

## 💬 Support

- **Documentation:** [GitHub Wiki](https://github.com/dchucks/book-landing-hugo-theme/wiki)
- **Issues:** [GitHub Issues](https://github.com/dchucks/book-landing-hugo-theme/issues)

## 🎯 Roadmap

- [ ] Dark mode support
- [ ] Multiple color scheme presets
- [ ] Video section for book trailers
- [ ] Blog integration
- [ ] Multilingual support
- [ ] Audio sample player

## ⭐ Show Your Support

If you found this theme helpful, please give it a star on GitHub!
<p><a href="https://ko-fi.com/debashish"><img src="https://storage.ko-fi.com/cdn/cup-border.png" alt="Buy Me a Coffee!" align="center" width="75px" height="auto">&nbsp;Buy me a Coffee ;)</a></p>

---

**Made with ❤️ for authors by an author**