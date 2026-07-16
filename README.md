# gh-bootstrap-repo

GitHub CLI extension to bootstrap BigTech+ repositories (labels, `CODEOWNERS`, teams, merge settings, branch protection).

**Requires [GitHub CLI](https://cli.github.com/)** (`gh`) — authenticated with access to the `thebigtechplus` org. All BigTech+ developers use `gh`.

Configures **one repository per run**. It does not apply to all repos automatically.

## Install

```bash
gh extension install thebigtechplus/gh-bootstrap-repo
```

Upgrade later:

```bash
gh extension upgrade bootstrap-repo
```

## Usage

```bash
# Create a private repo and configure it (default)
gh bootstrap-repo api --create

# Create a public repo
gh bootstrap-repo oss-demo --create --public

# Configure an existing repo
gh bootstrap-repo web
```

## Without the extension (one-liners)

Still requires `gh` on your PATH (the script calls `gh`).

```bash
# macOS / Linux / Git Bash / WSL
curl -fsSL https://raw.githubusercontent.com/thebigtechplus/.github/main/scripts/bootstrap-repo.sh | bash -s -- api --create
```

```powershell
# Windows PowerShell
$script = Join-Path $env:TEMP 'btp-bootstrap-repo.ps1'
Invoke-RestMethod -Uri 'https://raw.githubusercontent.com/thebigtechplus/.github/main/scripts/bootstrap-repo.ps1' -OutFile $script
pwsh -File $script api -Create
```

Canonical scripts live in [thebigtechplus/.github](https://github.com/thebigtechplus/.github). The extension loads them through the GitHub API so you always get the current default-branch version.
