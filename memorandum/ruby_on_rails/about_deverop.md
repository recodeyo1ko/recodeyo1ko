# 開発のために

```
git clone リポジトリURL
cd カレントディレクトリ
bundle install
rails webpacker:install
rails db:migrate
rails db:migrate RAILS_ENV=test
bundle exec rspec spec/ --format documentation
```

## rails c ローカル用
```
gem 'rb-readline'
```