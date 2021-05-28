* Ruby 2.6.6 
* Rails 5.2.4
* postgresql

# rails new

```
docker-compose run web rails new . --force --no-deps --database=postgresql --skip-bundle
```

# bundle install

```
docker-compose build
```

# Railsのconfig/database.ymlファイルを、下記のように書き換える。

```
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: 5

development:
  <<: *default
  database: myapp_development


test:
  <<: *default
  database: myapp_test
```

# コンテナ起動

```
docker-compose up
```

#  参考　https://qiita.com/kodai_0122/items/795438d738386c2c1966
