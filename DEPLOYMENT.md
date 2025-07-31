# Deployment Guide

This Next.js site is configured for static export and can be deployed to multiple platforms.

## 🚀 Quick Deploy Options

### 1. **Vercel (Recommended)**
- Go to [vercel.com](https://vercel.com)
- Connect your GitHub repository
- Vercel will automatically detect Next.js and deploy
- **No configuration needed!**

### 2. **Netlify (Already configured)**
- Go to [netlify.com](https://netlify.com)
- Connect your GitHub repository
- Build command: `bun run build`
- Publish directory: `out`
- **Already configured with `netlify.toml`**

### 3. **GitHub Pages**
1. Push your code to GitHub
2. Go to your repository Settings → Pages
3. Set source to "GitHub Actions"
4. The workflow in `.github/workflows/deploy.yml` will handle the rest

### 4. **Cloudflare Pages**
- Go to [pages.cloudflare.com](https://pages.cloudflare.com)
- Connect your GitHub repository
- Build command: `bun run build`
- Publish directory: `out`

## 🔧 Local Build Test

To test the build locally:

```bash
# Install dependencies
bun install

# Build the site
bun run build

# The static files will be in the `out` directory
```

## 📁 Build Output

The build creates static files in the `out` directory, which can be served by any static hosting service.

## 🌐 Custom Domain

All platforms support custom domains:
- **Vercel**: Add domain in project settings
- **Netlify**: Add domain in site settings
- **GitHub Pages**: Add CNAME file or configure in settings
- **Cloudflare Pages**: Add domain in project settings 