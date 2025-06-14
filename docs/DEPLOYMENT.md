# GitHub Pages Deployment Guide

## Setup Instructions

1. **Repository Setup**:
   - Create a new repository named `midirouter` on GitHub
   - Or use an existing repository with a `/midirouter` path

2. **Build for GitHub Pages**:
   ```bash
   # Run the GitHub Pages build
   node build-github.js
   ```

3. **Deploy Built Files**:
   ```bash
   # Copy all files from dist/ to your repository
   cp -r dist/* /path/to/your/repo/
   
   # Commit and push
   cd /path/to/your/repo/
   git add .
   git commit -m "Deploy MIDI Router (Hybrid Build)"
   git push origin main
   ```

4. **Enable GitHub Pages**:
   - Go to your repository settings
   - Navigate to "Pages" section
   - Select "Deploy from a branch"
   - Choose "main" branch and "/ (root)" folder
   - Save the settings

5. **Access Your App**:
   Your MIDI Router will be available at:
   `https://[username].github.io/midirouter/`

## Build Configuration
- Build type: Hybrid (static bundle + dynamic loading capability)
- Base path: `/midirouter/`
- All current blocks: Included in main bundle
- Dynamic blocks: Supported via assets/blocks/ directory
- GitHub Pages optimized: .nojekyll file included
- Asset organization: Clean structure for hosting

## Adding New Blocks After Deployment
1. Build new blocks using: `node build-independent-blocks.js --single your-block-name`
2. Upload generated .js files to your repository's `dist/assets/blocks/` directory
3. Commit and push changes
4. New blocks will be automatically discovered by the application

## Troubleshooting
- Ensure all files are committed and pushed
- Check GitHub Actions tab for deployment status
- Verify GitHub Pages is enabled in repository settings
- Wait 5-10 minutes for changes to propagate
- Check browser console for any path-related errors

Built on: 2025-06-14T04:08:34.448Z
