# Development Environment Setup

Development environment setup on Windows with PowerShell 7, Oh My Posh, Git, and GitHub CLI.

**GitHub:** vult-systems  
**Repos Location:** C:\repos

## Git & GitHub Setup

### 1. Install Git
```powershell
winget install Git.Git
```

### 2. Configure Git
```powershell
git config --global user.name "vult-systems"
git config --global user.email "ops.vult@gmail.com"
```

### 3. Install GitHub CLI
```powershell
winget install GitHub.cli
```

### 4. Authenticate with GitHub
```powershell
gh auth login
```

### 5. Create a New Repository
```powershell
cd C:\repos
mkdir new-repo-name
cd new-repo-name

git init
notepad README.md

git add .
git commit -m "Initial commit"
gh repo create new-repo-name --public --source=. --remote=origin --push
```

## PowerShell 7 Setup

### 1. Install PowerShell 7
```powershell
winget install Microsoft.PowerShell
```

### 2. Install Oh My Posh
```powershell
winget install JanDeDobbeleer.OhMyPosh
```

### 3. Install PSReadLine
```powershell
Install-Module -Name PSReadLine -Force -SkipPublisherCheck
```

### 4. Install Nerd Font
```powershell
oh-my-posh font install
```
Pick: CaskaydiaCove NF or BlexMono Nerd Font

### 5. Set up Profile
```powershell
New-Item -Path $PROFILE -Type File -Force
notepad $PROFILE
```

Add this:
```powershell
$env:POSH_THEMES_PATH = "C:\Program Files\WindowsApps\ohmyposh.cli_27.6.0.0_x64__96v55e8n804z4\themes"
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\atomic.omp.json" | Invoke-Expression

Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows
```

### 6. Windows Terminal Font
- Ctrl + , for Settings
- PowerShell 7 → Appearance
- Font: CaskaydiaCove NF

## Clone and Edit Existing Repository

### Clone a repo
```powershell
cd C:\repos
gh repo clone vult-systems/repo-name
cd repo-name
```

Or with HTTPS:
```powershell
cd C:\repos
git clone https://github.com/vult-systems/repo-name.git
cd repo-name
```

### Make changes and push
```powershell
# Edit files
notepad README.md

# Check what changed
git status

# Add, commit, and push
git add .
git commit -m "Updated documentation"
git push
```

### View repo on GitHub
```powershell
gh repo view --web
```

## Daily Git Commands
```powershell
git status                      # Check what changed
git add .                       # Stage all changes
git commit -m "message"         # Commit with message
git push                        # Push to GitHub
git pull                        # Pull latest changes
```