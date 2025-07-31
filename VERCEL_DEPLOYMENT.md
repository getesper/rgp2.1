# Deploy to Vercel - Step by Step Guide

## 🚀 Quick Deploy (5 minutes)

### Step 1: Push Your Code to GitHub
```bash
# If you haven't already, push your code to GitHub
git add .
git commit -m "Ready for Vercel deployment"
git push origin main
```

### Step 2: Deploy to Vercel
1. Go to [vercel.com](https://vercel.com)
2. Click "Sign Up" (use GitHub account)
3. Click "New Project"
4. Import your GitHub repository
5. Vercel will automatically detect it's a Next.js project
6. Click "Deploy"

**That's it!** Your site will be live in 2-3 minutes.

## 🔧 Advanced Configuration

### Environment Variables (if needed)
If your site uses environment variables, add them in Vercel:
1. Go to your project dashboard
2. Click "Settings" → "Environment Variables"
3. Add any variables your app needs

### Custom Domain
1. Go to your project dashboard
2. Click "Settings" → "Domains"
3. Add your custom domain
4. Update DNS records as instructed

## 📁 What Vercel Does Automatically

✅ **Detects Next.js** - No configuration needed  
✅ **Builds your site** - Runs `bun run build`  
✅ **Deploys static files** - Uses your `out` directory  
✅ **CDN distribution** - Global edge network  
✅ **Automatic HTTPS** - SSL certificates included  
✅ **Preview deployments** - Every PR gets a preview URL  

## 🔄 Continuous Deployment

Once connected, Vercel will:
- **Auto-deploy** on every push to `main`
- **Create preview URLs** for pull requests
- **Rollback** to previous versions if needed

## 🎯 Your Site URL

After deployment, you'll get:
- **Production**: `https://your-project-name.vercel.app`
- **Custom domain**: `https://yourdomain.com` (if configured)

## 🛠️ Troubleshooting

### Build Errors
If you get build errors:
1. Check the build logs in Vercel dashboard
2. Test locally: `bun run build`
3. Make sure all dependencies are in `package.json`

### Image Issues
Your `next.config.js` already has the right settings for static export:
```javascript
output: 'export',
images: {
  unoptimized: true,
}
```

### Performance
Vercel automatically:
- Optimizes images
- Minifies CSS/JS
- Enables gzip compression
- Uses edge caching

## 🎉 Next Steps

1. **Deploy**: Follow the steps above
2. **Test**: Visit your live site
3. **Custom domain**: Add your domain if desired
4. **Monitor**: Check Vercel analytics

Your martial arts academy site will be live and fast! 🥋 