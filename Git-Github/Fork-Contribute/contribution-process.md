# Step-by-Step Contribution Process

## 1. Fork the Repository
- Go to GitHub repo
- Click **Fork** button (top-right)
- Select destination (your account)
- Done! You now have a copy

## 2. Clone Your Fork
```bash
git clone https://github.com/YOUR-USERNAME/repo-name.git
cd repo-name
```

## 3. Add Upstream Connection
```bash
git remote add upstream https://github.com/ORIGINAL-OWNER/repo-name.git
git remote -v  # Verify
```

## 4. Create a Branch
```bash
git checkout -b feature/my-contribution
```

**Naming convention:**
- `feature/add-login` - New feature
- `bugfix/fix-crash` - Bug fix
- `docs/update-readme` - Documentation

## 5. Make Changes & Commit
```bash
git add .
git commit -m "Clear description of changes"
```

**Good messages:**
- Start with verb: "Add", "Fix", "Update"
- Reference issues: "Fix #123"

## 6. Sync Before PR (Important!)
```bash
git fetch upstream
git rebase upstream/main
```

## 7. Push to Your Fork
```bash
git push origin feature/my-contribution
```

## 8. Create Pull Request
- Go to GitHub
- Click **Compare & pull request**
- Write clear title and description
- Explain what changed and why
- Submit!

## 9. Address Feedback
Maintainers request changes:
```bash
# Make updates on same branch
git add .
git commit -m "Address review feedback"
git push origin feature/my-contribution
# PR updates automatically
```

## 10. After Merge - Cleanup
```bash
git checkout main
git pull upstream main
git branch -d feature/my-contribution
git push origin --delete feature/my-contribution
```

## Summary
```
Fork → Clone → Branch → Code → Commit → Push → PR → Review → Merge → Cleanup
```
