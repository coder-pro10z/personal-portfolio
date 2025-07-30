# 📦 Deployment Guide: GitHub Pages for Parcel Project

This guide outlines how to deploy your Parcel-built project (e.g., personal portfolio) to GitHub Pages.

---

## 🔧 Prerequisites

- Node.js and npm installed
- Git installed
- Your project pushed to a GitHub repository
- `gh-pages` package installed

```bash
npm install --save-dev gh-pages
````

---

## 📁 Project Structure (Example)

```
/Portfolio_Github1
├── src/
│   └── index.html
├── dist/              ← Auto-generated (do not commit)
├── .parcel-cache/     ← Auto-generated (ignore)
├── .gitignore
├── package.json
├── README.md
└── Deployment.md      ← You're here
```

---

## ⚙️ Update `.gitignore`

Ensure `dist/` and cache folders are ignored:

```
node_modules/
dist/
.parcel-cache/
```

---

## 📦 package.json Scripts

Add or update the following scripts:

```json
"scripts": {
  "start": "parcel",
  "build": "parcel build --public-url /<repo-name>/",
  "deploy": "npm run build && gh-pages -d dist"
}
```

> Replace `<repo-name>` with your GitHub repository name (e.g., `personal-portfolio`).

---

## 🚀 Initial Deployment

1. **Build for production**

   ```bash
   npm run build
   ```

2. **Deploy to GitHub Pages**

   ```bash
   npm run deploy
   ```

3. **Push your main code (optional)**

   ```bash
   git add .
   git commit -m "Prepare for deployment"
   git push origin main
   ```

---

## 🌐 Access Your Site

Visit:

```
https://<your-username>.github.io/<repo-name>/
```

Example:

```
https://praveenkashyap01.github.io/personal-portfolio/
```

---

## 🛠 Troubleshooting

* **404 for CSS/JS/images**
  ✅ Check `--public-url` is correctly set to `/your-repo-name/`

* **Changes not reflecting**
  ✅ Try clearing browser cache or force reload (Ctrl+Shift+R)

* **404 on GitHub Pages**
  ✅ Ensure your GitHub repo is public and `gh-pages` branch exists

---

## 🔄 ➕ Update & Redeploy

After making any updates to your portfolio:

1. **Stage and commit your source code changes** (optional but recommended)

   ```bash
   git add .
   git commit -m "Update content or styling"
   git push origin main
   ```

2. **Build your project again**

   ```bash
   npm run build
   ```

3. **Redeploy to GitHub Pages**

   ```bash
   npm run deploy
   ```

4. ✅ Done! Your live site will reflect the updated content.

---

> Need help with custom domains, Netlify, or Vercel deployment? Just ask!

