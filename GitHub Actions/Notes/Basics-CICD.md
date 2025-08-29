# Basics of CI/CD:
-----------------
## What is CI/CD?
- **CI (Continuous Integration):**  
    The practice of automatically integrating code changes from multiple contributors into a shared repository several times a day. Each integration is verified by automated builds and tests.

- **CD (Continuous Delivery/Deployment):**  
    - **Continuous Delivery:** Automatically prepares code changes for a release to production, but requires manual approval to deploy.
    - **Continuous Deployment:** Automatically releases every change that passes tests to production without manual intervention.

## Key Benefits
- Faster development cycles
- Early detection of bugs
- Consistent and repeatable deployments
- Improved collaboration

## Typical CI/CD Pipeline Steps
1. **Code Commit:** Developers push code to a version control system (e.g., Git).
2. **Build:** The application is built (compiled, packaged).
3. **Test:** Automated tests are run (unit, integration, etc.).
4. **Deploy:** The application is deployed to staging or production environments.
5. **Monitor:** The deployed application is monitored for issues.

## Popular CI/CD Tools
| Category        | Tools                                                   |
|-------------- --|-------------------------------------------------------- |
| Version Control | Git, GitHub, GitLab, Bitbucket                          |
| CI/CD Pipelines | Jenkins, GitHub Actions, GitLab CI, CircleCI, Travis CI |
| Containers      | Docker, Kubernetes                                      |
| Testing         | JUnit, Selenium, PyTest, Cypress                        |
----------------------------------------------------------------------------

## Example Workflow:
```yaml
# Example GitHub Actions workflow
name: CI

on: [push, pull_request]

jobs:
    build:
        runs-on: ubuntu-latest
        steps:
            - uses: actions/checkout@v3
            - name: Set up Node.js
                uses: actions/setup-node@v3
                with:
                    node-version: '18'
            - run: npm install
            - run: npm test
```
---
## 🧪 Example CI/CD Workflow:
1. Developer pushes code to GitHub.
2. GitHub Actions triggers:
   - Code is built.
   - Unit tests run.
   - Code is linted.
3. If successful:
   - Code is deployed to staging.
   - Optional manual approval.
   - Code is deployed to production.
---

