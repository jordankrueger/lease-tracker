![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-deployed-brightgreen?logo=github)
![Deploy Status](https://img.shields.io/github/deployments/jordankrueger/lease-tracker/github-pages?label=deploy&logo=github)
![PWA Ready](https://img.shields.io/badge/PWA-ready-5A0FC8?logo=pwa)
![No Backend](https://img.shields.io/badge/backend-none-blue)
![License: GPL-3.0](https://img.shields.io/badge/License-GPL%203.0-blue.svg)
![Made with React](https://img.shields.io/badge/React-18-61DAFB?logo=react)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC?logo=tailwindcss)

# Lease Mileage Tracker

A simple, privacy-focused web app to track your car lease mileage. Know exactly how many miles per day you can drive without going over your limit.

**[Click here for a live demo!](https://jordankrueger.github.io/lease-tracker/)**

## Table of Contents
- [Features](#features)
- [Use as a Progressive Web App](#use-as-a-progressive-web-app)
- [Quick Start (GitHub Pages)](#quick-start-github-pages)
- [Custom Domain](#custom-domain-optional)
- [Customizing the Icons](#customizing-the-icons)
- [How It Works](#how-it-works)
- [Development](#development)
- [License](#license)

## Features

- 📊 **Real-time calculations** - See your daily mile allowance based on remaining time and miles
- 🎯 **Pace tracking** - Know if you're ahead or behind your expected usage
- 🔗 **Shareable** - Generate links to share lease terms with others (they track their own mileage)
- 📱 **Installable** - Add to your phone's home screen like a native app
- 🔒 **Private** - All data stays on your device (localStorage), nothing sent to servers
- 🌐 **Works offline** - Service worker caches the app for offline use

## Use as a Progressive Web App

A Progressive Web App (PWA) is a website that can be installed on your phone or computer like a regular app. You don't need to download anything from an app store—just visit the site and add it to your home screen.

Once installed, Lease Tracker:
- Opens in its own window (no browser toolbar)
- Works offline
- Launches from your home screen or dock with its own icon

It's the convenience of a native app without the hassle of app store downloads or updates.

### On iPhone/iPad (Safari)
1. Open your site URL in Safari (not Chrome or another browser—iOS only allows PWA installs from Safari)
2. Tap the Share button (the square with an arrow pointing up)
3. Scroll down and tap "Add to Home Screen"
4. Give it a name (or keep "Lease Tracker") and tap Add

Now it appears on your home screen with its own icon, opens without Safari's browser chrome, and works offline.

### On Mac

#### Safari (macOS Sonoma or later):
1. Open the site in Safari
2. Click File → Add to Dock
3. It now lives in your Dock and opens in its own window

#### Chrome (any macOS version):
1. Open the site in Chrome
2. Click the three-dot menu (top right)
3. Click "Install Lease Mileage Tracker..." or Save and Share → Install
4. It appears in your Applications folder and Launchpad

### Tips
- The app caches itself after first load, so it works even without internet
- Your mileage data stays in that specific browser/install's storage—if you install on both your iPhone and Mac, they'll track separately
- If you ever need to "reset" the PWA, you can delete it and re-add it from the website

## Quick Start (GitHub Pages)

### Step 1: Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name your repository (e.g., `lease-tracker` or `mileage-tracker`)
3. Set it to **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 2: Upload the Files

**Option A: Upload via GitHub Web Interface**

1. On your new repo page, click **"uploading an existing file"** or the **Add file → Upload files** button
2. Drag and drop all files from this folder:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. Click **Commit changes**

**Option B: Use Git Command Line**

```bash
# Clone your new empty repo
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME

# Copy all the app files into this folder, then:
git add .
git commit -m "Initial commit - Lease Tracker app"
git push origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (tab at the top)
3. Scroll down to **Pages** in the left sidebar
4. Under **Source**, select **Deploy from a branch**
5. Under **Branch**, select `main` and `/ (root)`
6. Click **Save**

### Step 4: Access Your App

After a minute or two, your app will be live at:

```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

For example: `https://jordankrueger.github.io/lease-tracker/`

## Custom Domain (Optional)

If you want to use a custom domain like `lease.yourdomain.com`:

1. In your repo, create a file called `CNAME` containing just your domain:
   ```
   lease.yourdomain.com
   ```
2. In your DNS settings, add a CNAME record pointing to `YOUR_USERNAME.github.io`
3. In GitHub Pages settings, enter your custom domain

## Customizing the Icons

The included icons are simple placeholders. To create custom icons:

1. Create a 512x512 PNG image with your design
2. Use a tool like [favicon.io](https://favicon.io/) or [realfavicongenerator.net](https://realfavicongenerator.net/) to generate all sizes
3. Replace `icon-192.png` and `icon-512.png` in your repo

## How It Works

### Data Storage
- Lease configuration and current mileage are stored in your browser's `localStorage`
- Data persists across sessions but is device-specific
- Clearing browser data will reset the app

### Sharing
- The Share button generates a URL with lease parameters (dates, total miles, starting odometer)
- When someone opens a shared link, those values pre-fill the setup form
- Each person's mileage entries stay on their own device

### URL Parameters
You can manually construct URLs with these parameters:
- `start` - Lease start date (YYYY-MM-DD)
- `end` - Lease end date (YYYY-MM-DD)  
- `miles` - Total miles allowed
- `startOdo` - Odometer reading at lease start

Example:
```
https://yoursite.com/?start=2024-01-15&end=2027-01-15&miles=36000&startOdo=15
```

## Development

This is a single-page app with no build step required. To modify:

1. Edit `index.html` - contains all React code inline
2. Test locally by opening `index.html` in a browser (some features like service worker need a local server)
3. For local testing with full PWA features:
   ```bash
   npx serve .
   ```

## License

[GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) - Permissions of this strong copyleft license are conditioned on making available complete source code of licensed works and modifications, which include larger works using a licensed work, under the same license. Copyright and license notices must be preserved. Contributors provide an express grant of patent rights.

---

Built with React, Tailwind CSS, and localStorage. No backend required.
