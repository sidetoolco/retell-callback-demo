# Deployment Guide

This guide covers deploying your Retell callback widget demo to Vercel.

## Quick Deploy to Vercel

### Option 1: Deploy via Vercel CLI (Recommended)

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm install -g vercel
   ```

2. **Deploy from your project directory**:
   ```bash
   cd /Users/edescobar/retell-callback-demo
   vercel
   ```

3. **Follow the prompts**:
   - Log in to your Vercel account
   - Select your scope (sidetoolco)
   - Confirm project settings
   - Deploy!

4. **Your site will be live at**: `https://retell-callback-demo.vercel.app` (or similar)

### Option 2: Deploy via Vercel Dashboard

1. Go to [vercel.com](https://vercel.com)
2. Click "Add New Project"
3. Import from GitHub: `sidetoolco/retell-callback-demo`
4. Click "Deploy"

### Option 3: One-Click Deploy

Click the button below to deploy directly:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/sidetoolco/retell-callback-demo)

## Configuration

### Before Deploying

⚠️ **Important**: Make sure to configure your phone number in `index.html` before deploying!

```html
data-phone-number="+15551234567"  <!-- Replace with your actual number -->
```

### Environment Variables

This demo doesn't require any environment variables since it uses Retell's public key system. All configuration is done via the HTML script tag attributes.

## Post-Deployment

After deployment:

1. **Test the widget** on your live URL
2. **Verify the callback functionality** works correctly
3. **Update your README** with the live demo URL

### Update README with Live Demo

Add this to the top of your README.md:

```markdown
## 🌐 Live Demo

Try the live demo: [https://your-deployment-url.vercel.app](https://your-deployment-url.vercel.app)
```

## Custom Domain (Optional)

To use a custom domain:

1. Go to your Vercel project settings
2. Click "Domains"
3. Add your custom domain
4. Follow Vercel's DNS configuration instructions

## Deployment Settings

The `vercel.json` file is already configured for static site deployment:

```json
{
  "version": 2,
  "builds": [
    {
      "src": "index.html",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/$1"
    }
  ]
}
```

This configuration:
- Serves all files as static assets
- Routes all paths correctly
- Optimizes for performance

## Continuous Deployment

Once connected to GitHub, Vercel will automatically:
- Deploy on every push to `main` branch
- Create preview deployments for pull requests
- Provide deployment URLs for each commit

## Troubleshooting

### Widget Not Loading on Vercel

If the widget doesn't load:
1. Check browser console for CORS errors
2. Verify the Retell widget script is loading
3. Check that your public key is valid

### Phone Number Issues

If calls aren't working:
1. Verify phone number is configured in `index.html`
2. Check phone number format (E.164: `+1234567890`)
3. Ensure Retell account has active credits

### SSL/HTTPS Issues

Vercel automatically provides SSL. If you see mixed content warnings:
1. Verify all resources use HTTPS
2. The Retell widget script already uses HTTPS

## Deployment Checklist

- [ ] Phone number configured in `index.html`
- [ ] Tested locally before deployment
- [ ] Vercel CLI installed (or using dashboard)
- [ ] Connected to GitHub repository
- [ ] Deployed successfully
- [ ] Tested live widget functionality
- [ ] Updated README with live demo URL
- [ ] (Optional) Custom domain configured

## Monitoring

After deployment, you can monitor:
- **Vercel Analytics**: View page visits and performance
- **Retell Dashboard**: Track call volumes and success rates
- **Browser DevTools**: Debug any client-side issues

## Re-deploying

To redeploy after making changes:

```bash
git add .
git commit -m "Your changes"
git push
```

Vercel will automatically detect the push and redeploy.

Or manually trigger a deployment:

```bash
vercel --prod
```

## Additional Resources

- [Vercel Documentation](https://vercel.com/docs)
- [Vercel CLI Reference](https://vercel.com/docs/cli)
- [Static Site Deployment](https://vercel.com/docs/concepts/deployments/overview)
- [Custom Domains](https://vercel.com/docs/concepts/projects/custom-domains)
