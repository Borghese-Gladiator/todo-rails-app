# Ruby on Rails Template Project
This project is to test out my local Kubernetes setup and refresh some Ruby on Rails.

## Setup
```
Ruby version:  ruby 3.2.2 (2023-03-30 revision e51014f9c0) [x64-mingw-ucrt]
```

# Notes
## Scaffolding
- initialize project
  ```
  gem install rails  # install Ruby on Rails
  rails new todo-rails-app
  mkdir todo-django-app
  cd todo-django-app
  poetry init
  pyenv global 3.10.11
  poetry add django
  ```
- Dockerfile -> comes by default
- create Models + Controllers
  ```
  # Models
  rails generate model Task title:string description:text
  # Controllers
  rails generate controller Tasks index show new create edit update destroy
  # Migrate
  rails db:migrate
  ```
- create Views
  ```
  Index: app/views/tasks/index.html.erb
  Show: app/views/tasks/show.html.erb
  New: app/views/tasks/new.html.erb
  Edit: app/views/tasks/edit.html.erb
  ```

## Deployment
- deploy to Railway 
- deploy via Harness to Kubernetes on home server

