\# PowerShell 7 Setup Guide



My personal PowerShell 7 environment setup with Oh My Posh and atomic theme.



\## Dependencies \& Installation Steps



\### 1. PowerShell 7

```powershell

winget install Microsoft.PowerShell

```



\### 2. Oh My Posh

```powershell

winget install JanDeDobbeleer.OhMyPosh

```

\*(Or if winget issues: use the direct installer script)\*



\### 3. PSReadLine (for IntelliSense)

```powershell

Install-Module -Name PSReadLine -Force -SkipPublisherCheck

```



\### 4. Nerd Font

```powershell

oh-my-posh font install

```

\*\*Recommended fonts:\*\* CaskaydiaCove NF or BlexMono Nerd Font



\### 5. Set up Profile

```powershell

\# Create profile if it doesn't exist

New-Item -Path $PROFILE -Type File -Force



\# Edit profile

notepad $PROFILE

```



Add this to the profile:

```powershell

\# Set themes path for Oh My Posh

$env:POSH\_THEMES\_PATH = "C:\\Program Files\\WindowsApps\\ohmyposh.cli\_27.6.0.0\_x64\_\_96v55e8n804z4\\themes"

oh-my-posh init pwsh --config "$env:POSH\_THEMES\_PATH\\atomic.omp.json" | Invoke-Expression



\# PSReadLine options for better IntelliSense

Set-PSReadLineOption -PredictionSource History

Set-PSReadLineOption -PredictionViewStyle ListView

Set-PSReadLineOption -EditMode Windows

```



\### 6. Windows Terminal Font Settings

\- Open Windows Terminal Settings (`Ctrl + ,`)

\- Go to PowerShell 7 profile → Appearance

\- Set Font to your installed Nerd Font



\## Notes

\- Theme: \*\*atomic\*\* (retro, minimal, clean)

\- Alternative themes available in `$env:POSH\_THEMES\_PATH`

