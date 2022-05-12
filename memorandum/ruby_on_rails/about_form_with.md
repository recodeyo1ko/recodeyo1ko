発生した問題

更新しないとボタンが動かない

divをまたぐ


hiddenについてまとめること


select を使う
```form.erb
<%= form_with model: @item, url: item_path(@item), method: :patch do |f| %>
  <%= f.select :amount, [['1',1],['2',2],['3',3],['4',4],['5',5],['6',6],['7',7],['8',8],['9',9]] %>
  <%= f.submit "変更", class:"btn btn-success" %>
<% end %>
```
