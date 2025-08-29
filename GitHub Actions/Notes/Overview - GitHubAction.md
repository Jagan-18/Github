# What is GitHib Actions:
------------------------
**GitHub Actions** is a CI/CD (Continuous Integration and Continuous Deployment) platform provided by GitHub. It allows you to automate workflows for building, testing, and deploying your code directly from your GitHub repository.

### 🛠️ What It Does GitHub Actions enables you to:
--------------------------------------------------
- **Automate tasks** like building, testing, and deploying code
- **Trigger workflows** on events such as pushes, pull requests, or issue creation
- **Run jobs** on GitHub-hosted or self-hosted runners (Linux, Windows, macOS)

### 📦 Key Components:
----------------------
- **Workflows**: Defined in `.yml` files inside `.github/workflows/`. A workflow is a set of instructions triggered by events.
- **Jobs**: A workflow can have multiple jobs that run in parallel or sequentially.
- **Steps**: Each job consists of steps, which are individual tasks like running a script or installing dependencies.
- **Actions**: Reusable extensions or commands that perform specific tasks. You can use prebuilt ones or write your own.

### 🌐 Use Cases:
- Continuous Integration (CI) and Continuous Deployment (CD)
- Automated testing
- Code linting and formatting
- Deployment to cloud services
- Sending notifications or creating issues

### Example Workflow:
--------------------
```yaml
name: CI

on: [push, pull_request]

jobs:
    build:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v4
            - name: Set up Node.js
                uses: actions/setup-node@v4
                with:
                    node-version: '18'
            - run: npm install
            - run: npm test
```
---
Absolutely! Here's a **detailed explanation of the core components of GitHub Actions**, broken down clearly so you can understand how they work together to automate your development workflows:

---

## ⚙️ Core Components of GitHub Actions:
---------------------------------------
- **Workflows**: Automated procedures defined by YAML files stored in the `.github/workflows` directory. Each workflow is triggered by specific events (like pushes or pull requests).
- **Events**: Specific activities that trigger workflows, such as code pushes, pull requests, or scheduled times.
- **Jobs**: A workflow consists of one or more jobs. Each job runs in a fresh virtual environment (runner) and can execute a series of steps.
- **Steps**: Individual tasks within a job, such as running commands or using actions.
- **Actions**: Reusable extensions that can be included as steps in workflows. Actions can be created by you or shared by the community.
- **Runners**: Servers that execute your jobs. GitHub provides hosted runners, or you can use your own self-hosted runners.

These components work together to automate building, testing, and deploying your code directly from your GitHub repository.
---
### 1. 🧩 **Workflow**
A **workflow** is the top-level automation process. It defines what should happen and when.

- **Defined in**: `.github/workflows/` directory using `.yml` or `.yaml` files
- **Triggered by**: Events like `push`, `pull_request`, `schedule`, or manually
- **Contains**: One or more jobs

**Example:**
```yaml
name: CI Pipeline
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3
```
---
### 2. 🧱 **Job**
A **job** is a group of steps that run on the same virtual machine (runner).

- **Runs on**: A GitHub-hosted or self-hosted runner (e.g., `ubuntu-latest`)
- **Can run**: In parallel or sequentially using `needs`
- **Isolated**: Each job runs in a clean environment unless artifacts are passed

**Example:**
```yaml
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Run tests
        run: npm test
```
---
### 3. 🔨 **Step**
A **step** is an individual task within a job.

- **Executes**: Either a shell command (`run`) or an action (`uses`)
- **Runs sequentially**: Within the job
- **Shares context**: Steps in the same job can share data

**Example:**
```yaml
steps:
  - name: Install dependencies
    run: npm install
  - name: Run tests
    run: npm test
```
---
### 4. 🧰 **Action**
An **action** is a reusable unit of code that performs a specific task.

- **Types**: JavaScript actions or Docker container actions
- **Used via**: `uses:` keyword
- **Source**: GitHub Marketplace or custom-built

**Example:**
```yaml
- name: Checkout code
  uses: actions/checkout@v3

- name: Setup Node.js
  uses: actions/setup-node@v3
  with:
    node-version: '20'
```
---
### 5. 🎯 **Event**
An **event** is what triggers the workflow.

- **Examples**: `push`, `pull_request`, `issue`, `schedule`, `workflow_dispatch`
- **Defined in**: The `on:` field of the workflow

**Example:**
```yaml
on:
  push:
    branches:
      - main
```
---
### 6. 🏃 **Runner**
A **runner** is the server that executes your jobs.

- **GitHub-hosted**: Linux, Windows, macOS
- **Self-hosted**: Your own machine or server
- **Defined in**: `runs-on` field

**Example:**
```yaml
runs-on: ubuntu-latest
```
---

# 🏃‍♂️ Types of Runners in GitHub Actions:
----------------------------------------
## 1. ☁️ **GitHub-Hosted Runners:**
These are **virtual machines provided and managed by GitHub**. They come pre-installed with commonly used tools and are ready to use out of the box.

#### ✅ Features:
- No setup required
- Automatically updated and maintained by GitHub
- Supports multiple operating systems:
  - `ubuntu-latest`
  - `windows-latest`
  - `macos-latest`
- Can run workflows in a VM or Docker container

#### 🧪 Example:
```yaml
runs-on: ubuntu-latest
```
#### 📌 Use When:
- You want quick setup and don’t need custom environments
- You prefer GitHub to manage infrastructure
---
## 2. 🖥️ **Self-Hosted Runners**
These are **machines that you set up and manage yourself**. You install the GitHub Actions runner application on your own hardware or cloud VM.

#### ✅ Features:
- Full control over the environment (OS, tools, hardware)
- Can use specialized hardware (e.g., GPUs, ARM processors)
- Useful for private networks or restricted environments

#### 🧪 Example:
```yaml
runs-on: self-hosted
```
#### 📌 Use When:
- You need custom software or configurations
- You want to avoid GitHub-hosted runner limits
- You require access to internal systems or private networks
---
### 🆚 Comparison Table:


| Feature            | GitHub-hosted Runner                                                         | Self-hosted                                                |
|--------------------|------------------------------------------------------------------------------|------------------------------------------------------------|
| **Hosting**        | Hosted and maintained by GitHub                                              | Runs on your own infrastructure (servers, VMs, cloud, etc.)|
| **Environment**    | Provides a clean virtual machine for every job execution                     | Can run multiple jobs on the same machine                  |
| **Customization**  | Limited to selecting runner type (e.g., Ubuntu, Windows, macOS)              | Full control over environment and installed software       |
| **Cost**           | Included in GitHub subscription with usage limits; extra charges if exceeded | You handle all maintenance and operational costs           |
-------------------------------------------------------------------------------------------------------------------------------------------------------------------

---



