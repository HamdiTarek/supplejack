---
layout: page
title: "Supplejack Website"
category: start
date: 2014-06-30 15:00:53
order: 7
---

The Supplejack Website is part of the standard Supplejack platform that can aggregate data and content from many different sources.

It uses the `supplejack_client` gem to connect to the Supplejack API. For more information about Supplejack Client gem, please refer to the [documentation](http://digitalnz.github.io/supplejack/start/supplejack-client.html#configuration)

## Installation

Clone the project

```bash
git clone git@github.com:DigitalNZ/supplejack_website.git
```

Create a `local_env.rb` file and place it inside `config/`

```ruby
# config/local_env.rb
API_HOST = 'http://localhost:3000'
API_KEY = 'your_api_key'
THUMBNAIL_SERVER_URL = "http://magickly.afeld.me/'
```

Run bundle install

```bash
bundle install
```

Create a `database.yml` file and place it inside `config/`. Follow Rails standard database configuration. Run migrations

```bash
bundle exec rake db:create
bundle exec rake db:migrate
```

Run Rails server

```bash
rails s
```

####Notes

* Supplejack demo website should work out of the box, providing no modification in supplejack api record schema.
* You need to update `config/initializers/supplejack_client.rb` if you modify the sample supplejack api record schema. Refer to [Supplejack Client](/supplejack/start/supplejack-client.html) doc to understand the configuration steps.
* Please always check [Website github](https://github.com/DigitalNZ/supplejack_website) source code to know what to fix.
* Supplejack website comes with devise for authentication and the user have email and password as default fields. To add custom fields to user follow [tutorial](http://jacopretorius.net/2014/03/adding-custom-fields-to-your-devise-user-model-in-rails-4.html)
* Follow Rails standard mailer configuration for any mail sending to work for the website.