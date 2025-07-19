# GitHub Repository Setup Instructions

Follow these steps to push the monorepo to GitHub:

## 1. Create the Repository on GitHub

1. Go to https://github.com/new
2. Repository name: `zenmind-financial-assistant`
3. Description: "WhatsApp-based financial assistant platform"
4. Set as **Private** (or Public if you prefer)
5. **DO NOT** initialize with README, .gitignore, or license
6. Click "Create repository"

## 2. Push the Local Repository

After creating the empty repository on GitHub, run these commands:

```bash
cd "/Users/jose.lyra/Desktop/Code/Cursor Claude/Financial Assistant"

# Add the remote origin (replace 'yourusername' with your GitHub username)
git remote add origin https://github.com/yourusername/zenmind-financial-assistant.git

# Push the main branch
git push -u origin main

# Initialize and update submodules
git submodule update --init --recursive
```

## 3. Update the Repository URL in package.json

After creating the repository, update the package.json file:

```json
"repository": {
  "type": "git",
  "url": "https://github.com/yourusername/zenmind-financial-assistant.git"
}
```

## 4. Working with Submodules

When team members clone the repository, they should use:

```bash
# Clone with submodules
git clone --recurse-submodules https://github.com/yourusername/zenmind-financial-assistant.git

# Or if already cloned without submodules
git submodule update --init --recursive
```

## 5. Important Notes

- The `zenmind-website` and `whatsapp-integration` directories are git submodules
- They maintain their own separate repositories and git history
- Changes to submodules need to be committed in both the submodule and the parent repository
- Make sure team members have access to all three repositories:
  - Main monorepo: `zenmind-financial-assistant`
  - Submodule: `zenmind-website`
  - Submodule: `whatsapp-integration`

## 6. Alternative: Convert to a True Monorepo (Optional)

If you prefer NOT to use submodules and want everything in a single repository:

1. Remove the submodules:
   ```bash
   git submodule deinit -f zenmind-website
   git submodule deinit -f whatsapp-integration
   git rm -f zenmind-website
   git rm -f whatsapp-integration
   rm -rf .git/modules/zenmind-website
   rm -rf .git/modules/whatsapp-integration
   ```

2. Copy the directories without .git:
   ```bash
   cp -r zenmind-website temp-website
   cp -r whatsapp-integration temp-whatsapp
   rm -rf temp-website/.git
   rm -rf temp-whatsapp/.git
   mv temp-website zenmind-website
   mv temp-whatsapp whatsapp-integration
   ```

3. Add and commit:
   ```bash
   git add .
   git commit -m "Convert from submodules to monorepo"
   ```

This would lose the individual git histories but simplify the repository structure.