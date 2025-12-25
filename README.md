# bootstrap-mac
MacBookの初期化から開発環境構築までの手順をまとめたリポジトリ

## MacBook初期化
### インストール
* Chrome
* Logi Options

### キーボード設定
1. キーのリピート速度：速い（最大）
2. リピート入力認識までの時間：短い（最大）
3. 連打できるように下記のコマンドをターミナルに入力
```zsh
defaults write -g ApplePressAndHoldEnabled -bool false
```

### ログイン
* Google
* X
* Github

## 開発環境構築
### インストール
#### アプリケーション
* [Github Desktop](https://desktop.github.com/download/)
* [Docker Desktop](https://www.docker.com/products/docker-desktop/)
* [DBeaver](https://dbeaver.io/download/)
* [Postman](https://www.postman.com/downloads/)
* [Figma](https://www.figma.com/ja-jp/downloads/)
* [iTerm2](https://iterm2.com/downloads.html)

#### パッケージマネージャ
* [Homebrew](https://brew.sh/)

#### シェルカスタマイズ
**starship**
* [starship](https://formulae.brew.sh/formula/starship#default)
* [starship config](https://starship.rs/ja-JP/config/)

```zsh
brew install starship
```

```zsh
# configファイル生成
mkdir -p ~/.config && touch ~/.config/starship.toml
```

```toml
# エディターの補完を設定スキーマに合わせて取得
"$schema" = 'https://starship.rs/config-schema.json'

# シェルのプロンプトの間に空行を挿入する
add_newline = true

# 記号"❯"を記号"➜"に置き換える
[character] # 設定対象のモジュール名は 'character'
success_symbol = '[➜](bold green)' # セグメント 'success_symbol' を '➜' 配色 'bold green' (太字の緑色) に設定

# package モジュールを無効化してプロンプトから完全に非表示にする
[package]
disabled = true
```

```zsh
# テーマインストール（tokyo night）
starship preset tokyo-night -o ~/.config/starship.toml
```

**sheldon**
* [sheldon](https://formulae.brew.sh/formula/sheldon#default)

```zsh
brew install fzf tmux eza bat ripgrep fd zoxide mise gh
```

```zsh
# configファイル生成
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

# syntax-highlighting は最後に読み込む
[plugins.zsh-syntax-highlighting]
github = "zsh-users/zsh-syntax-highlighting"
```

#### エディター
* [NeoVim](https://neovim.io/doc/install/)
* [LazyVim](https://www.lazyvim.org/installation)

```zsh
brew install neovim
```

#### CLIツール
* [fzf](https://formulae.brew.sh/formula/fzf) 
* [tmux](https://formulae.brew.sh/formula/tmux)
* [eza](https://formulae.brew.sh/formula/eza#default)
```zsh
# .zshrc
alias ei="eza --icons --git"
alias ea="eza -la --icons --git"
alias ee="eza -aahl --icons --git"
alias et="eza -T -L 3 -a -I 'node_modules|.git|.cache' --icons"
alias ls=ei
alias la=ea
alias ll=ee
```
* [bat](https://formulae.brew.sh/formula/bat#default)
* [ripgrep](https://formulae.brew.sh/formula/ripgrep#default)
* [fd](https://formulae.brew.sh/formula/fd#default)
* [zoxide](https://formulae.brew.sh/formula/zoxide#default)
```zsh
# .zshrc
eval "$(zoxide init zsh --cmd cd)"
```
* [mise](https://formulae.brew.sh/formula/mise#default)

```zsh
# 設定ファイル生成
mkdir -p .config/mise && .config/mise/config.toml
```

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
* [gh](https://formulae.brew.sh/formula/gh#default)

```zsh
brew install fzf tmux eza bat ripgrep fd zoxide mise gh
```

#### font
* [nerd font](https://formulae.brew.sh/cask/font-3270-nerd-font#default)

```zsh
brew install --cask font-3270-nerd-font
```

#### LazyVimのパッケージ
1. LSP
2. Linter
3. Formmater

#### 言語
```zsh
# node
brew install node
```
