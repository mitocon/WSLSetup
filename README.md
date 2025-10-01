# WSLSetup

## Table of contents
1. zshインストール

## zshインストール
```
sudo apt update
sudo apt install zsh -y
zsh --version

chsh -s $(which zsh)
# ターミナルを再起動する

# Oh My Zshのインストール
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# テーマ適用
sed -i 's/^ZSH_THEME=.*/ZSH_THEME="agnoster"/' ~/.zshrc
```
参考：oh my zshのテーマ一覧 [Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/themes)
