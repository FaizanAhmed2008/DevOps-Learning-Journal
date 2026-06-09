# Git Conflict Resolution Commands

- Create a feature branch: `git switch -c feature1`
- Make a change on the feature branch: `echo "feature change" > test.txt`
- Stage and commit the feature change: `git add .` then `git commit -m "feature change"`
- Switch back to main: `git switch main`
- Make a conflicting change on main: `echo "main change" > test.txt`
- Stage and commit the main change: `git add .` then `git commit -m "main change"`
- Merge the feature branch into main: `git merge feature1`
- Resolve conflicts manually, then stage the resolution: `git add .`
- Commit the resolved merge: `git commit`
- Abort the merge if needed: `git merge --abort`  