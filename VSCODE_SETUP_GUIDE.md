# VSCode Universal Setup Guide

## 📋 Quick Setup Instructions

### Option 1: Global Settings (Recommended for personal use)

Place `settings.json` in your **user settings** directory:

**Windows:**
```
%APPDATA%\Code\User\settings.json
```

**macOS:**
```
~/Library/Application Support/Code/User/settings.json
```

**Linux:**
```
~/.config/Code/User/settings.json
```

### Option 2: Workspace Settings (Project-specific)

Create a `.vscode` folder in your project root and add these files:

```
your-project/
├── .vscode/
│   ├── settings.json       # Settings for this project
│   ├── extensions.json     # Recommended extensions
│   ├── launch.json         # Debug configurations
│   └── tasks.json          # Build/test tasks
└── ... (your project files)
```

---

## 🚀 Step-by-Step Setup

### Step 1: Copy Configuration Files

1. **Download the files I created:**
   - `settings.json` → Universal editor settings
   - `extensions.json` → Recommended extensions list
   - `launch.json` → Debug configurations
   - `tasks.json` → Build and test tasks

2. **Choose your setup method:**
   - **Global**: Copy to user settings directory (affects all projects)
   - **Per-project**: Copy to `.vscode/` folder in each project

### Step 2: Install Extensions

Open VSCode and press:
- **Windows/Linux:** `Ctrl+Shift+P`
- **macOS:** `Cmd+Shift+P`

Type: `Extensions: Show Recommended Extensions`

Click "Install All" for the extensions in `extensions.json`

**Essential Extensions (install these first):**
```
code --install-extension ms-python.python
code --install-extension ms-python.vscode-pylance
code --install-extension charliermarsh.ruff
code --install-extension dbaeumer.vscode-eslint
code --install-extension esbenp.prettier-vscode
code --install-extension eamodio.gitlens
code --install-extension usernamehw.errorlens
```

### Step 3: Configure AI Assistant (Optional)

**GitHub Copilot (Paid):**
1. Install: `github.copilot` + `github.copilot-chat`
2. Create `.github/copilot-instructions.md` in project root
3. Paste the system prompt there

**Continue.dev (Free, Open-Source):**
1. Install: `continue.continue`
2. Configure: `~/.continue/config.json`
3. Add your system prompt to `systemMessage` field

**Cline (Claude Dev):**
1. Install: `saoudrizwan.claude-dev`
2. Create `.clinerules` in project root
3. Paste system prompt there

---

## 🎯 How to Use the System Prompt

### For GitHub Copilot:

Create `.github/copilot-instructions.md`:
```markdown
[Paste the full system prompt here]
```

Copilot will automatically use it as context for all conversations.

### For Continue.dev:

Edit `~/.continue/config.json`:
```json
{
  "systemMessage": "[Paste system prompt here - escape quotes with \\]",
  "models": [
    {
      "title": "Claude Sonnet 4",
      "provider": "anthropic",
      "model": "claude-sonnet-4-20250514",
      "apiKey": "your-api-key"
    }
  ]
}
```

### For Cline:

Create `.clinerules` in project root and paste the full system prompt.

---

## 📁 Recommended Project Structure

```
your-project/
├── .vscode/                    # VSCode workspace config
│   ├── settings.json
│   ├── extensions.json
│   ├── launch.json
│   └── tasks.json
├── .github/                    # GitHub-specific
│   └── copilot-instructions.md # System prompt for Copilot
├── .clinerules                 # System prompt for Cline
├── .ide/                       # IDE context (from system prompt)
│   ├── manifest.json
│   └── architecture.md
├── memory.md                   # Project memory (AI context)
├── src/                        # Source code
├── tests/                      # Test files
├── .gitignore
├── README.md
└── (other config files)
```

---

## 🛠️ Customization Tips

### 1. Adjust Formatting Preferences

In `settings.json`, modify:
```json
{
  "prettier.printWidth": 100,        // Line length
  "prettier.semi": true,             // Semicolons
  "prettier.singleQuote": false,     // Quote style
  "editor.tabSize": 2                // Indentation
}
```

### 2. Change Theme & Icons

```json
{
  "workbench.colorTheme": "GitHub Dark",           // or "Monokai", "Dracula"
  "workbench.iconTheme": "material-icon-theme"     // or "vs-seti"
}
```

### 3. Add Custom Tasks

In `tasks.json`, add your own tasks:
```json
{
  "label": "My Custom Task",
  "type": "shell",
  "command": "your-command-here",
  "problemMatcher": []
}
```

