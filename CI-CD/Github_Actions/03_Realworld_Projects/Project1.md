

### 📁 Project 1: CI Pipeline for a Node.js App

**🎯 Goal:** Set up a complete CI workflow for a Node.js app to install dependencies, run linting and tests, and upload test reports.

### 📦 Components

* Node.js app (Express or similar)
* Jest for testing
* GitHub Actions workflow with matrix testing

---

### 📂 Directory Structure

```
nodejs-ci/
├── .github/
│   └── workflows/
│       └── ci.yml
├── package.json
├── app.js
└── tests/
    └── app.test.js
```

---

### 🧾 ci.yml

```yaml
name: Node.js CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [14, 16, 18]

    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v4
      with:
        node-version: ${{ matrix.node-version }}

    - run: npm ci
    - run: npm run lint
    - run: npm test

    - name: Upload test results
      if: always()
      uses: actions/upload-artifact@v4
      with:
        name: test-results
        path: test-results/
```

---

### 🛠️ Setup Instructions

1. Create `.github/workflows/ci.yml` in your repo
2. Add scripts in `package.json`:

```json
"scripts": {
  "lint": "eslint .",
  "test": "jest --coverage"
}
```

3. Push changes to GitHub and observe workflow in the **Actions** tab

---

### ✅ Expected Output

* Workflow triggers on push/PR
* Runs across multiple Node.js versions
* Lints, tests, and uploads results
* View results in GitHub UI

---

