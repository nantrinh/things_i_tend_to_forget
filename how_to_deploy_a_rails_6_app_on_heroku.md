### How to Deploy a Rails 6 App on Heroku
Assumptions:
- the app was created with `rails new appname --database=postgresql`.
- there is at least one model, view, controller, and route
- you are using a database with some migrations
- you have already committed your code to a git repo

[Heroku instructions](https://devcenter.heroku.com/articles/getting-started-with-rails6)

- `heroku create` 
- `git push heroku master` 
- `heroku run rake db:migrate`
- `heroku open`

### Useful Commands
- `heroku run rails console`

### Todo
- [Add a Procfile](https://devcenter.heroku.com/articles/deploying-rails-applications-with-the-puma-web-server#config)
