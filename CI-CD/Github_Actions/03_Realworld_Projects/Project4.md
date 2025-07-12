
### 📁 Project 4: Auto Release Generator using GitHub Actions

**🎯 Goal:** Automatically generate GitHub Releases with changelogs when a version tag is pushed.

### 📦 Components

* GitHub version tags (e.g. `v1.0.0`)
* GitHub Releases
* `actions/create-release` or `release-drafter`

---

### 📂 Directory Structure

```
auto-release/
├── .github/
│   └── workflows/
│       └── release.yml
├── CHANGELOG.md
└── src/
    └── main.js
```

---

### 🧾 release.yml

```yaml
name: Create Release

on:
  push:
    tags:
      - 'v*'

jobs:
  release:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Code
      uses: actions/checkout@v3

    - name: Create GitHub Release
      uses: softprops/action-gh-release@v2
      with:
        tag_name: ${{ github.ref_name }}
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

### 🛠️ Setup Instructions

1. Push a tag using:

```bash
git tag v1.0.0
git push origin v1.0.0
```

2. GitHub Actions will trigger and publish the release
3. Use `release-drafter` for automatic changelog generation (optional)

---

### ✅ Expected Output

* Release created in GitHub UI under the **Releases** tab
* Tag and release title auto-filled
* Optional changelog shown if using `release-drafter`

---
