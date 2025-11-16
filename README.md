# AllGround Privacy Policy - GitHub Pages Deployment

This directory contains the privacy policy HTML for the AllGround app, ready to deploy to GitHub Pages.

## Quick Setup (5 minutes)

### Option 1: Create New Repository (Recommended)

1. **Create a new GitHub repository:**
   ```bash
   # Create new repo on GitHub: https://github.com/new
   # Name it: allground-privacy
   # Make it public
   # Don't initialize with README
   ```

2. **Initialize and push this directory:**
   ```bash
   cd gh-pages
   git init
   git add .
   git commit -m "Initial commit: Privacy policy for AllGround app"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/allground-privacy.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Go to repo **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **(root)**
   - Click **Save**

4. **Your privacy policy will be live at:**
   ```
   https://YOUR_USERNAME.github.io/allground-privacy/
   ```

5. **Update app.json:**
   ```json
   {
     "expo": {
       "ios": {
         "config": {
           "usesNonExemptEncryption": false
         }
       },
       "privacyManifests": {
         "NSPrivacyAccessedAPICategoryUserDefaults": {
           "NSPrivacyAccessedAPITypeReasons": ["CA92.1"]
         }
       },
       "privacy": "public",
       "privacyPolicyUrl": "https://YOUR_USERNAME.github.io/allground-privacy/"
     }
   }
   ```

### Option 2: Use Existing AllGround Repo (If Preferred)

If you want to host it in the main AllGround repo:

1. **Copy index.html to docs folder:**
   ```bash
   mkdir -p docs
   cp gh-pages/index.html docs/privacy.html
   ```

2. **Commit and push:**
   ```bash
   git add docs/privacy.html
   git commit -m "Add privacy policy HTML"
   git push origin main
   ```

3. **Enable GitHub Pages:**
   - Repo **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **/docs**
   - Click **Save**

4. **Your privacy policy will be at:**
   ```
   https://YOUR_USERNAME.github.io/AllGround/privacy.html
   ```

## Verify It Works

After deploying, test the URL in your browser to ensure the privacy policy displays correctly.

## Next Steps

1. Update `app.json` with the correct privacy policy URL
2. Update `eas.json` submission config if needed
3. Verify Apple App Store Connect has the correct privacy URL

## Files in This Directory

- `index.html` - Complete privacy policy in HTML format (ready to deploy)
- `README.md` - This file with deployment instructions

## Need Help?

If you have issues with GitHub Pages:
- Check that the repository is public
- Wait 1-2 minutes after enabling Pages for the site to build
- Verify the URL matches the pattern: `https://USERNAME.github.io/REPO_NAME/`
