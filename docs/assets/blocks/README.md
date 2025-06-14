# Dynamic MIDI Blocks

This directory allows you to add new MIDI processing blocks after deployment on GitHub Pages.

## How to Add New Blocks

1. Build your block as a self-contained JavaScript file using the independent block builder:
   ```bash
   node build-independent-blocks.js --single your-block-name
   ```

2. Upload the generated block file to this directory in your repository:
   ```
   git add dist/assets/blocks/your-block-name.js
   git commit -m "Add new MIDI block"
   git push origin main
   ```

3. The block will be automatically discovered and available in the application.

## Directory Structure

- Each block should be a self-contained .js file
- Blocks are organized by category (system/, note/, processor/, etc.)
- The application scans this directory at runtime for new blocks

## Current Blocks

All blocks that were available at build time are included in the main application bundle.
This directory is for adding NEW blocks after deployment.
