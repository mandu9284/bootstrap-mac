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
* [starship](https://formulae.brew.sh/formula/starship#default)

```zsh
brew install starship
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
* [bat](https://formulae.brew.sh/formula/bat#default)
* [ripgrep](https://formulae.brew.sh/formula/ripgrep#default)
* [fd](https://formulae.brew.sh/formula/fd#default)
* [zoxide](https://formulae.brew.sh/formula/zoxide#default)
* [sheldon](https://formulae.brew.sh/formula/sheldon#default)
* [mise](https://formulae.brew.sh/formula/mise#default)
* [gh](https://formulae.brew.sh/formula/gh#default)

```zsh
brew install fzf tmux eza bat ripgrep fd zoxide sheldon mise gh
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
