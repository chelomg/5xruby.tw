Development Guide
=================

Software Dependencies (OS X)
----------------------------

```bash
$ brew install postgres redis imagemagick pkg-config
```

Setup
-----

```
$ bundle install
$ cp config/application.yml.example config/application.yml
$ cp config/database.yml.example config/database.yml
$ rake db:setup dev:fake
$ rails server
```

Tasks
-----

* `rake dev:fake[model_name,count]`

    dev:fake to generate fake data for all model, dev:fake[course,3] to create 3 fake courses (available parameters: author, post, speaker, category, course, faq)

Generate Admin Pages for Models
-------------------------------

For example, to generate admin pages for `Post` model:

```bash
$ rails generate model post title:string content:text
$ rails generate scaffold admin/post title:string content:text --migration=false --parent=post
```

Schema Changing
---------------

1. Generate migraion file
2. Update facotry
3. Update `_form.html.erb`
4. Update `show` page

# `db/schema.rb` MUST BE CONSISTENT in every environment, both servers and clients. Having differnt content is totally not permitted.

Contact
=======

hi@5xruby.tw