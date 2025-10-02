# 🔧 GitHub Pages Setup & Troubleshooting Guide

## 📋 Step-by-Step GitHub Pages Setup

### 1. Enable GitHub Pages

1. **Go to your repository**: https://github.com/dhblue616/wephoneshop-analysis
2. **Click on "Settings"** tab (top navigation)
3. **Scroll down to "Pages"** in the left sidebar
4. **Configure Source**:
   - Source: Select **"GitHub Actions"**
   - This will use our custom workflow file

### 2. Verify Repository Settings

Make sure your repository is:
- ✅ **Public** (GitHub Pages is free for public repos)
- ✅ Has the correct files in the main branch
- ✅ Contains the `.github/workflows/deploy.yml` file

### 3. Manual Trigger (if needed)

If the workflow doesn't trigger automatically:
1. Go to **"Actions"** tab in your repository
2. Click on **"Deploy to GitHub Pages"** workflow
3. Click **"Run workflow"** button
4. Select **"main"** branch and click **"Run workflow"**

---

## 🚨 Common Issues & Solutions

### Issue 1: "There isn't a GitHub Pages site here"

**Possible Causes:**
- GitHub Pages not enabled
- Workflow hasn't run yet
- Repository is private
- Wrong branch selected

**Solutions:**
1. **Check Pages Settings**:
   - Go to Settings > Pages
   - Ensure Source is set to "GitHub Actions"

2. **Check Workflow Status**:
   - Go to Actions tab
   - Look for "Deploy to GitHub Pages" workflow
   - Check if it completed successfully

3. **Repository Visibility**:
   - Ensure repository is public
   - Private repos need GitHub Pro for Pages

### Issue 2: Workflow Fails

**Check these common issues:**

1. **Permissions Error**:
   ```
   Error: Resource not accessible by integration
   ```
   **Solution**: Go to Settings > Actions > General > Workflow permissions
   - Select "Read and write permissions"
   - Check "Allow GitHub Actions to create and approve pull requests"

2. **Pages Not Enabled**:
   ```
   Error: Pages is not enabled for this repository
   ```
   **Solution**: Enable Pages in Settings > Pages first

3. **Branch Protection**:
   - Ensure main branch allows Actions to push

### Issue 3: 404 Error on Site

**Possible Causes:**
- Wrong file path
- Case sensitivity issues
- Missing index.html

**Solutions:**
1. **Check File Names**:
   - Ensure `01.html` exists in root directory
   - Check for typos in file names

2. **Use Correct URLs**:
   - Main site: `https://dhblue616.github.io/wephoneshop-analysis/`
   - Direct access: `https://dhblue616.github.io/wephoneshop-analysis/01.html`

3. **Index File**:
   - We've created `index.html` that redirects to `01.html`
   - This ensures the root URL works

---

## 🔍 Debugging Steps

### 1. Check Workflow Logs

1. Go to **Actions** tab
2. Click on the latest workflow run
3. Expand each step to see detailed logs
4. Look for error messages in red

### 2. Verify File Structure

Your repository should have:
```
├── .github/
│   └── workflows/
│       └── deploy.yml
├── index.html          # ← New redirect file
├── 01.html             # ← Main content
├── README.md
└── other files...
```

### 3. Test Locally

Before deploying, test locally:
```bash
# Start local server
python -m http.server 8080
# or
npx http-server . -p 8080

# Test URLs:
# http://localhost:8080/
# http://localhost:8080/01.html
```

---

## ⚡ Quick Fix Commands

If you need to update and redeploy:

```bash
# Add the new index.html file
git add index.html

# Commit changes
git commit -m "Add index.html redirect page"

# Push to trigger deployment
git push origin main
```

---

## 📞 Expected Results

After successful setup:

1. **Main URL**: https://dhblue616.github.io/wephoneshop-analysis/
   - Should redirect to the analysis report

2. **Direct URL**: https://dhblue616.github.io/wephoneshop-analysis/01.html
   - Should show the full WEPhoneShop analysis

3. **Deployment Time**: Usually 2-5 minutes after push

---

## 🎯 Success Indicators

✅ **Green checkmark** in Actions tab
✅ **Pages build and deployment** workflow completed
✅ **Site accessible** at the GitHub Pages URL
✅ **Content displays** correctly with all styles and charts

---

## 📧 Still Having Issues?

If you're still experiencing problems:

1. **Check GitHub Status**: https://www.githubstatus.com/
2. **Repository Settings**: Ensure all permissions are correct
3. **Wait Time**: Sometimes it takes up to 10 minutes for changes to propagate
4. **Clear Browser Cache**: Try accessing in incognito/private mode

The site should be live at: **https://dhblue616.github.io/wephoneshop-analysis/**