# Lease Mileage Tracker

A simple, privacy-focused web app to track your car lease mileage. Know exactly how many miles per day you can drive without going over your limit.

**[Live Demo →](#)** *(Update this link after deploying)*

## Features

- 📊 **Real-time calculations** - See your daily mile allowance based on remaining time and miles
- 🎯 **Pace tracking** - Know if you're ahead or behind your expected usage
- 🔗 **Shareable** - Generate links to share lease terms with others (they track their own mileage)
- 📱 **Installable** - Add to your phone's home screen like a native app
- 🔒 **Private** - All data stays on your device (localStorage), nothing sent to servers
- 🌐 **Works offline** - Service worker caches the app for offline use

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

MIT - Feel free to use, modify, and share.

---

Built with React, Tailwind CSS, and localStorage. No backend required.
