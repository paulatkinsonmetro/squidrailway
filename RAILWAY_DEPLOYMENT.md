# Railway Deployment Guide for SquidRailway

## Prerequisites
- GitHub repository with this code
- Railway account
- Shopify Partner account

## Step 1: Create Railway Project
1. Go to [Railway.app](https://railway.app)
2. Click "New Project"
3. Select "Deploy from GitHub repo"
4. Connect your GitHub account and select the `squidrailway` repository

## Step 2: Add PostgreSQL Database
1. In your Railway project, click "New"
2. Select "Database" → "PostgreSQL"
3. Railway will automatically create a PostgreSQL database
4. Note the connection details (you'll need them for environment variables)

## Step 3: Configure Environment Variables
In your Railway project settings, add these environment variables:

### Database
- `DATABASE_URL`: Copy from your PostgreSQL service (Railway provides this automatically)

### Shopify App
- `SHOPIFY_API_KEY`: Your Shopify app's API key
- `SHOPIFY_API_SECRET`: Your Shopify app's API secret
- `SHOPIFY_APP_URL`: Your Railway app URL (e.g., `https://your-app.railway.app`)
- `SHOPIFY_SCOPES`: `write_products,read_products`

### App Environment
- `NODE_ENV`: `production`

## Step 4: Deploy
1. Railway will automatically deploy when you push to your main branch
2. The app will run the database migrations automatically
3. Your app will be available at the Railway-provided URL

## Step 5: Update Shopify App Configuration
1. Go to your Shopify Partner dashboard
2. Update your app's App URL to match your Railway URL
3. Update the allowed redirection URLs to include your Railway URL

## Troubleshooting
- Check Railway logs if deployment fails
- Ensure all environment variables are set correctly
- Verify the database connection is working
- Make sure your Shopify app configuration matches your Railway URL 