# GitHub Metrics Setup Guide

This guide will help you set up GitHub Metrics to generate beautiful visualizations of your GitHub activity, just like the example you saw!

## Prerequisites

- A GitHub account
- Your profile repository (username/username)
- Admin access to your repository

## Setup Steps

### 1. Create a Personal Access Token

1. Go to GitHub Settings: https://github.com/settings/tokens
2. Click **"Generate new token (classic)"**
3. Give it a name like "GitHub Metrics"
4. Set expiration (recommended: 90 days or No expiration)
5. Select the following scopes:
   - ✅ `repo` (all)
   - ✅ `user` (all)
   - ✅ `read:org`
6. Click **"Generate token"**
7. **IMPORTANT:** Copy the token immediately (you won't see it again!)

### 2. Add Token to Repository Secrets

1. Go to your profile repository: `https://github.com/Devaaldo/Devaaldo`
2. Click **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Name: `METRICS_TOKEN`
5. Value: Paste your token from step 1
6. Click **"Add secret"**

### 3. Upload Workflow File

The workflow file has already been created at `.github/workflows/metrics.yml`

You need to:
1. Commit and push this file to your repository
2. Make sure it's in the correct path: `.github/workflows/metrics.yml`

### 4. Enable GitHub Actions

1. Go to your repository
2. Click the **"Actions"** tab
3. If prompted, click **"I understand my workflows, go ahead and enable them"**

### 5. Run the Workflow

1. Go to **Actions** tab
2. Click on **"GitHub Metrics"** workflow
3. Click **"Run workflow"** → **"Run workflow"** (green button)
4. Wait 2-5 minutes for it to complete

### 6. Verify Metrics Generated

After the workflow completes:
1. Go to your repository root
2. You should see new SVG files:
   - `metrics.classic.svg`
   - `metrics.plugin.isocalendar.fullyear.svg`
   - `metrics.plugin.languages.svg`
   - `metrics.plugin.habits.svg`
   - `metrics.plugin.achievements.svg`
   - `metrics.plugin.notable.svg`
   - And more!

### 7. Commit Changes

The README has been updated to display these metrics. You need to:
```bash
git add .
git commit -m "Add GitHub Metrics with AI/Backend focus"
git push
```

## Metrics Included

Your setup includes the following metrics:

| Metric | Description |
|--------|-------------|
| **Classic** | Overall GitHub statistics and activity |
| **Full-year Calendar** | Your contribution calendar for the entire year |
| **Languages** | Most used programming languages (Python, JavaScript, etc.) |
| **Coding Habits** | When you code, recent facts, and charts |
| **Achievements** | GitHub achievements and milestones |
| **Notable Contributions** | Highlighted repositories and contributions |
| **Recent Activity** | Latest GitHub activities |
| **Code Snippet** | Random code snippets from your repos |

## Automated Updates

The metrics will automatically update:
- **Daily at midnight** (Asia/Jakarta timezone)
- **On every push** to main/master branch
- **Manually** via "Run workflow" button

## Optional: Add WakaTime Integration

If you use [WakaTime](https://wakatime.com/) to track coding time:

1. Get your WakaTime API key from https://wakatime.com/settings/account
2. Add it as a repository secret named `WAKATIME_TOKEN`
3. Uncomment the WakaTime section in `.github/workflows/metrics.yml`

## Customization

You can customize your metrics by editing `.github/workflows/metrics.yml`:

- Add more plugins from: https://github.com/lowlighter/metrics#-plugins
- Change colors, layouts, and themes
- Adjust update frequency
- Add/remove specific metrics

## Troubleshooting

### Workflow fails with "Error 403"
- Check that your `METRICS_TOKEN` has correct permissions
- Regenerate token with proper scopes

### SVG files not showing in README
- Make sure the workflow has run successfully
- Check that SVG files exist in repository root
- Wait a few minutes for GitHub to cache images

### Metrics not updating
- Check Actions tab for errors
- Verify workflow file is in correct location
- Ensure Actions are enabled in repository settings

## Resources

- [GitHub Metrics Documentation](https://github.com/lowlighter/metrics)
- [Available Plugins](https://github.com/lowlighter/metrics#-plugins)
- [Configuration Options](https://github.com/lowlighter/metrics/blob/master/source/plugins/README.md)

---

**Your backup README is saved as:** `README.backup.md`

If anything goes wrong, you can always restore from the backup!
