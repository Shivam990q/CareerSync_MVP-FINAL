# Deploying CareerSync Frontend to Vercel

This guide will help you deploy the CareerSync frontend application to Vercel.

## Prerequisites

- A Vercel account (free tier is sufficient)
- Git repository with your CareerSync frontend code

## Steps to Deploy

1. **Push your code to a Git repository**
   Make sure your code is up to date in a GitHub, GitLab, or Bitbucket repository.

2. **Login to Vercel**
   Go to [Vercel](https://vercel.com) and login with your account.

3. **Create a new project**
   - Click "Add New..." → "Project"
   - Import your Git repository
   - Select the repository that contains your CareerSync frontend code

4. **Configure the project**
   - Framework Preset: Select "Vite"
   - Root Directory: Select "Frontend" (if your repository has a Frontend folder)
   - Build Command: `npm run build`
   - Output Directory: `dist`

5. **Set up environment variables**
   Add the following environment variables:
   
   - `VITE_API_BASE_URL`: Set to your backend URL (e.g., https://careersync-backend.vercel.app)

6. **Deploy**
   - Click the "Deploy" button
   - Wait for the build to complete

## Verifying the Deployment

1. Once deployed, Vercel will provide a URL for your application
2. Visit the URL to make sure everything is working correctly
3. Test the job fetching functionality to ensure it connects to the backend properly

## Troubleshooting

- If you encounter CORS issues, make sure your backend allows requests from your frontend Vercel domain
- Check the build logs if the deployment fails
- Verify that all environment variables are set correctly
- Ensure the `vercel.json` configuration is correct
- In case of routing issues, ensure the rewrites in `vercel.json` are working properly

## Custom Domain (Optional)

To set up a custom domain:
1. Go to your project settings in Vercel
2. Click on "Domains"
3. Add your custom domain and follow the instructions to verify ownership 