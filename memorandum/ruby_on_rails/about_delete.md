## deleteメソッドが動かない要因



```
<%= link_to '削除', "#{@root.id}", method: :delete %>
```

rootテーブルに投稿されたレコードを削除するため、実装したが削除されない。
リンクは表示されてクリックできるけどアクションが発火しない。加えてエラーも出ない。
ログを見るとGETで送られている。

route.rb、controllerの記述はちゃんとできてる。
rails routesを確認して、HTTPメソッドは来ている。htmlもdeleteになっている。


(.../app/javascript/packs/application.js )

```
import Rails from "@rails/ujs"
```

.../app/views/layouts/application.html.erb

```
<%= csrf_meta_tags %>
<%= csp_meta_tag %>
<%= stylesheet_pack_tag 'application', media: 'all', 'data-turbolinks-track': 'reload' %>
<%= javascript_pack_tag 'application', 'data-turbolinks-track': 'reload' %>
 ```

があるか確認。

jsをうまくimportできればok
