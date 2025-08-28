

6. Recovering from Hard Reset with Reflog


Goal: Restore accidentally deleted changes

# Check reflog (Git's safety net)
git reflog

# Output:
# 1a2b3c4 (HEAD -> main) HEAD@{0}: reset: moving to HEAD~1
# 2b3c4d5 HEAD@{1}: commit: Add JavaScript logger
# 4d5e6f7 HEAD@{2}: reset: moving to HEAD~1
# ...

# Restore to the commit before hard reset
git reset --hard 2b3c4d5

# Verify recovery
git log --oneline
# Output:
# * 2b3c4d5 (HEAD -> main) Add JavaScript logger
# * 4d5e6f7 Add blue background
# * 7g8h9i0 Add HTML structure

# Check files
ls
# Output: app.js  index.html  styles.css  # app.js is back!