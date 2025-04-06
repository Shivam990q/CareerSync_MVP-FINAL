# Deploying CareerSync Backend to Vercel

This guide will help you deploy the CareerSync backend API to Vercel.

## Prerequisites

- A Vercel account (free tier is sufficient)
- Git repository with your CareerSync backend code
- MongoDB Atlas account (or other MongoDB provider)

## Steps to Deploy

1. **Push your code to a Git repository**
   Make sure your code is up to date in a GitHub, GitLab, or Bitbucket repository.

2. **Login to Vercel**
   Go to [Vercel](https://vercel.com) and login with your account.

3. **Create a new project**
   - Click "Add New..." → "Project"
   - Import your Git repository
   - Select the repository that contains your CareerSync backend code

4. **Configure the project**
   - Framework Preset: Select "Node.js"
   - Root Directory: Select "backend" (if your repository has a backend folder)
   - Build Command: `npm install`
   - Output Directory: Leave blank (not applicable for Node.js)

5. **Set up environment variables**
   Add all the environment variables from your `.env` file:
   
   - `PORT`: Not needed as Vercel will handle this
   - `MONGODB_URI`: Your MongoDB connection string
   - `JWT_SECRET`: Your JWT secret key
   - `JWT_EXPIRES_IN`: JWT token expiration (e.g., "90d")
   - `NODE_ENV`: Set to "production"
   - `GOOGLE_CLIENT_ID`: Your Google OAuth client ID
   - `MONGODB_PUBLIC_KEY`: Your MongoDB Atlas API public key (if applicable)
   - `MONGODB_PRIVATE_KEY`: Your MongoDB Atlas API private key (if applicable)
   - `MONGODB_PROJECT_ID`: Your MongoDB Atlas project ID (if applicable)

6. **Deploy**
   - Click the "Deploy" button
   - Wait for the build to complete

## Verifying the Deployment

1. Once deployed, Vercel will provide a URL for your API
2. Test the API by visiting `https://your-api-url.vercel.app/api/status`
3. You should see a JSON response indicating that the server is running and connected to MongoDB

## Troubleshooting

- Check the Vercel logs if the deployment fails
- Make sure your MongoDB Atlas database has network access allowed for Vercel's IP addresses (or set to allow access from anywhere for testing)
- Verify that all environment variables are set correctly
- Ensure the `vercel.json` configuration is correct
- Check that the server.js file is correctly referenced in your vercel.json
- If you're having CORS issues, ensure your CORS configuration allows requests from your frontend domain

## Important Notes

- Vercel's serverless functions have certain limitations:
  - Maximum execution time of 10 seconds (free plan)
  - Limited memory allocation
  - Cold starts may occur

- To work around these limitations:
  - Optimize database queries
  - Implement caching where possible
  - Consider upgrading to a paid plan for more resources if needed

## Custom Domain (Optional)

To set up a custom domain:
1. Go to your project settings in Vercel
2. Click on "Domains"
3. Add your custom domain and follow the instructions to verify ownership 