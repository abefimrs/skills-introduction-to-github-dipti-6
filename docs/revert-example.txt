# Create new project
mkdir git-revert-demo && cd git-revert-demo
git init

# Commit 1: Initial config
echo '{"port": 3000}' > config.json
git add config.json
git commit -m "Add initial config"

# Commit 2: Add debug mode (VULNERABILITY!)
echo '{"port": 3000, "debug": true}' > config.json
git add config.json
git commit -m "Enable debug mode"

# Commit 3: Add SSL support
echo '{"port": 3000, "debug": true, "ssl": true}' > config.json
git add config.json
git commit -m "Add SSL support"


2. Identify Problem Commit

git log --oneline


3. Revert the Vulnerable Commit
git revert e6f7g8h

4. Verify the Result
cat config.json
git log --oneline
