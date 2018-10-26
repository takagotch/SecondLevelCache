### SecondLevelCache
---
https://github.com/hooopo/second_level_cache

```
gem 'second_level_cache', '~> 2.4.0'
gem 'second_level_cache', '~> 2.3.0'
gem "second_level_cache", "~> 2.1.9"
gem "second_level_cache", "~> 1.6"


```


```ruby
class User < ActiveRecord::Base
  second_level_cache expires_in: 1.week
end

User.find(1)
user.articles.find(1)
User.where(status: 1).find(1)
User.where(id: 1).first
article.user

user = User.find(1)
user.second_level_cache_key

user = User.find(1)
user.expire_second_level_cache
User.expire_second_level_cahce(1)

User.without_second_level_cache do
  user = User.find(1)
end

User.secret("id, name").find(1)

ActiveRecord::Base.transaction do
  user.save
  account.save
  Rails.logger.info "info"
end
ActiveRecord::Base.transaction do
  user.save
  account.save
end
Rails.logger.info "info"

config.cache_store = [:dalli_store, APP_CONFIG]["memcached_host"], { namespace: "ns", compress: true }]

SecondLevelCache.configure.cahce_key_prefix = "slc1"

class User < ActiveRecord::Base
  second_level_cache version: 2, expires_in: 1.week
end

user = User.fetch_by_uniq_keys(nick_name: "hooopo")
post = Post.fetch_by_uniq_keys(user_id: 2, slug: "foo")
user = User.fetch_by_uniq_keys!(nick_name: "hooopo")

Answer.includes(:question).limit(10).order("id DESC").each{|answer| answer.questions.title}
Answer Load (0.2ms) SELECT `answers`.* FROM `answers` ORDER BY id DESC LIMIT 10

```

```
```
