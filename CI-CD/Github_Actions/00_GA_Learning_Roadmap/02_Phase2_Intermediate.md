

## 📘 Phase 2: Intermediate GitHub Actions

### 🎯 Objective

Deepen your understanding of GitHub Actions with advanced techniques like secrets, matrix builds, Docker jobs, and reusable workflows.

---

### 🔐 Using Secrets and Environment Variables

* Store secrets in GitHub repository settings
* Access them using `secrets.MY_SECRET`

```yaml
env:
  API_KEY: ${{ secrets.API_KEY }}
```

---

### 🔄 Matrix Builds (Parallel Testing)

Run the same job across multiple configurations.

```yaml
strategy:
  matrix:
    node: [14, 16, 18]

runs-on: ubuntu-latest
steps:
  - uses: actions/setup-node@v4
    with:
      node-version: ${{ matrix.node }}
```

---

### 🧱 Job Dependencies and Conditions

Run jobs in sequence or based on results:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Build stage"

  deploy:
    runs-on: ubuntu-latest
    needs: build
    if: github.ref == 'refs/heads/main'
    steps:
      - run: echo "Deploying..."
```

---

### 🔁 Reusable Workflows

Separate logic into reusable workflow files:

```yaml
# .github/workflows/main.yml
jobs:
  call-reusable:
    uses: ./.github/workflows/shared.yml
    with:
      name: Vinay
```

```yaml
# .github/workflows/shared.yml
on: workflow_call

jobs:
  say-hello:
    runs-on: ubuntu-latest
    steps:
      - run: echo "Hello ${{ inputs.name }}"
```

---

### 📦 Artifact Uploads & Caching

* **Upload artifacts:**

```yaml
- name: Upload build
  uses: actions/upload-artifact@v4
  with:
    name: app
    path: dist/
```

* **Cache dependencies:**

```yaml
- uses: actions/cache@v4
  with:
    path: ~/.npm
    key: ${{ runner.os }}-npm-${{ hashFiles('**/package-lock.json') }}
    restore-keys: |
      ${{ runner.os }}-npm-
```

---

### 🐳 Using Docker Containers in Jobs

```yaml
jobs:
  docker-test:
    runs-on: ubuntu-latest
    container:
      image: node:18
    steps:
      - run: node --version
```

---

### ☁️ GitHub-Hosted vs Self-Hosted Runners

* **GitHub-hosted**: Free, automatic provisioning
* **Self-hosted**: Use your own VM/server, customize environments

---

### ✅ Summary

You now understand:

* Matrix builds and job dependencies
* Secrets, cache, and artifacts
* Reusable workflows
* Docker containers in Actions

---

