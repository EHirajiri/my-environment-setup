# Mac setup

## Homebrewをインストール (2025/11/1時点 v4.6.19)

※ 最新の情報は[公式ページ](https://brew.sh/ja/)を参照

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

パス設定

```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/$(whoami)/.zprofile
. /Users/$(whoami)/.zprofile
```

## 必須アプリ

### Google Chrome

```
brew install google-chrome
```

Macの設定の「プライバシーとセキュリティ」中の「画面収録とシステムオーディオ録音」に「Google Chrome」を追加する

## コミュニケーションツール

### Slack

```
brew install slack
```

## 開発ツール

## その他

### リモートデスクトップ（Windows)

```
brew install --cask windows-app
```

### Clipy

クリップボード拡張アプリ

```
brew install --cask clipy
softwareupdate --install-rosetta --agree-to-license
```
