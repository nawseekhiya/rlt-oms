# 🌿 Branching Strategy – Real-Time Order Management System

This document outlines the branching strategy used in this project for clean collaboration, maintainability, and CI/CD integration.

---

## 🔀 Core Branches

| Branch  | Purpose                                  |
|---------|-------------------------------------------|
| `main`  | Production-ready, stable, deployable code |
| `dev`   | Integration branch for merging all features before main release |

All feature branches are created off `dev` and merged back into `dev` after completion.

---

## 🧱 Feature Branch Naming Convention

We follow this convention for all working branches:

```
<type>/<domain>/<task>
````

### Naming Prefixes

| Type         | When to use it                                | Example                           |
|--------------|-----------------------------------------------|-----------------------------------|
| `feat/`      | For new features                              | `feat/frontend/ui-dashboard`      |
| `fix/`       | For bug fixes                                 | `fix/frontend/form-validation`    |
| `chore/`     | For setup, tooling, and non-feature tasks     | `chore/project/init-structure`    |
| `docs/`      | For documentation-only changes                | `docs/readme/aws-setup`           |
| `refactor/`  | For internal improvements, no behavior change | `refactor/backend/order-model`    |
| `ci/`        | For CI/CD configurations                      | `ci/github/deploy-pipeline`       |

---

## ✅ Current Working Branches

| Branch                         | Purpose                                      |
|--------------------------------|----------------------------------------------|
| `feat/backend/api-orders`      | Implement core API endpoints (CRUD)          |
| `feat/backend/aws-services`    | Integrate AWS S3, DynamoDB, and SNS          |
| `feat/frontend/ui-dashboard`   | Build dashboard view with order table        |
| `feat/frontend/form-create`    | Create Order page with PDF upload support    |
| `ci/github/deploy-pipeline`    | Set up GitHub Actions for CI/CD deployment   |
| `chore/project/init-structure` | Initialize base folder structure and configs |

---

## 🔁 Workflow

1. Create a feature branch off `dev`
   ```
   git checkout dev
   git checkout -b feat/backend/api-orders
   ```

2. Work, commit changes, push to origin

   ```
   git add .
   git commit -m "feat: add order creation and listing APIs"
   git push origin feat/backend/api-orders
   ```

3. Open a Pull Request into `dev`

4. After `dev` is verified and tested, merge into `main` for production

---

## 🛡 Branch Protection (Suggested)

* Protect `main` from direct push
* Allow PRs only for merging into `main` or `dev`
* Enable status checks (e.g. CI must pass)

---

## 📎 Notes

* Branches like `fix/*` or `refactor/*` may be created only when needed.
* Stick to [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for clear commit messages:

  * `feat: create order form`
  * `fix: resolve invoice download bug`
  * `chore: update .env template`

---

## 📄 Reference

This strategy is based on conventional commit naming and domain-scoped prefixes for full-stack clarity.