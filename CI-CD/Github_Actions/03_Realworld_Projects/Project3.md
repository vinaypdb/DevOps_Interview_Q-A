

### 📁 Project 3: Deploy Static Site to GitHub Pages

**🎯 Goal:** Automatically deploy a static website (e.g. React, HTML, Vue) to GitHub Pages on every push.

### 📦 Components

* Static website (React, HTML, Vue, etc.)
* GitHub Actions Workflow
* `gh-pages` branch for deployment

---

### 📂 Directory Structure

```
static-site/
├── .github/
│   └── workflows/
│       └── gh-pages-deploy.yml
├── dist/
│   └── index.html
├── package.json
└── README.md
```

---

### 🧾 gh-pages-deploy.yml

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v3

    - name: Install Dependencies
      run: |
        npm install
        npm run build

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v4
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./dist
```

---

### 🛠️ Setup Instructions

1. Ensure your static build outputs to a `dist/` directory
2. Configure your app’s `package.json` with a build script
3. Add the workflow to `.github/workflows/`
4. Push code to `main` to trigger deployment
5. GitHub Pages will deploy from `gh-pages` branch automatically

---

### ✅ Expected Output

* Site is built and deployed to `gh-pages` branch
* Live at: `https://yourusername.github.io/repo-name`

---

