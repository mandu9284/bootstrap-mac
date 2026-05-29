
# bootstrap-mac
A repository summarizing the steps from MacBook initialization to development environment setup.

## MacBook Setup
### Install
* Chrome
* Logi Options

### Keyboard Settings
1. Key Repeat Rate: Fast (Max)
2. Delay Until Repeat: Short (Max)
3. change capslock and control each other
4. Enter the following command in the terminal to enable key repetition on long-press:

```zsh
defaults write -g ApplePressAndHoldEnabled -bool false

```

### Logins

* Google
* X
* GitHub

### Development Environment Setup

#### Package Manager

* [Homebrew](https://brew.sh/)

#### Applications

* [GitHub Desktop](https://desktop.github.com/download/)

```zsh
brew install --cask github
```

* [Docker Desktop](https://www.docker.com/products/docker-desktop/)

```zsh
brew install --cask docker-desktop
```

* [iTerm2](https://iterm2.com/downloads.html)

```zsh
brew install --cask iterm2
```


#### Shell Customization

**starship**

* [brew-starship](https://formulae.brew.sh/formula/starship#default)
* [starship config](https://starship.rs/config/)

1. install starship using brew 
```zsh
brew install starship
```

2. make the directory and a config file
```zsh
mkdir -p ~/.config && touch ~/.config/starship.toml

```

```toml
# Fetch editor completions matching the config schema
"$schema" = '[https://starship.rs/config-schema.json](https://starship.rs/config-schema.json)'

# Inserts a blank line between shell prompts
add_newline = true

# Replace the "❯" symbol with "➜"
[character] # The target module to configure is 'character'
success_symbol = '[➜](bold green)' # Set the 'success_symbol' segment to '➜' with a 'bold green' color scheme

# Disable the package module to hide it completely from the prompt
[package]
disabled = true

```


3. set tokyo-night theme
```zsh
starship preset tokyo-night -o ~/.config/starship.toml
```

4. set starship config variable in .zprofile
```zsh
export STARSHIP_CONFIG=~/example/non/default/path/starship.toml
```

**sheldon**

* [sheldon](https://formulae.brew.sh/formula/sheldon#default)

```zsh
brew install sheldon 
```

```zsh
# Generate config file
mkdir -p .config/sheldon && touch .config/sheldon/plugins.toml

```

```toml
# ~/.config/sheldon/plugins.toml
shell = "zsh"

[plugins.zsh-autosuggestions]
github = "zsh-users/zsh-autosuggestions"

[plugins.zsh-completions]
github = "zsh-users/zsh-completions"

[plugins.zsh-async]
github = "mafredri/zsh-async"

# syntax-highlighting must be loaded last
[plugins.zsh-syntax-highlighting]
github = "zsh-users/zsh-syntax-highlighting"

```

#### Editors

* [NeoVim](https://neovim.io/doc/install/)
* [LazyVim](https://www.lazyvim.org/installation)

1. neovim install
```zsh
brew install neovim
```

2. cloning
```zsh
git clone https://github.com/LazyVim/starter ~/.config/nvim
```

3. LazyVim Packages

**LSP**

* taplo
* css-lsp
* gh-actions-language-server
* html-lsp
* marksman
* ruff
* stylua
* typescript-language-server
* yaml-language-server

**Linter**

* markdownlint
* taplo
* eslint_d
* ruff

**Formatter**

* prettierd
* jq
* fixjson
* markdownlint
* yamlfix
* sql-formatter
* taplo
* ruff
* shfmt
* stylua

#### AI Tools

1. cursor install 
```zsh
https://formulae.brew.sh/cask/cursor#default
```

2. cursor cli install

```zsh
curl https://cursor.com/install -fsS | bash
```

#### CLI Tools

* [fzf](https://formulae.brew.sh/formula/fzf)
* [tmux](https://formulae.brew.sh/formula/tmux)
* [tree](https://formulae.brew.sh/formula/tree#default)
* [jq](https://formulae.brew.sh/formula/jq#default)
* [eza](https://formulae.brew.sh/formula/eza#default)
* [bat](https://formulae.brew.sh/formula/bat#default)
* [ripgrep](https://formulae.brew.sh/formula/ripgrep#default)
* [fd](https://formulae.brew.sh/formula/fd#default)
* [zoxide](https://formulae.brew.sh/formula/zoxide#default)
* [gh](https://formulae.brew.sh/formula/gh#default)
* [lazygit](https://formulae.brew.sh/formula/lazygit#default)

1. installations
```zsh
brew install fzf tmux tree jq eza bat ripgrep fd zoxide gh lazygit
```

2. alisas
```zsh
alias ei="eza --icons --git"
alias ea="eza -la --icons --git"
alias ee="eza -aahl --icons --git"
alias et="eza -T -L 3 -a -I 'node_modules|.git|.cache' --icons"
alias ls=ei
alias la=ea
alias ll=ee
```

3. zoxide using default command (cd)
```zsh
eval "$(zoxide init zsh --cmd cd)"
```

#### Fonts

* [font-jetbrains-mono-nerd-font]([https://formulae.brew.sh/cask/font-3270-nerd-font#default](https://formulae.brew.sh/cask/font-jetbrains-mono-nerd-font))

```zsh
brew tap homebrew/cask-fonts
```

```zsh
brew install --cask font-jetbrains-mono-nerd-font
```

#### node setting

0. node version package manager

* [mise](https://formulae.brew.sh/formula/mise#default)

```zsh
brew mise
```

1. Generate config file()
```zsh
mkdir -p .config/mise && .config/mise/config.toml
```

2. config file contents
```toml
# ~/.config/mise/config.toml
[tools]
awscli = "latest"
node = "latest"
ruby = "3.4.2"
neovim = "latest"
terraform = "latest"
go = "latest"
postgres = "17"
zoxide = "latest"
```

3. pnpm 
* [pnpm](https://pnpm.io/installation)

```zsh
brew install pnpm 
```

4. set security setting in .npmrc 

```zsh
touch ~/.npmrc
```

```text
# Enforces strict compliance with the Node/npm versions specified in package.json's "engines" field.
engine-strict=true

# Disables execution of all scripts (like pre/postinstall) defined in dependency packages for security.
ignore-scripts=true

# Automatically runs a security vulnerability scan (npm audit) during package installations.
audit=true

# Blocks the installation of packages published less than 1 day ago to prevent zero-day supply chain attacks.
min-release-age=1

# Saves the exact version number to package.json instead of using version ranges like ^ or ~.
save-exact=true

# Sets the minimum vulnerability severity level that will cause npm audit to fail the build to "high".
audit-level=high

# Forces installation to fail if there are any conflicting or missing peer dependencies.
strict-peer-deps=true

# Allows Git-based dependency installations to run lifecycle scripts as root only if npm was run as root.
allow-git=root
```


