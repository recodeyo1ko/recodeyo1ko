# ルーティングについて

resouces :books






## namespace

```
namespace :page do
  get :privacy_policy
  get :company_information
  get :term_of_use
  get :businessdeal
end
```

「名前付きルート」「パス」「コントローラ#アクション」にpageが追加

## :module
```
resources :users, module: :admin

#以下も同等
scope module: :admin do
  resources :users
end
```
- 「コントローラ#アクション」にしかadmin名前空間が追加されていません。
- パスには表したくないが別のディレクトリにまとめたいコントローラがある場合に利用できます。


参考

[Railsのルーティング（routes）を極める](https://techracho.bpsinc.jp/baba/2020_11_20/15619)