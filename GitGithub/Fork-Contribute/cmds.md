# Fork & Contribute - Commands

## Fork & Clone
```bash
# Clone your forked repository
git clone https://github.com/YOUR-USERNAME/repo-name.git
cd repo-name
```

## Setup Remote Tracking
```bash
# Add upstream (original repo)
git remote add upstream https://github.com/ORIGINAL-OWNER/repo-name.git

# View all remotes
git remote -v
```

## Create & Switch Branch
```bash
# Create and switch to feature branch
git checkout -b feature/my-feature
# OR (newer):
git switch -c feature/my-feature
```

## Sync with Upstream
```bash
# Fetch latest from original repo
git fetch upstream

# Merge upstream changes
git merge upstream/main
# OR rebase:
git rebase upstream/main
```

## Commit & Push
```bash
# Stage and commit changes
git add .
git commit -m "Description of changes"

# Push to your fork
git push origin feature/my-feature
```

## Cleanup After Merge
```bash
# Switch to main and delete branch
git checkout main
git pull upstream main
git branch -d feature/my-feature
git push origin --delete feature/my-feature
```

## Resolve Conflicts
```bash
# During rebase with conflicts
git rebase upstream/main
# Fix conflicts in editor
git add .
git rebase --continue
git push origin feature/my-feature --force
```
