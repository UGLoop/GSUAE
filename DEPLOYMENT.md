# Deployment Instructions for Golo Consultancy Website

## Step 1: GitHub Setup

### 1.1 Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Repository settings:
   - Repository name: `golo-consultancy-website`
   - Description: "Golo Consultancy - Premium Business Advisory & Marketing Solutions"
   - Make it Public or Private (your choice)
   - DO NOT initialize with README (we already have one)
   - Click "Create repository"

### 1.2 Upload Files to GitHub

#### Option A: Using GitHub Web Interface (Easiest)

1. On your new repository page, click "uploading an existing file"
2. Drag and drop these files:
   - `index.html`
   - `package.json`
   - `vercel.json`
   - `README.md`
   - `.gitignore`
3. Write commit message: "Initial commit - Golo Consultancy website"
4. Click "Commit changes"

#### Option B: Using Git Command Line

```bash
# Navigate to your project folder
cd golo-consultancy-website

# Initialize git
git init

# Add all files
git add .

# Commit files
git commit -m "Initial commit - Golo Consultancy website"

# Add your GitHub repository as origin
git remote add origin https://github.com/YOUR_USERNAME/golo-consultancy-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 2: Vercel Deployment

### 2.1 Create Vercel Account

1. Go to [Vercel.com](https://vercel.com)
2. Click "Sign Up"
3. Choose "Continue with GitHub" (recommended)
4. Authorize Vercel to access your GitHub

### 2.2 Import and Deploy Project

1. Once logged in to Vercel, click "Add New..." → "Project"
2. Click "Import Git Repository"
3. Find and select `golo-consultancy-website` from your repositories
4. Configure your project:
   - Framework Preset: `Other` (or leave as auto-detected)
   - Root Directory: `./` (leave as is)
   - Build Command: (leave empty or `npm run build`)
   - Output Directory: (leave empty)
   - Install Command: `npm install` (or leave as auto)
5. Click "Deploy"
6. Wait for deployment (usually takes 1-2 minutes)

### 2.3 Your Website is Now Live!

After deployment, you'll get a URL like:
- `https://golo-consultancy-website.vercel.app`

## Step 3: Custom Domain Setup (goloconsultancy.com)

### 3.1 Add Domain in Vercel

1. In your Vercel project, go to "Settings" → "Domains"
2. Type `goloconsultancy.com` in the input field
3. Click "Add"
4. Also add `www.goloconsultancy.com` as an alias

### 3.2 Configure DNS Settings

Go to your domain registrar (where you bought goloconsultancy.com) and update DNS:

#### For apex domain (goloconsultancy.com):
- Type: A
- Name: @ (or leave empty)
- Value: 76.76.21.21

#### For www subdomain:
- Type: CNAME
- Name: www
- Value: cname.vercel-dns.com

#### Alternative (if your registrar supports ALIAS/ANAME):
- Type: ALIAS or ANAME
- Name: @ (or leave empty)
- Value: alias.vercel.com

### 3.3 Wait for DNS Propagation

- DNS changes can take 24-48 hours to propagate globally
- Vercel will automatically provision SSL certificates
- You'll see green checkmarks in Vercel when everything is configured

## Step 4: Future Updates

### Making Changes to Your Website

1. Edit the `index.html` file with your changes
2. Commit and push to GitHub:
```bash
git add .
git commit -m "Update: description of changes"
git push
```
3. Vercel will automatically detect changes and redeploy (takes ~1 minute)

### Monitoring Your Site

- **Vercel Dashboard**: Check deployments, analytics, and domains
- **GitHub**: Track code changes and version history
- **Domain Status**: Monitor in Vercel → Settings → Domains

## Troubleshooting

### Common Issues and Solutions

1. **Domain not working after 48 hours**
   - Verify DNS settings with your registrar
   - Check Vercel domain configuration
   - Use [whatsmydns.net](https://www.whatsmydns.net) to check DNS propagation

2. **Deployment failed**
   - Check build logs in Vercel
   - Ensure all files are properly formatted
   - Verify `vercel.json` configuration

3. **SSL Certificate issues**
   - Vercel automatically provisions SSL
   - If issues persist, remove and re-add domain

4. **404 errors on navigation**
   - The `vercel.json` routes configuration should handle this
   - Ensure the configuration is properly uploaded

## Support Resources

- **Vercel Documentation**: https://vercel.com/docs
- **Vercel Support**: https://vercel.com/support
- **GitHub Help**: https://docs.github.com
- **DNS Checker**: https://www.whatsmydns.net

## Quick Commands Reference

```bash
# Local development
npm run dev

# Check git status
git status

# View deployment URL
vercel

# Open Vercel dashboard
vercel dashboard
```

---

**Congratulations!** Your Golo Consultancy website is now deployed and live! 🎉

For any issues or questions, contact: contact@goloconsultancy.com
