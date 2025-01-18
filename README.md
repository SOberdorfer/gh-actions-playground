# GitHub Actions Workflows Testing Repository

This repository is dedicated to testing various GitHub Actions workflows. It includes multiple workflows for building, testing, and deploying applications using GitHub Actions.

---

## Workflows

### 1. Pull-Request Workflow

The `pull-request` workflow is triggered when a PR is created or a PR is being synced. It starts the building [rwf_build](.github/workflows/rwf_build.yml) and deployment [rwf_deploy](.github/workflows/rwf_deploys.yml) workflow. The idea is that there's a feature-artifact pushed to the artifactory. 

### 2. Release Workflow

The `release` workflow is triggered manually or on a push to the `master` branch. It starts the building [rwf_build](.github/workflows/rwf_build.yml) and deployment [rwf_deploy](.github/workflows/rwf_deploys.yml) workflows. The main/master branch artifact is build, and pushed as a release candidate to the artifactory, which then is pulled in the next step and pushed to the correct environment.

### 3. Reusable Build Workflow

The `rwf_build` workflow is responsible for building the application. It includes steps for checking out the code, setting up Node.js, installing dependencies, linting, testing, and packaging the application.

### 4. Reusable Deploy Workflow

The `rwf_deploy` workflow handles the deployment of the built artifact to the specified environment. It includes steps for checking out the code, pulling the artifact from the artifactory, and deploying it to the target environment.

## Usage

To use these workflows, you can manually trigger the `deploy` workflow or push changes to the `main` branch. The workflows will automatically handle the build and deployment processes.

push to main branch
```bash
---
