# macOS Terminal Configuration with Zsh

A comprehensive guide to configuring your macOS terminal with iTerm2, Zsh, and Oh My Zsh for improved productivity and aesthetics.

## Overview

This setup enhances the default macOS terminal experience by integrating:
- **iTerm2**: Advanced terminal replacement with powerful features
- **Zsh**: Unix shell with extensive improvements over bash
- **Oh My Zsh**: Framework for managing Zsh configuration
- **Custom themes and plugins**: Beautiful UI and enhanced functionality

---

## Prerequisites

- macOS operating system
- Basic familiarity with terminal commands

---

## Installation Steps

### Step 1: Install Homebrew

Homebrew is a package manager that simplifies software installation on macOS.

1. Install Xcode Command Line Tools:
```bash
xcode-select --install
```

If you encounter an error, reset xcode-select:
```bash
xcode-select -r
```

2. Install Homebrew:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

3. Add Homebrew to your PATH:

After installation, the installer will display commands to add Homebrew to your PATH. Run them exactly as shown.

**For Apple Silicon Macs (M1/M2/M3):**
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

**For Intel Macs:**
```bash
echo 'eval "$(/usr/local/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/usr/local/bin/brew shellenv)"
```

4. Verify Homebrew installation:
```bash
brew --version
```

### Step 2: Install iTerm2

iTerm2 is a feature-rich terminal replacement for macOS.

```bash
brew install --cask iterm2
```

### Step 3: Install Zsh

Install Zsh using Homebrew:

```bash
brew install zsh
```

> **Note**: macOS ships with Zsh by default at `/bin/zsh`, but installing via Homebrew ensures you have the latest version.

### Step 4: Install Oh My Zsh

Oh My Zsh is a framework for managing Zsh configuration with community-driven plugins and themes.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

**Verify installation:**
```bash
zsh --version
```

**Upgrade Oh My Zsh:**
```bash
upgrade_oh_my_zsh
```

After installation, restart iTerm2 to apply changes.

---

## Configuration

### Step 5: Change the Default Theme

Oh My Zsh includes many pre-installed themes. The default is `robbyrussell`.

**To change to a pre-installed theme (e.g., agnoster):**

1. Open the Zsh configuration file:
```bash
nano ~/.zshrc
```
Or:
```bash
open ~/.zshrc
```

2. Find the line `ZSH_THEME="robbyrussell"` and change it to:
```bash
ZSH_THEME="agnoster"
```

3. Apply changes:
```bash
source ~/.zshrc
```

**To install a custom theme (e.g., powerlevel9k):**

1. Clone the theme repository:
```bash
git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

2. Update `~/.zshrc`:
```bash
ZSH_THEME="powerlevel9k/powerlevel9k"
```

3. Apply changes:
```bash
source ~/.zshrc
```

### Step 6: Install Powerline Fonts

Many themes require powerline-patched fonts for proper display.

**Install all powerline fonts:**
```bash
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```

**Configure font in iTerm2:**
1. Navigate to: `iTerm2 > Preferences > Profiles > Text > Change Font`
2. Select a powerline font (e.g., Inconsolata, Fira Code)
3. For ligature support (e.g., → symbols), check "Use ligatures"

### Step 7: Install Color Scheme

Enhance visual appearance with custom color schemes.

1. Download [iTerm2 Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
2. Extract the ZIP file
3. Navigate to: `iTerm2 > Preferences > Profiles > Colors > Color Presets > Import`
4. Import schemes from the `schemes` folder
5. Select your preferred color scheme (e.g., Batman)

### Step 8: Install Plugins

Oh My Zsh comes with a git plugin pre-installed. Add additional plugins for enhanced functionality.

**Example: Install Docker plugin**

1. Clone the plugin:
```bash
git clone https://github.com/zsh-users/zsh-docker.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-docker
```

2. View installed plugins:
```bash
open ~/.oh-my-zsh
```
Navigate to: `custom > plugins`

3. Add to `~/.zshrc`:
```bash
plugins=(git zsh-docker)
```

4. Apply changes:
```bash
source ~/.zshrc
```

**Popular plugins to consider:**
- `zsh-autosuggestions`: Command suggestions based on history
- `zsh-syntax-highlighting`: Syntax highlighting for commands
- `docker`: Docker command completions
- `kubectl`: Kubernetes command completions

### Step 9: Add Aliases

Create shortcuts for frequently used commands.

**Edit `~/.zshrc` and add aliases:**
```bash
# Docker aliases
alias dckimgs="docker images"
alias dckps="docker ps"
alias dckrm="docker rm"

# Git aliases
alias gs="git status"
alias ga="git add"
alias gc="git commit"

# Navigation aliases
alias ll="ls -la"
alias ..="cd .."
```

**Apply changes:**
```bash
source ~/.zshrc
```

---

## Useful Commands

| Command | Description |
|---------|-------------|
| `nano ~/.zshrc` | Edit Zsh configuration in nano |
| `open ~/.zshrc` | Edit Zsh configuration in default editor |
| `source ~/.zshrc` | Apply configuration changes |
| `upgrade_oh_my_zsh` | Update Oh My Zsh to latest version |
| `open ~/.oh-my-zsh` | View Oh My Zsh directory |

---

## Troubleshooting

**Issue: Characters not displaying correctly**
- Ensure you've installed and selected a powerline font in iTerm2

**Issue: Theme not loading**
- Verify theme name is correct in `~/.zshrc`
- Run `source ~/.zshrc` to apply changes

**Issue: Plugins not working**
- Check plugin is listed in the `plugins=()` array in `~/.zshrc`
- Ensure plugin is properly installed in `~/.oh-my-zsh/custom/plugins/`

---

## Resources

- [Oh My Zsh Documentation](https://github.com/robbyrussell/oh-my-zsh)
- [iTerm2 Official Site](https://www.iterm2.com/)
- [Powerline Fonts](https://github.com/powerline/fonts)
- [iTerm2 Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)
- [Zsh Documentation](https://zsh.sourceforge.io/)

---

## Credits

Based on the tutorial by Chiamaka Ikeanyi from [freeCodeCamp](https://www.freecodecamp.org/news/how-to-configure-your-macos-terminal-with-zsh-like-a-pro-c0ab3f3c1156/)

---

## License

Feel free to use and modify this configuration guide for your personal setup.
