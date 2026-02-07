# Cursor IDE Configuration Backup

This directory contains Cursor IDE extensions and settings for easy restoration on a new machine.

## Files Included

- `extensions.txt` - List of all installed extensions
- `settings.json` - Editor settings and preferences
- `keybindings.json` - Custom keyboard shortcuts

## Installed Extensions

| Extension | Description |
|-----------|-------------|
| anthropic.claude-code | Claude AI coding assistant |
| bierner.markdown-mermaid | Mermaid diagram support in Markdown |
| cweijan.dbclient-jdbc | Database client JDBC support |
| cweijan.vscode-mysql-client2 | MySQL database client |
| dbaeumer.vscode-eslint | ESLint JavaScript linter |
| eamodio.gitlens | Git supercharged |
| editorconfig.editorconfig | EditorConfig support |
| esbenp.prettier-vscode | Prettier code formatter |
| github.vscode-github-actions | GitHub Actions workflow support |
| golang.go | Go language support |
| hashicorp.hcl | HCL language support |
| hashicorp.terraform | Terraform language support |
| haskell.haskell | Haskell language support |
| justusadam.language-haskell | Haskell syntax highlighting |
| mhutchie.git-graph | Git graph visualization |
| mkhl.shfmt | Shell script formatter |
| ms-azuretools.vscode-containers | Container tools |
| ms-azuretools.vscode-docker | Docker support |
| ms-vscode.makefile-tools | Makefile support |
| redhat.vscode-yaml | YAML language support |
| streetsidesoftware.code-spell-checker | Spell checker |
| tidalcycles.vscode-tidalcycles | TidalCycles live coding |
| timonwong.shellcheck | ShellCheck linter |

## Settings Overview

### Editor Settings
- **Format on Save**: Enabled
- **Tab Completion**: On
- **Inline Suggestions**: Enabled
- **Zoom Level**: 1
- **Large File Optimizations**: Disabled

### Terminal Settings
- **Scrollback**: 9,999,999 lines (effectively unlimited)

### Language-Specific Settings

| Language | Formatter | Tab Size |
|----------|-----------|----------|
| TypeScript | ESLint | default |
| JSON | Prettier | default |
| YAML | Red Hat YAML | default |
| Haskell | Haskell (ormolu) | 2 |
| HCL/Terraform | HashiCorp HCL | default |
| Docker Compose | Red Hat YAML | 2 |
| GitHub Actions | Red Hat YAML | default |

### Custom Keybindings
- `Cmd+I` → Open Composer Agent Mode

## Installation on a New Machine

### Prerequisites
1. Install Cursor on your new machine:
   ```bash
   # Using Homebrew
   brew install --cask cursor
   ```

### Step 1: Install Extensions

Run the following command to install all extensions:

```bash
# Install all extensions from the list
cat extensions.txt | xargs -L 1 cursor --install-extension
```

Or install them one by one:

```bash
cursor --install-extension anthropic.claude-code
cursor --install-extension bierner.markdown-mermaid
cursor --install-extension cweijan.dbclient-jdbc
cursor --install-extension cweijan.vscode-mysql-client2
cursor --install-extension dbaeumer.vscode-eslint
cursor --install-extension eamodio.gitlens
cursor --install-extension editorconfig.editorconfig
cursor --install-extension esbenp.prettier-vscode
cursor --install-extension github.vscode-github-actions
cursor --install-extension golang.go
cursor --install-extension hashicorp.hcl
cursor --install-extension hashicorp.terraform
cursor --install-extension haskell.haskell
cursor --install-extension justusadam.language-haskell
cursor --install-extension mhutchie.git-graph
cursor --install-extension mkhl.shfmt
cursor --install-extension ms-azuretools.vscode-containers
cursor --install-extension ms-azuretools.vscode-docker
cursor --install-extension ms-vscode.makefile-tools
cursor --install-extension redhat.vscode-yaml
cursor --install-extension streetsidesoftware.code-spell-checker
cursor --install-extension tidalcycles.vscode-tidalcycles
cursor --install-extension timonwong.shellcheck
```

### Step 2: Copy Settings

Copy the settings and keybindings to Cursor's configuration directory:

```bash
# Create the User directory if it doesn't exist
mkdir -p ~/Library/Application\ Support/Cursor/User

# Copy settings
cp settings.json ~/Library/Application\ Support/Cursor/User/
cp keybindings.json ~/Library/Application\ Support/Cursor/User/
```

### Step 3: Restart Cursor

Quit and restart Cursor for all settings to take effect.

## One-Liner Installation Script

Run this from the `cursor` directory to do everything at once:

```bash
# Install extensions and copy settings
cat extensions.txt | xargs -L 1 cursor --install-extension && \
mkdir -p ~/Library/Application\ Support/Cursor/User && \
cp settings.json keybindings.json ~/Library/Application\ Support/Cursor/User/
```

## Updating This Backup

To update this backup with your current Cursor settings:

```bash
# Export extensions list
cursor --list-extensions > extensions.txt

# Copy current settings
cp ~/Library/Application\ Support/Cursor/User/settings.json .
cp ~/Library/Application\ Support/Cursor/User/keybindings.json .
```

## Troubleshooting

### Extensions not installing?
- Make sure Cursor CLI is in your PATH
- Try opening Cursor first, then run the commands
- Check if the extension ID is correct: `cursor --list-extensions`

### Settings not applying?
- Ensure Cursor is completely closed before copying settings
- Check for JSON syntax errors in the settings file
- Try copying settings via GUI: `Cmd+Shift+P` → "Preferences: Open User Settings (JSON)"

### Keybindings conflicts?
- Check for conflicts: `Cmd+K Cmd+S` to open Keyboard Shortcuts
- System shortcuts may override Cursor shortcuts

## Manual Settings Import (GUI Method)

1. Open Cursor
2. Press `Cmd+Shift+P` to open Command Palette
3. Type "Preferences: Open User Settings (JSON)"
4. Copy contents from `settings.json` into the opened file
5. For keybindings: `Cmd+Shift+P` → "Preferences: Open Keyboard Shortcuts (JSON)"
6. Copy contents from `keybindings.json`

---

*Last updated: February 5, 2026*
*Cursor version: Latest*
