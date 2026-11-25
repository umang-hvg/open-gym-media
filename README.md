# 🏋️‍♂️ Open Gym Media Library (`open-gym-media`)

> Public CDN-hosted exercise animations, static preview illustrations, and catalog metadata for the **Open Gym** platform and mobile applications.
> [![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
> [![CDN: jsDelivr](https://img.shields.io/badge/CDN-jsDelivr-orange.svg)](https://www.jsdelivr.com/)

## [![Asset Count](https://img.shields.io/badge/Exercises-6%2C550%2B-brightgreen.svg)]()

## 🎯 Purpose

In the Open Gym mobile app, embedding thousands of high-definition animations and exercise figures would result in an APK / app bundle size of **~250 MB**.
By hosting these media files in this dedicated public repository and serving them via a global edge **CDN (jsDelivr)**:

- ⚡ **Mobile APK size is reduced from ~250MB to < 15MB.**
- 🚀 **Fast on-demand streaming and caching** (only exercises viewed by the athlete are downloaded and cached).
- 🔄 **Independent media updates** without needing to recompile or redeploy the mobile app.

---

## 📁 Repository Structure

```text
open-gym-media/
├── clips/         # ~6,550 looping MP4 exercise demonstration animations (~20-50 KB each)
├── still/         # ~6,550 static WebP exercise preview illustrations (~5 KB each)
├── exercises/     # ~6,550 JSON metadata files detailing anatomy, muscles, and instructions
├── .gitignore     # Ignores system junk (.DS_Store, Thumbs.db)
└── README.md      # Repository documentation
```

### File Naming Convention

Every asset is indexed by its 4-digit exercise ID (e.g. `0001`, `0025`, `2476`):

- **Stills:** `still/<id>.webp` (e.g. `still/0001.webp`)
- **Animations / Clips:** `clips/<id>.mp4` (e.g. `clips/0001.mp4`)
- **Metadata:** `exercises/<id>.json` (e.g. `exercises/0001.json`)

---

## 🌐 CDN Access (jsDelivr)

Because this repository is public, all files are automatically available via the free, high-speed **jsDelivr CDN** (backed by Cloudflare & Fastly edge servers worldwide).

> Replace `<YOUR_GITHUB_USERNAME>` with your GitHub username:

### 1. Exercise Preview Stills (WebP)

```text
https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/still/{id}.webp
```

_Example:_ `https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/still/0001.webp`

### 2. Exercise Animation Clips (MP4)

```text
https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/clips/{id}.mp4
```

_Example:_ `https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/clips/0001.mp4`

### 3. Exercise Definition JSON

```text
https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/exercises/{id}.json
```

## _Example:_ `https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/exercises/0001.json`

## 📲 How to Connect with Open Gym Mobile App

In your Open Gym mobile app project (`dashboard/mobile-app/frontend`), update your environment file:

### In `.env.production` (or `.env`):

```env
VITE_IMG_BASE=https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/still/
VITE_GIF_BASE=https://cdn.jsdelivr.net/gh/<YOUR_GITHUB_USERNAME>/open-gym-media@main/clips/
```

> **Note:** Keep the trailing slash `/` at the end of both URLs.

---

## 🚀 Quick Start: Pushing to GitHub

Run these commands inside your `open-gym-media` folder:

```bash
# 1. Add all files to git
git add .
# 2. Commit the media library
git commit -m "feat: initial commit of exercise media library (clips, stills, exercises)"
# 3. Rename branch to main
git branch -M main
# 4. Add your GitHub remote repository (Replace with your GitHub repo URL)
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/open-gym-media.git
# 5. Push to GitHub
git push -u origin main
```

---

## ⚡ Performance & Bandwidth

- **Average static image size:** ~5 KB
- **Average animation clip size:** ~35 KB
- **No Git LFS Required:** Every file is well below GitHub's 100MB limit and jsDelivr's 20MB limit.
- **Global CDN Caching:** Assets are cached indefinitely on edge nodes worldwide for ultra-low latency.

---

## 📜 License

This asset library is part of the **Open Gym** open-source ecosystem.
