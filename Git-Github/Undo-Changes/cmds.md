# Git Undo Commands

- Unstage a file: `git restore --staged file.txt`
- Discard working directory changes: `git restore file.txt`
- Reset the last commit but keep changes staged: `git reset --soft HEAD~1`
- Reset the last commit and keep changes unstaged: `git reset --mixed HEAD~1`
- Reset the last commit and discard all changes: `git reset --hard HEAD~1`
- Revert the last commit with a new commit: `git revert HEAD`
- Restore all working tree files to the last commit: `git restore .`
- Show recent HEAD changes and recover lost refs: `git reflog`