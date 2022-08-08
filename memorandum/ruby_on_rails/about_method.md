# Method解説用保管庫

<details><summary>レコードの存在をチェック</summary>

# レコードの存在をチェック

[Railsドキュメント,レコードの存在をチェック](
https://railsdoc.com/page/exists_q)

## 説明

- 指定したレコードが存在するか

## 使い方

```
モデル.exists?([条件])
```
### 引数の指定例

```
モデル.exists?(カラム: '文字列')
モデル.exists?(モデル.id)
```


## 例

```
User.all

>> [#<User id: 6, email: "11@11", name: "11", introduction: nil, created_at: "2022-08-07 06:45:48.063041000 +0000", updated_at: "2022-08-07 06:45:48.410068000 +0000">,               
 #<User id: 7, email: "33@33", name: "33", introduction: nil, created_at: "2022-08-08 06:09:54.367668000 +0000", updated_at: "2022-08-08 06:09:54.726593000 +0000">]   


User.exists?(name: '33')

>>  User Exists? (0.2ms)  SELECT 1 AS one FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "33"], ["LIMIT", 1]]
 => true   
 
 User.exists?(name: 'test')
   User Exists? (0.2ms)  SELECT 1 AS one FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "test"], ["LIMIT", 1]]
 => false 
 
```

</details>

<details><summary>条件に当てはまる値を全て取得</summary>

# 条件に当てはまる値を全て取得
[Railsドキュメント,条件に当てはまる値を全て取得](
https://railsdoc.com/page/model_where)


## 説明

- 条件に当てはまるレコードを全て取得

## 使い方

```
モデル.where(条件..)
```
### 引数の指定例

#### 文字列で指定
```
モデル.where("category_id = '1'")
```

#### ハッシュで指定
```
モデル.where(category_id: 1)
```

#### プレースホルダを使用
```
モデル.where("category_id = :category_id", {category_id: params[:category_id]})
```

#### あいまい検索
第一引数（列名 LIKE ?）の?の部分が、第二引数へ置き換えられる。
```
モデル.where("列名 LIKE ?", "%値%")  # 値(文字列)を含む
モデル.where("列名 LIKE ?", "値_")   # 値(文字列)と末尾の1文字
```

#### 範囲指定
```
モデル.where(:id => 1..10)
```

#### 終端なしの範囲指定
```
モデル.where(age: 20..)
```



#### 複数キーを指定

```
モデル.where(category_id: [1, 2])
```

## 例

```
User.where("name LIKE?", "%#{11}%"
 User Load (0.2ms)  SELECT "users".* FROM "users" WHERE (name LIKE'11')
 => [#<User id: 6, email: "11@11", name: "11", introduction: nil, created_at: "2022-08-07 06:45:48.063041000 +0000", updated_at: "2022-08-07 06:45:48.410068000 +0000">]

 
User.where("name = ?", '11')
 User Load (0.2ms)  SELECT "users".* FROM "users" WHERE (name = '11')                      
 => [#<User id: 6, email: "11@11", name: "11", introduction: nil, created_at: "2022-08-07 06:45:48.063041000 +0000", updated_at: "2022-08-07 06:45:48.410068000 +0000">]

```

</details>



<details><summary>関連するテーブルをまとめて取得</summary>

# 関連するテーブルをまとめて取得

[Railsドキュメント,関連するテーブルをまとめて取得](
https://railsdoc.com/page/includes)

## 説明

- 関連するテーブルをまとめて取得

## 使い方

```
モデル.includes(引数..)
```


## 例

```
test
```

</details>

<details><summary>条件を指定して最初の1件を取得</summary>

# 条件を指定して最初の1件を取得

[Railsドキュメント,条件を指定して最初の1件を取得](
https://railsdoc.com/page/find_by)

## 説明

- 条件を指定して最初の1件を取得
- 存在しない場合はnil

## 使い方

```
モデル.find_by(条件..)

# 失敗したら例外発生
モデル.find_by!(条件..)
```


## 例

```
User.find_by(name: 11)
User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "11"], ["LIMIT", 1]]
=> #<User id: 6, email: "11@11", name: "11", introduction: nil, created_at: "2022-08-07 06:45:48.063041000 +0000", updated_at: "2022-08-07 06:45:48.410068000 +0000"> 

User.find_by(name: 22)
User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."name" = ? LIMIT ?  [["name", "22"], ["LIMIT", 1]]
 => nil 

User.find_by(id: 7)
User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 7], ["LIMIT", 1]]
 => #<User id: 7, email: "33@33", name: "33", introduction: nil, created_at: "2022-08-08 06:09:54.367668000 +0000", updated_at: "2022-08-08 06:09:54.726593000 +0000"> 
```

</details>



<details><summary>IDを指定してレコードを取得</summary>

# IDを指定してレコードを取得

[IDを指定してレコードを取得](
https://railsdoc.com/page/find)

## 説明

- IDを指定してレコードを取得
- 指定したIDの中に存在しないIDが1つでもあると例外が発生

## 使い方

```
モデル.find(件数..)

```


## 例

```
User.find(7)
User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 7], ["LIMIT", 1]]
 => #<User id: 7, email: "33@33", name: "33", introduction: nil, created_at: "2022-08-08 06:09:54.367668000 +0000", updated_at: "2022-08-08 06:09:54.726593000 +0000"> 

User.find_by(id: 7)
User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 7], ["LIMIT", 1]]
 => #<User id: 7, email: "33@33", name: "33", introduction: nil, created_at: "2022-08-08 06:09:54.367668000 +0000", updated_at: "2022-08-08 06:09:54.726593000 +0000"> 

User.find(6,7)
User Load (0.3ms)  SELECT "users".* FROM "users" WHERE "users"."id" IN (?, ?)  [["id", 6], ["id", 7]]
 => 
[#<User id: 6, email: "11@11", name: "11", introduction: nil, created_at: "2022-08-07 06:45:48.063041000 +0000", updated_at: "2022-08-07 06:45:48.410068000 +0000">,
 #<User id: 7, email: "33@33", name: "33", introduction: nil, created_at: "2022-08-08 06:09:54.367668000 +0000", updated_at: "2022-08-08 06:09:54.726593000 +0000">] 

 User.find(2)
 User Load (0.1ms)  SELECT "users".* FROM "users" WHERE "users"."id" = ? LIMIT ?  [["id", 2], ["LIMIT", 1]]
/home/ec2-user/.rvm/gems/ruby-3.1.2/gems/activerecord-6.1.6.1/lib/active_record/core.rb:346:in `find': Couldn't find User with 'id'=2 (ActiveRecord::RecordNotFound)
```

</details>




<details><summary>find、find_by、whereの違い</summary>

# find、find_by、whereの違い

[find、find_by、whereの違い](
https://qiita.com/tsuchinoko_run/items/f3926caaec461cfa1ca3)

## 説明

- idの値が分かっていて、そのidのデータを取得したい場合・・・find
- idの値が不明で、id以外のカラムを検索条件としたい場合・・・find_by
- id以外のカラムの検索条件で、複数の実行結果を取得したい場合・・・where

</details>

