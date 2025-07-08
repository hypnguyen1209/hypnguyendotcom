# Nguyen Van Hiep - Portfolio Website

A minimalist portfolio website that automatically updates repository star counts and deploys to GitHub Pages.

## 🚀 Features

- **Ultra-minimalist design** - Single-section layout with essential information
- **Auto-updating star counts** - GitHub Actions automatically fetch and update repository stars every 7 days
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

- **`update-stars-and-deploy.yml`** - Runs every 7 days to update star counts and deploy
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
   - Fetches current star counts from GitHub API
   - Updates the HTML file with new star counts
   - Commits changes if any updates were made
   - Deploys the updated site

2. **Manual Updates**: You can manually trigger the workflow from the Actions tab

3. **Push Deployment**: Every push to main/master automatically deploys the site

## 🛠 Customization

To modify the repositories being tracked:

1. Edit the `repos` array in the workflow file
2. Update the corresponding HTML content in `index.html`
3. Adjust the regex patterns in the update script

## 📝 License

© 2025 Nguyen Van Hiep. All rights reserved.
