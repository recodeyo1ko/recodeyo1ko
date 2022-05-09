# gitに関するあれやこれ


コマンド一覧

<details><summary>初期設定</summary>

```
git config --global user.name "XXXX"
git config --global user.email "XXXX@hogehoge.com"
```
</details>


<details><summary>ローカルリポジトリを作成し、最初にpushする手順</summary>

```
$ git init
$ git add .
$ git commit -m "Initial commit"
$ git remote add origin https://github.com/XXXX/XXXXXX.git
$ git push -u origin main
```
</details>

<details><summary>クローン</summary>
```
git clone https://github.com/XXXX/XXXXXX.git
```
</details>

<details><summary>ブランチ作成・変更</summary>

```
#ブランチの確認
git branch
#ブランチの作成
git branch branch_name
#ブランチの変更
git checkout branch_name
```
</details>

<details><summary>マージ</summary>

現在のブランチが更新される。

```

```
</details>


```
rm -rf .git
```

```
rmdir /s .git
```

git フォルダが開けに現象：監視リポジトリが下にある


```
//ファイル全体のキャッシュ削除
$ git rm -r --cached .

//ファイルを指定してキャッシュ削除
$ git rm -r --cached [ファイル名]
```
