# Ubuntuの導入手順

## OSの準備
- [ ] UbuntuOSのインストール　（[UbuntuのOSインストールサイト](https://jp.ubuntu.com/download)）
- [ ] OSをUSBメモリに書き込む　（[balena etcher](https://www.balena.io/etcher/)） 
- [ ] 書き込んだUSBを挿し、BIOS画面からBoot

## パッケージのインストール
> バージョンによってファイル名が異なるため、適宜合わせる
> コマンドの実行はカレンとディレクトリの移動を適宜行うこと（もしくはファイルパスを指定すること）

### 初期設定

- [ ] まずは最新の状態にしておく

```
Sudo apt update
```
### Chrome

- [ ] chromeのインストール　([chromeのダウンロード](https://www.google.com/chrome/))
> google-chrome-stable_current_amd64.debファイルがダウンロードできたら、ターミナルから下記コマンドを実行する
```
sudo apt-get install ./google-chrome-stable_current_amd64.deb
sudo dpkg -i ./google-chrome-stable_current_amd64.deb
```

### VScode
- [ ] vscodeのインストール　([vscodeのダウンロード](https://code.visualstudio.com/download))
> code_1.74.2-1671533413_amd64.debファイルがダウンロードできたら、ターミナルから下記コマンドを実行する
```
sudo apt install ./code_1.74.2-1671533413_amd64.deb
sudo dpkg -i code_1.64.2-1644445741_amd64.deb
```

### git
gitのインストール
```
sudo apt install git
```
ssh接続の準備
```
cd ~/.ssh
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub
```


gitの接続がエラーになったら
```
ssh -T git@github.com
vi ~/.ssh/config
```
vim内で以下記述後保存して終了。（:wq）
```
Host github.com
   User git
   Hostname ssh.github.com
   Port 443
   IdentityFile ~/.ssh/id_rsa
```
### Slack
```
sudo snap install slack

```