Run tasks: `Ctrl+Shift+B` (Windows/Linux) or `Cmd+Shift+B` (macOS)

### 4. Add Debug Configurations

In `launch.json`, add configurations for your project:
```json
{
  "name": "My Debug Config",
  "type": "node",
  "request": "launch",
  "program": "${workspaceFolder}/src/index.js"
}
```

Start debugging: `F5`

---

## 🔧 Troubleshooting

### Extensions Not Working?

1. **Reload VSCode:** `Ctrl+Shift+P` → "Developer: Reload Window"
2. **Check extension settings:** Some need API keys or configuration
3. **Install language support:** Python extension needs Python installed, etc.

### Formatting Not Working?

1. **Check default formatter:**
   ```json
   "[python]": {
     "editor.defaultFormatter": "charliermarsh.ruff"
   }
   ```
2. **Enable format on save:**
   ```json
   "editor.formatOnSave": true
   ```
3. **Check for conflicts:** Disable other formatters for the same language

### Linter Showing Errors?

1. **Install dependencies:**
   - Python: `pip install ruff mypy`
   - Node.js: `npm install -D eslint prettier`
2. **Configure linter settings** in `settings.json`
3. **Check linter is enabled:**
   ```json
   "ruff.enable": true,
   "eslint.enable": true
   ```

### Debug Not Starting?

1. **Check program path** in `launch.json`
2. **Install debugger extension:**
   - Python: `ms-python.debugpy`
   - Node.js: Built-in
3. **Set breakpoints:** Click left gutter or press `F9`

---

## 🎓 Keyboard Shortcuts to Remember

### Essential Commands

| Action | Windows/Linux | macOS |
|--------|--------------|-------|
| Command Palette | `Ctrl+Shift+P` | `Cmd+Shift+P` |
| Quick Open File | `Ctrl+P` | `Cmd+P` |
| Toggle Terminal | `` Ctrl+` `` | `` Cmd+` `` |
| Format Document | `Shift+Alt+F` | `Shift+Option+F` |
| Go to Definition | `F12` | `F12` |
| Find References | `Shift+F12` | `Shift+F12` |
| Rename Symbol | `F2` | `F2` |
| Start Debugging | `F5` | `F5` |
| Run Build Task | `Ctrl+Shift+B` | `Cmd+Shift+B` |
| Toggle Sidebar | `Ctrl+B` | `Cmd+B` |

### AI Assistant Shortcuts

| Action | Shortcut |
|--------|----------|
| Open Copilot Chat | `Ctrl+Shift+I` |
| Inline Suggestion Accept | `Tab` |
| Next Suggestion | `Alt+]` |
| Previous Suggestion | `Alt+[` |

---

## 📚 Additional Resources

**Official Docs:**
- [VSCode Settings](https://code.visualstudio.com/docs/getstarted/settings)
- [Debugging Guide](https://code.visualstudio.com/docs/editor/debugging)
- [Tasks Reference](https://code.visualstudio.com/docs/editor/tasks)

**Extension Docs:**
- [Python in VSCode](https://code.visualstudio.com/docs/python/python-tutorial)
- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://prettier.io/docs/en/editors.html#visual-studio-code)

**AI Assistants:**
- [GitHub Copilot Docs](https://docs.github.com/en/copilot)
- [Continue.dev Docs](https://continue.dev/docs)
- [Cline (Claude Dev)](https://github.com/cline/cline)

---

## ✅ Verification Checklist

After setup, verify everything works:

- [ ] Settings applied (check `settings.json`)
- [ ] Extensions installed (check Extensions panel)
- [ ] Python formatting works (`Shift+Alt+F` on `.py` file)
- [ ] TypeScript formatting works (`Shift+Alt+F` on `.ts` file)
- [ ] ESLint shows errors in JS/TS files
- [ ] Debug configurations appear in Run & Debug panel
- [ ] Tasks appear in Terminal → Run Task menu
- [ ] AI assistant responds with system prompt context
- [ ] Git integration works (Source Control panel)

---

## 🚀 Next Steps

1. **Create `.ide/` and `memory.md`** in your project (per system prompt)
2. **Initialize Git** if not already: `git init`
3. **Add `.gitignore`** for your stack (Python/Node.js)
4. **Run your first task:** `Ctrl+Shift+B` → Select a task
5. **Test debugging:** Set a breakpoint and press `F5`

Happy coding! 🎉
