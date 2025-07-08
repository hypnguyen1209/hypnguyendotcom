# Nguyen Van Hiep - Portfolio Website

A minimalist portfolio website that automatically updates repository star counts and deploys to GitHub Pages.

## 🚀 Features

- **Ultra-minimalist design** - Single-section layout with essential information
- **Auto-updating stats** - GitHub Actions automatically fetch and update user stats (repos/followers) and repository stars every 7 days
- **Dynamic repository tracking** - Automatically detects and tracks any GitHub repositories linked in your projects section
- **Automated deployment** - Deploys to GitHub Pages on every push
- **Responsive design** - Works on all device sizes

## 🔧 Setup Instructions

### 1. Repository Setup

1. Create a new repository on GitHub
2. Push this code to your repository
3. Go to repository Settings → Pages
4. Set Source to "GitHub Actions"

### 2. GitHub Actions Setup

The repository includes two workflows:

- **`update-stars-and-deploy.yml`** - Runs every 7 days to update user stats, repository star counts, and deploy
- **`deploy.yml`** - Deploys on every push to main/master branch

### 3. Custom Domain (Optional)

To use a custom domain like `https://hypnguyen.com`:

1. Add a `CNAME` file to the repository root with your domain:
   ```
   hypnguyen.com
   ```

2. Configure your domain's DNS:
   - Add a CNAME record pointing to `your-username.github.io`
   - Or add A records pointing to GitHub's IP addresses:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```

3. In repository Settings → Pages → Custom domain, enter your domain

### 4. Repository Permissions

Ensure the GitHub Actions have proper permissions:
- Go to Settings → Actions → General
- Set "Workflow permissions" to "Read and write permissions"

## 📁 File Structure

```
.
├── .github/
│   └── workflows/
│       ├── update-stars-and-deploy.yml
│       └── deploy.yml
├── index.html          # Main HTML file
├── style.css           # Minimalist styles
└── README.md           # This file
```

## 🔄 How It Works

1. **Scheduled Updates**: Every Sunday at midnight UTC, GitHub Actions:
   - Fetches current user statistics (total repos and followers)
   - Updates the stats section with current numbers
   - Scans for all GitHub repository links in the projects section
   - Fetches current star counts from GitHub API for each repository
   - Updates existing star counts or adds star counts to repositories that have them
   - Commits changes if any updates were made
   - Deploys the updated site

2. **Manual Updates**: You can manually trigger the workflow from the Actions tab

3. **Push Deployment**: Every push to main/master automatically deploys the site

## 🛠 Customization

The workflow automatically detects and tracks any GitHub repositories you link to in your projects section. To modify what gets tracked:

1. **Add/Remove repositories**: Simply edit the repository links in the `<div class="projects">` section of `index.html`
2. **The workflow automatically adapts**: No need to manually update the workflow file
3. **User stats**: Automatically tracks `hypnguyen1209` - change the username in the workflow if needed

## 📝 License

© 2025 Nguyen Van Hiep. All rights reserved.
