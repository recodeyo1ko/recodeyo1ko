# アソシエーションについて

- モデル間の関連付け に使われる概念

## Primary Key(主キー)とforeign_key(外部キー)
- まず、データには一つ一つ識別するためのidがあります。これを Primary Keyと言い、Railsでは id というカラム名でテーブル作成時に標準搭載されています。
- foreign key というのはその 親のid(Primary key)を保存するカラム というわけです。
これにより どの親に所属しているのか？ というのを識別することができます。
























参考

[【初心者向け】丁寧すぎるRails『アソシエーション』チュートリアル【幾ら何でも】【完璧にわかる】](https://qiita.com/kazukimatsumoto/items/14bdff681ec5ddac26d1#%E3%82%B3%E3%83%B3%E3%83%88%E3%83%AD%E3%83%BC%E3%83%A9%E3%83%93%E3%83%A5%E3%83%BC%E3%81%AE%E5%AE%9F%E8%A3%85)