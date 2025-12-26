# Hugo Fluid Starter

🚀 Quick start template for Hugo Fluid theme - A Material Design theme for Hugo inspired by hexo-theme-fluid.

## Live Demo

🌐 **[View Live Demo →](https://hugo-fluid.github.io)**

## Features

- ✅ Pre-configured with Hugo Modules
- ✅ Complete example content showcasing all theme features
- ✅ Multi-language support (Chinese/English/Traditional Chinese)
- ✅ GitHub Actions deployment included
- ✅ Ready to use out of the box

## Quick Start

### Prerequisites

- Hugo Extended v0.120.0+
- Git 2.0+
- Go 1.21+
- Node.js v18.0+ (for Pagefind search)
- pnpm v8.0+

### Installation

1. **Use this template** (click the green button above) or clone:

```bash
git clone https://github.com/ouraihub-hugo-themes/hugo-theme-fluid-starter.git my-blog
cd my-blog
```

2. **Initialize Hugo Modules**:

```bash
hugo mod get -u
```

3. **Install dependencies** (for search):

```bash
pnpm install
```

4. **Start development server**:

```bash
pnpm dev
```

5. **Visit** http://localhost:1313

## What's Included

This starter includes complete example content from the theme's exampleSite:

### 📝 Content
- **27 example posts** showcasing all theme features
- **Multi-language content** (zh/en/tw)
- **All page types**: About, Links, Archives, Categories, Tags
- **Feature demos**: Math formulas, Mermaid diagrams, Code blocks, etc.

### ⚙️ Configuration
- **Complete theme configuration** with detailed comments
- **Multi-language setup** ready to use
- **SEO optimization** configured
- **Comment systems** ready to enable

### 🎨 Customization
- **Banner images** for all page types
- **Color scheme** configuration
- **Typography** settings
- **Social icons** setup

## Customization

### 1. Basic Settings

Edit `config/_default/hugo.toml`:
```toml
baseURL = "https://your-domain.com/"
title = "Your Blog Title"
```

### 2. Theme Parameters

Edit `config/_default/params.toml`:
```toml
[navbar]
blog_title = "Your Blog"

[about]
name = "Your Name"
intro = "Your introduction"
```

### 3. Add Your Content

Replace the example content in `content/` with your own:

```bash
# Create a new post
hugo new content/zh/post/my-first-post.md
hugo new content/en/post/my-first-post.md
```

### 4. Customize Images

Replace images in `static/images/` or override theme images in `static/img/`:
- `static/img/avatar.png` - Your avatar
- `static/img/home.webp` - Homepage banner
- Add your own images to `static/images/`

## Deployment

### GitHub Pages

This starter includes GitHub Actions for automatic deployment:

1. Go to repository **Settings → Pages**
2. Set **Source** to "GitHub Actions"
3. Push to main branch

### Other Platforms

- **Vercel**: Connect your GitHub repository
- **Netlify**: Connect your GitHub repository
- **Manual**: Run `pnpm build` and deploy the `public/` folder

## Commands

```bash
# Development
pnpm dev              # Start development server
pnpm dev:debug        # Start with debug logging

# Building
pnpm build            # Build for production (Hugo only)
pnpm build:with-search # Build with Pagefind search (when theme supports it)
pnpm build:hugo       # Build Hugo only (alias for build)
pnpm preview          # Preview production build

# Maintenance
pnpm clean            # Clean build artifacts
pnpm update-theme     # Update theme to latest version

# Search (experimental)
pnpm pagefind         # Generate search index (requires theme support)
```

## Search Functionality

The Hugo Fluid theme includes built-in search functionality. External search indexing with Pagefind is currently disabled until the theme templates are updated to support it. The theme's native search should work out of the box.

## Updating Theme

```bash
hugo mod get -u
hugo mod tidy
```

## Support

- **Theme Documentation**: [Hugo Fluid Docs](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid)
- **Hugo Documentation**: [Hugo Docs](https://gohugo.io/documentation/)
- **Issues**: [Report Issues](https://github.com/ouraihub-hugo-themes/hugo-theme-fluid/issues)

## License

MIT License - see [LICENSE](LICENSE) for details.

## Acknowledgments

- Original [hexo-theme-fluid](https://github.com/fluid-dev/hexo-theme-fluid) theme
- Hugo community for the amazing static site generator