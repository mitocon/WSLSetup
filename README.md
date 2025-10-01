# WSLSetup

## Table of contents
1. zsh インストール
1. Docker インストール
1. Claude Code インストール

## zsh インストール
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

## Docker インストール
```
sudo apt update
sudo apt install -y docker.io
```

## Claude Code インストール
```
npm install -g @anthropic-ai/claude-code

# 権限の問題(EACCES: permission denied)が発生した場合は以下を実行して再試行する
# mkdir -p ~/.npm-global
# npm config set prefix '~/.npm-global'
# echo '# npm global packages' >> ~/.zshrc
# echo 'export PATH=$HOME/.npm-global/bin:$PATH' >> ~/.zshrc
# source ~/.zshrc
```
MCPなどの設定は ClaudeCodeSetup を確認すること。
