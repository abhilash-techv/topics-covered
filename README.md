# Learning Topics Website

Site built for Abhilash — displays learning topics & subtopics from the workbook.

## Overview

This is a static React application that visualizes learning topics from an Excel workbook (`Learning Time Frame.xlsx`). It features:
- **Search**: Filter topics and subtopics instantly.
- **Responsive Design**: Works on desktop and mobile.
- **Dark Mode**: Toggle between light and dark themes.
- **Data Driven**: Content is generated directly from the Excel file.

## Setup & Installation

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Update Data**
   If you modify `Learning Time Frame.xlsx`, run this command to regenerate the website data:
   ```bash
   node scripts/load_data.js
   ```

3. **Run Locally**
   ```bash
   npm run dev
   ```

## Deployment to GitHub Pages

This project is ready for GitHub Pages.

### Option 1: Manual Deploy (easiest)

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Commit and Push**
   Ensure all changes are committed and pushed to GitHub.

3. **Deploy**
   You can use the `gh-pages` package (already configured if you add the script) or simply:
   - Go to your GitHub Repository Settings -> Pages.
   - Select `gh-pages` branch (if you use a deploy script) or `main` / `docs` folder if configured manually.
   
   **Recommended Workflow:**
   
   Add a deploy script to `package.json`:
   ```json
   "scripts": {
     "predeploy": "npm run build",
     "deploy": "gh-pages -d dist"
   }
   ```
   
   Then run:
   ```bash
   npm install -D gh-pages
   npm run deploy
   ```

### Option 2: GitHub Actions

Push to `main`. If you have a workflow set up, it will deploy automatically.

## Project Structure

- `src/data/topics.json`: Generated data file.
- `scripts/load_data.js`: Script to parse Excel.
- `src/components`: UI components.
- `Learning Time Frame.xlsx`: Source of truth.

## Notes

- The app assumes the Excel file has sheets named "Main Topics" and "Sub Topics".
- Columns used: `Topic`, `Documentation`, `Sub-Topics`, `Parent Topic`.
