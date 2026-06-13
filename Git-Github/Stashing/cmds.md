# Git Stashing Commands

- Save uncommitted changes to a new stash: `git stash`
- Show all saved stashes: `git stash list`
- Apply the latest stash and remove it: `git stash pop`
- Apply a stash without deleting it: `git stash apply [<stash>]`
- Delete a stash entry: `git stash drop [<stash>]`
- Remove all stashes: `git stash clear`
- Save a stash with a message: `git stash push -m "docker config changes"`