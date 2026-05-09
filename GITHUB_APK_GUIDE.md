# 🚀 VidAI — GitHub APK Build Guide

## What This Does
Every time you push code to GitHub, it **automatically builds an APK** you can download and install on your Android phone. No PC Android Studio needed!

---

## STEP 1 — Create a Free Expo Account

1. Go to **https://expo.dev** in your browser
2. Click **Sign Up** (top right)
3. Enter your email + password → Create Account
4. **Verify your email** (check inbox)
5. Stay logged in — you'll need this

---

## STEP 2 — Get Your Expo Token

1. Go to: **https://expo.dev/accounts/[your-username]/settings/access-tokens**
   *(replace [your-username] with your actual Expo username)*
2. Click **Create token**
3. Name it: `github-actions`
4. Click **Create**
5. **Copy the token** (it shows ONCE — save it somewhere!)

---

## STEP 3 — Create a GitHub Repository

1. Go to **https://github.com** and sign in (or create account)
2. Click the **+** icon → **New repository**
3. Name it: `VidAI`
4. Set to **Private** (recommended)
5. Click **Create repository**

---

## STEP 4 — Add Your Expo Token to GitHub Secrets

1. In your GitHub repo, click **Settings** (top tab)
2. On left sidebar → **Secrets and variables** → **Actions**
3. Click **New repository secret**
4. Name: `EXPO_TOKEN`
5. Value: *paste the token you copied in Step 2*
6. Click **Add secret**

---

## STEP 5 — Upload the VidAI Code to GitHub

### Option A: Using GitHub Desktop (Easiest)
1. Download **GitHub Desktop**: https://desktop.github.com
2. Install and sign in with your GitHub account
3. Click **File → Add Local Repository**
4. Select your VidAI folder
5. Click **Publish repository** → select your `VidAI` repo
6. Click **Push origin**

### Option B: Using Command Prompt
```cmd
cd Desktop\VidAI
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/VidAI.git
git push -u origin main
```
*(Replace YOUR_USERNAME with your GitHub username)*

---

## STEP 6 — Watch the Build Run

1. Go to your GitHub repo in browser
2. Click **Actions** tab (top)
3. You'll see **"Build VidAI APK"** running (yellow spinner)
4. Click it to watch the live log
5. Wait **10–20 minutes** for the build to complete

---

## STEP 7 — Download and Install Your APK

1. Once the build shows ✅ green checkmark
2. Click on the completed run
3. Scroll down to **Artifacts**
4. Click **VidAI-APK** to download
5. Transfer the `.apk` file to your phone
6. On your phone: **Settings → Security → Allow Unknown Sources** (or "Install unknown apps")
7. Open the APK file → **Install**
8. Open VidAI and enjoy! 🎉

---

## Rebuilding After Changes

Every time you push new code to the `main` branch, a new APK is built automatically.

You can also trigger a build manually:
1. Go to **Actions** tab
2. Click **"Build VidAI APK"**
3. Click **Run workflow** → **Run workflow**

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Build fails with "EXPO_TOKEN" error | Re-check Step 4 — make sure secret name is exactly `EXPO_TOKEN` |
| "Not logged in" error | Create Expo account and get a fresh token |
| APK installs but crashes | Check that your phone runs Android 8.0+ |
| "Install blocked" on phone | Enable "Install from unknown sources" in phone Settings |

---

## ⚠️ Important Notes

- EAS Build gives you **30 free builds/month** on the free plan
- Each build takes ~10–20 minutes (happens in the cloud, not your PC)
- The APK file will be available for **30 days** before it expires
- This is a **debug/preview APK** — not for the Play Store (that needs more setup)
