# Vercel Deployment Settings

## 🚀 **Exact Vercel Configuration**

When setting up your project in Vercel, use these exact settings:

### **Project Settings:**
- **Framework Preset**: `Next.js` (auto-detected)
- **Root Directory**: `./` (leave as default)
- **Build Command**: `npm run build` (or `bun run build` if you prefer)
- **Output Directory**: `out` (this is crucial!)
- **Install Command**: `npm install` (or `bun install`)

### **Environment Variables (if needed):**
```
NODE_ENV=production
```

### **Build Settings:**
- **Node.js Version**: `18.x` (recommended)
- **Override**: No (let Vercel auto-detect)

## 🔧 **Why These Settings Work:**

### **Output Directory: `out`**
Your `next.config.js` has:
```javascript
output: 'export',
distDir: 'out',
```
This means your static files are built to the `out` directory.

### **Build Command: `npm run build`**
This runs the Next.js build process that creates static files.

## 📋 **Step-by-Step Vercel Setup:**

1. **Go to [vercel.com](https://vercel.com)**
2. **Sign up/login with GitHub**
3. **Click "New Project"**
4. **Import Repository**: `getesper/rgp2.1`
5. **Configure Project**:
   - Framework: Next.js (auto-detected)
   - Root Directory: `./`
   - Build Command: `npm run build`
   - Output Directory: `out`
   - Install Command: `npm install`
6. **Click "Deploy"**

## ⚙️ **Advanced Settings (Optional):**

### **Custom Domain:**
- Add in Project Settings → Domains
- Vercel will provide DNS instructions

### **Environment Variables:**
- Add in Project Settings → Environment Variables
- Usually not needed for static sites

### **Analytics:**
- Enable in Project Settings → Analytics
- Track performance and visitors

## 🎯 **What Vercel Will Do:**

✅ **Auto-detect Next.js**  
✅ **Install dependencies** (`npm install`)  
✅ **Build your site** (`npm run build`)  
✅ **Deploy static files** from `out` directory  
✅ **Enable CDN** for global performance  
✅ **Add HTTPS** automatically  
✅ **Create preview URLs** for PRs  

## 🚨 **Important Notes:**

### **Static Export Compatibility:**
Your site is perfectly configured for Vercel because:
- `output: 'export'` in `next.config.js`
- `distDir: 'out'` specifies output directory
- All images use `unoptimized: true`

### **No Server-Side Features:**
Since you're using static export:
- No API routes
- No server-side rendering
- No dynamic routes (unless pre-generated)

## 🎉 **After Deployment:**

Your site will be available at:
- **Production**: `https://your-project-name.vercel.app`
- **Custom Domain**: `https://yourdomain.com` (if configured)

## 🔄 **Automatic Deployments:**

Once connected, Vercel will:
- Deploy on every push to `main`
- Create preview URLs for pull requests
- Allow rollbacks to previous versions

Your martial arts academy site will be live and fast! 🥋 