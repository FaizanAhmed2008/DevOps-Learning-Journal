# Vercel Introduction & Deployment

## What is Vercel?
- Cloud platform for hosting static websites, frontend frameworks (Next.js, React, Vue, Svelte), and Serverless Functions.
- Created by the team behind **Next.js**, optimized for speed and developer experience.

## Key Features
- **Zero Config Builds**: Automatically detects your framework and configures build settings.
- **Git Integration**: Automatically builds & deploys on every `git push` (GitHub, GitLab, Bitbucket).
- **Preview Deployments**: Generates a unique preview URL for every branch or Pull/Merge Request.
- **Edge Network & Global CDN**: Serves content from edge locations worldwide for minimal latency.
- **Automatic HTTPS/SSL**: Free SSL certificates provisioned automatically for custom domains.

## Vercel CLI Commands

### 1. Installation & Login
- Install Vercel CLI globally:
  - `npm i -g vercel`
- Log in to your Vercel account:
  - `vercel login`

### 2. Deploying Projects
- Deploy preview build (from project directory):
  - `vercel`
- Deploy to Production:
  - `vercel --prod`
- View project deployment status:
  - `vercel status`
- Manage environment variables:
  - `vercel env pull .env.local`

## Notes
- **Production Branch**: Default target branch is usually `main` or `master`.
- **Serverless Functions**: Place API routes inside `/api` directory for automatic serverless endpoint creation.
