# dev_env_cheatsheet

## Mac環境設定

### **共有**

- コンピューター名を変更する

### **トラックパッド**

- 「ポイントとクリック」は、すべててチェックする
- 「スクロールとズーム」は、すべてチェックする
- 「その他のジェスチャ」は、「アプリケーションExpose」以外すべてチェックする

### キーボード

- 「ショートカット」でspotlightの項目の「spotlight検索を表示」と「Finderの検索ウィンドウを表示」のチェックを外す

### Dock

- 「Dock」を自動的に表示・非表示のチェックを付ける

### 省エネルギー

- 「電源アダプタ」で「ディスプレイがオフの時にコンピュータを自動的にオフにしない」にチェックを入れる

### セキュリティとプライバシー

- 「一般」で「スリープとスクリーンセーバの解除にパスワードを要求」を「開始後：すぐに」に設定

### デスクトップとスクリーンセーバ

- 「スクリーンセーバ」の「ホットコーナー」の右上を「ディスプレイをスリープさせる」に変更（これで、マウスを画面右上に移動するだけで、画面のロックをかける事ができる）

## 開発ツール類

- ターミナル起動（iTerm2かHyperまだ入れてないので）

### Xcode

```shell
xcode-select --install
```

### Homebrew

HP : https://brew.sh/index_ja

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew update

# cask リポジトリ追加
brew tap
brew tap caskroom/cask
brew tap homebrew/cask-versions
```

### zsh

```shell
brew install zsh
sudo echo '/usr/local/bin/zsh' >> /etc/shells
chsh -s /usr/local/bin/zsh
```

### git

```shell
brew install git

# 設定
git config --global user.name "ユーザ名"
git config --global user.mail "メールアドレス"
```

### docker

```shell
brew cask install docker
```

### font

- HP

https://ics.media/entry/7010/
https://qiita.com/yoskeoka/items/3b18ed4a40267aacc76f
http://com4tis.net/source-han-code-jp-mac-install/

- SourceHanCodeJP

##### インストールだけ手動

GitHub : https://github.com/adobe-fonts/source-han-code-jp/releases

```shell
curl -L https://github.com/adobe-fonts/source-han-code-jp/archive/2.011R.tar.gz | tar zx
```

- fontbookを検索→fontbookを開く
- fontbookの『+』から解凍したフォルダーを選択

***

##### 自動で入れる

```shell
curl -L https://github.com/adobe-fonts/source-han-code-jp/archive/2.011R.tar.gz | tar zx
mv source-han-code-jp-2.011R/OTC/SourceHanCodeJP.ttc ~/library/fonts
rm -r source-han-code-jp-2.011R
```

うまくインストールされていない時、以下を実行してから再起動

```shell
sudo atsutil databases -remove
```

### jq（json加工）

HP : https://qiita.com/takeshinoda@github/items/2dec7a72930ec1f658af

```shell
brew install jq
```

### AWS CLI

```shell
brew install awscli
```

### Node.js

```shell
brew install nodebrew

mkdir -p ~/.nodebrew/src
# インストールできるバージョン確認
nodebrew ls-remote

# nodebrew install-binary {version}
nodebrew install-binary latest
nodebrew use v7.1.0

# 有効化確認
nodebrew ls

# PATH
echo 'export PATH=$HOME/.nodebrew/current/bin:$PATH' >> ~/.bash_profile

# 最終確認
node -v
```

### yarn （js管理）

```shell
brew install yarn
```

## アプリ類

### java

```shell
brew cask install java
/usr/libexec/java_home -V

# PATH
touch ~/.bash_profile

# .bashrc OR .zshrcに追記
export JAVA_HOME=`/usr/libexec/java_home -v "12"` #12はその時のバージョン
export PATH=${JAVA_HOME}/bin:${PATH}

source ~/.bash_profile
echo $PATH
echo $JAVA_HOME
```

### ブラウザ

```shell
brew cask install google-chrome
brew cask install firefox
```

### Google 日本語入力

```shell
brew cask install google-japanese-ime
```

### チャットツール

Slack-Skype連携 : https://businesschatmaster.com/slack/skype-data-coordination

```shell
brew cask install slack
brew cask install skype
```

### Caffeine

```shell
brew cask install caffeine
```

### IDE

```shell
brew cask install visual-studio-code
brew cask install android-studio
```

### DBeaver

```shell
brew cask install dbeaver-community
```

### Forklift（sftpクライアント）

```shell
brew cask install forklift
```

## App Store

- ImageOptim
- Pocket
- Alfred
- Skitch

## その他

- zshからfishに変えるか検討中

### ssh設定

HP : https://qiita.com/reflet/items/0c338df07d9f6c6ef776
