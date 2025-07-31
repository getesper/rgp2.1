# WYSIWYG CMS Setup Guide

## 🎯 Recommended: Strapi CMS

Strapi provides a powerful WYSIWYG editor that integrates perfectly with your Next.js site.

### Quick Setup:

1. **Deploy Strapi to Railway/Heroku:**
```bash
# Create new Strapi project
npx create-strapi-app@latest rgp-cms --quickstart
```

2. **Content Types to Create:**
   - **Classes** (name, description, schedule, instructor)
   - **Instructors** (name, bio, photo, specialties)
   - **Announcements** (title, content, date, priority)
   - **Gallery** (title, images, category)
   - **Testimonials** (name, content, rating, photo)

3. **Connect to Next.js:**
   - Add Strapi API calls to your pages
   - Use real-time content updates

### Alternative: Contentful (Enterprise)

- **Pros**: Professional WYSIWYG, content modeling
- **Cons**: Expensive ($300+/month)
- **Best for**: Large organizations with budget

### Alternative: Sanity.io

- **Pros**: Real-time collaboration, custom studio
- **Cons**: Learning curve
- **Best for**: Teams that need real-time editing

## 🔧 Implementation Steps

### Step 1: Deploy Strapi
```bash
# Create Strapi project
npx create-strapi-app@latest rgp-cms --quickstart

# Deploy to Railway
railway login
railway init
railway up
```

### Step 2: Configure Content Types
1. Go to Strapi admin panel
2. Create "Classes" content type
3. Add fields: title, description, schedule, instructor, image
4. Repeat for other content types

### Step 3: Connect to Next.js
```typescript
// lib/strapi.ts
const STRAPI_URL = process.env.STRAPI_URL;

export async function getClasses() {
  const res = await fetch(`${STRAPI_URL}/api/classes?populate=*`);
  return res.json();
}
```

### Step 4: Update Pages
```typescript
// app/schedule/page.tsx
import { getClasses } from '@/lib/strapi';

export default async function SchedulePage() {
  const { data: classes } = await getClasses();
  
  return (
    <div>
      {classes.map(class => (
        <div key={class.id}>
          <h3>{class.attributes.title}</h3>
          <p>{class.attributes.description}</p>
        </div>
      ))}
    </div>
  );
}
```

## 💰 Cost Comparison

| Platform | WYSIWYG | Cost | Setup Time |
|----------|---------|------|------------|
| **Strapi** | ✅ Excellent | Free | 2-3 hours |
| Contentful | ✅ Professional | $300+/month | 1 hour |
| Sanity.io | ✅ Great | Free tier | 3-4 hours |
| WordPress | ✅ Good | Free | 4-5 hours |
| Webflow | ✅ Excellent | $14+/month | Rebuild needed |

## 🎯 Recommendation

**Start with Strapi** - it's free, powerful, and integrates perfectly with your Next.js site. You can always upgrade to Contentful later if you need enterprise features.

Would you like me to help you set up Strapi for your martial arts academy? 