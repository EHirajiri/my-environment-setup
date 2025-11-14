# Mac setup

## Homebrewをインストール
※ 最新の情報は[公式ページ](https://brew.sh/ja/)を参照
```
% /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

パス設定
```
% echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/$(whoami)/.zprofile
% . /Users/$(whoami)/.zprofile
% brew --version
Homebrew 4.6.19
```

## ユーティリティ

### Google Chrome
```
% brew install google-chrome
% brew info google-chrome 
==> google-chrome: 142.0.7444.60 (auto_updates)
```

Macの設定の「プライバシーとセキュリティ」中の「画面収録とシステムオーディオ録音」に「Google Chrome」を追加する

### Google Drive
```
% brew install --cask google-drive
% brew info --cask google-drive 
==> google-drive: 116.0.6 (auto_updates)
```

### 7-Zip
```
brew install sevenzip
```

### Clipy
クリップボード拡張アプリ
```
% brew install --cask clipy
% softwareupdate --install-rosetta --agree-to-license
% brew info --cask clipy
==> clipy: 1.2.1 (auto_updates)
```

### Kindle
- App Storeからインストール

## コミュニケーションツール

### Slack
```
% brew install slack
% brew info slack
==> slack: 4.46.104 (auto_updates)
```

## 開発ツール

### Git
```
% brew install git
% brew info git  
==> git: stable 2.51.2 (bottled), HEAD
```

設定
```
% git config --global user.name "Your Name"
% git config --global user.email "your.email@mail.com" 
# 確認
% git config --global -l
		user.name=Your Name
		user.email=your.email@mail.com
```

GithubのSSH設定
- SSHキー作成
```
% ssh-keygen -t ed25519 -C "your.email@mail.com"
```
- SSH 公開鍵をコピーし、Githubに登録
```
% pbcopy < ~/.ssh/id_ed25519.pub
```
- 設定ファイル作成
```
% touch ~/.ssh/config
% open ~/.ssh/config

# 下記を追加
Host github.com
  IdentityFile ~/.ssh/id_ed25519
  User git
```
- 接続確認
```
% ssh -T git@github.com
```

### NVM
```
% brew install nvm
% mkdir ~/.nvm
% vi ~/.zprofile
# 下記を追加
export NVM_DIR="$HOME/.nvm"
  [ -s "/opt/homebrew/opt/nvm/nvm.sh" ] && \. "/opt/homebrew/opt/nvm/nvm.sh"
  [ -s "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm" ] && \. "/opt/homebrew/opt/nvm/etc/bash_completion.d/nvm"
% . /Users/$(whoami)/.zprofile
% nvm -v
0.40.3
```

- nodeインストール
```
% nvm ls-remote 22
       v22.21.1   (Latest LTS: Jod)
% nvm install v22.21.1
% node -v
v22.21.1
% nvm alias default v22.21.1
```

### pnpm
```
brew install pnpm
% pnpm --version
10.20.0
```

### Visual Studio Code
```
% brew install --cask visual-studio-code
% code --version
1.105.1
```
- 拡張機能
  - [Japanese Language Pack for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MS-CEINTL.vscode-language-pack-ja)
  - [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
  - [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
  - [Vitest](https://marketplace.visualstudio.com/items?itemName=vitest.explorer)
  - [Docker](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)

### Android Studio
```
% brew install --cask android-studio
```

### Python
```
% brew search python@3
==> Formulae
python@3.10     python@3.12     python@3.14 ✔   bpython         jython
python@3.11     python@3.13     python@3.9      ipython         cython
% brew install python@3.14
% python3 -V 
Python 3.9.6
% vi ~/.zprofile
# 下記を追記
export PATH="$(brew --prefix python)/libexec/bin:$PATH"
% . /Users/$(whoami)/.zprofile
% python --version
Python 3.14.0
% python3 --version
Python 3.14.0
```

### Java
```
% brew install java
% echo 'export PATH="/usr/local/opt/openjdk/bin:$PATH"' >> ~/.zprofile
% echo 'export CPPFLAGS="-I/usr/local/opt/openjdk/include"' >> ~/.zprofile
```

### Apidog
```
% brew install --cask apidog
% brew info --cask apidog
==> apidog: 2.7.45 (auto_updates)
```

### Docker Desktop for Mac
```
% brew install --cask docker
% brew info --cask docker     
==> docker-desktop: 4.49.0,208700 (auto_updates)
```

### Figma
```
% brew install figma
% brew info figma
==> figma: 125.9.10 (auto_updates)
```

### リモートデスクトップ（Windows)
```
% brew install --cask windows-app
% brew info --cask windows-app
==> windows-app: 11.2.5
```

### Github CLI
```
% brew install gh
% gh --version
gh version 2.83.0 (2025-11-04)
```

### XCode

[Appleの開発者向けページ](https://developer.apple.com/download/all/) からダウンドード

