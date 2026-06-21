# GitHub Actions

GitHub Actions is a CI/CD automation service built into GitHub. It lets you run automated workflows when events happen in your repository, like pushes to the `main` branch.

This folder contains GitHub Actions workflows that automate build tasks for web projects.

## Included Workflows

- `Artifacts-and-Caching-for-Next.js-Build.yml`
  - Runs on `push` to `main`
  - Checks out the repo
  - Sets up Node.js
  - Installs dependencies
  - Builds the Next.js project
  - Uploads build artifacts

- `Automate-Angular-Build-Process.yml`
  - Runs on `push` to `main`
  - Checks out the repo
  - Sets up Node.js
  - Installs dependencies
  - Builds the Angular project

## Purpose

These workflows help automate the development process by building projects automatically on every main branch update, so the repository can stay ready for testing and deployment.
