# GitLab Basic Commands

## Clone a GitLab repo
```bash
git clone https://gitlab.com/YOUR-USERNAME/your-project.git
cd your-project
```

## Check status and history
```bash
git status
git diff
git log --oneline
```

## Create and switch branches
```bash
git branch feature/my-change
git switch feature/my-change
# older git versions
# git checkout -b feature/my-change
```

## Stage and commit changes
```bash
git add .
git commit -m "Add feature description"
```

## Push work to GitLab
```bash
git push -u origin feature/my-change
```

## Sync with main
```bash
git fetch origin
git switch main
git pull origin main
git switch feature/my-change
git merge main
```

## Prepare for merge request
```bash
git push origin feature/my-change
# Then open a merge request in GitLab
```

## Review and cleanup
```bash
git switch main
git pull origin main
git branch -d feature/my-change
```
