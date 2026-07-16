# gh-bootstrap-repo

GitHub CLI extension to bootstrap BigTech+ repositories (labels, `CODEOWNERS`, teams, merge settings, branch protection).

**Requires [GitHub CLI](https://cli.github.com/)** (`gh`) — authenticated with access to the `thebigtechplus` org.

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
# Create a private repo and configure it
gh bootstrap-repo api --create

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
irm https://raw.githubusercontent.com/thebigtechplus/.github/main/scripts/bootstrap-repo.ps1 | iex
# then:
# (the script does not accept piped args via iex easily — prefer the extension, or:)
Invoke-RestMethod https://raw.githubusercontent.com/thebigtechplus/.github/main/scripts/bootstrap-repo.ps1 -OutFile $env:TEMP\btp-bootstrap.ps1
pwsh -File $env:TEMP\btp-bootstrap.ps1 api -Create
```

Canonical scripts live in [thebigtechplus/.github](https://github.com/thebigtechplus/.github).
