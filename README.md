# WSLSetup

## Table of contents
1. zsh インストール
1. GitHub CLI インストール
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

## GitHub CLI インストール
公式：https://github.com/cli/cli/blob/trunk/docs/install_linux.md#debian

2025-10-02 現在
```
(type -p wget >/dev/null || (sudo apt update && sudo apt install wget -y)) \
	&& sudo mkdir -p -m 755 /etc/apt/keyrings \
	&& out=$(mktemp) && wget -nv -O$out https://cli.github.com/packages/githubcli-archive-keyring.gpg \
	&& cat $out | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
	&& sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
	&& sudo mkdir -p -m 755 /etc/apt/sources.list.d \
	&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
	&& sudo apt update \
	&& sudo apt install gh -y
```

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
