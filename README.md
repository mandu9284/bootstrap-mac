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
#### junha
* Google
* X
* dcincide
#### mandu
* Google
* X
* Github
#### calme
* Google
* X
* pixiv
* pinterest

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

#### エディター
* [NeoVim](https://neovim.io/doc/install/)
* [LazyVim](https://www.lazyvim.org/installation)

#### CLIツール
* [fzf](https://formulae.brew.sh/formula/fzf)
* [tmux](https://formulae.brew.sh/formula/tmux)
* [eza](https://formulae.brew.sh/formula/eza#default)
* [bat](https://formulae.brew.sh/formula/bat#default)
* [ripgrep](https://formulae.brew.sh/formula/ripgrep#default)
* [fd](https://formulae.brew.sh/formula/fd#default)
* [zoxide](https://formulae.brew.sh/formula/zoxide#default)
```zsh
brew install fzf tmux eza bat ripgrep fd zoxide
```

#### LazyVimのパッケージ
1. LSP
2. Linter
3. Formmater
