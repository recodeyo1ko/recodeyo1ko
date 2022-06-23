## deviseに関するあれやこれ


## destroy_user_sessionのHTTPメソッドがGETになっている。

- config/initializers/devise.rb /
```
# The default HTTP method used to sign out a resource. Default is :delete.
config.sign_out_via = :get
```

defaultがdeleteなのに手を加えてしまった。
