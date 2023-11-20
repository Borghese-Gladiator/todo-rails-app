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
- create GitHub Action to build image and push to DockerHub
  - create DockerHub repository to store images
  - create DockerHub access token
  - go to GitHub repository | Settings | Secrets and variables | Actions | click "New repository secret"
    - `DOCKERHUB_USERNAME: <value>`
    - `DOCKERHUB_TOKEN: <value>`
  - linux
    ```
    mkdir -p .github/workflows
    touch .github/workflows/build_and_push.yaml
    ```
  - windows (batch)
    ```
    mkdir .github\workflows
    type nul > .github\workflows\build_and_push.yaml
    ```
  - windows (powershell)
    ```
    New-Item -ItemType Directory -Path .github\workflows
    New-Item -ItemType File -Path .github\workflows\build_and_push.yaml
    ```
- create Kubernetes manifests in kubernetes/ using Docker Image name
  - linux
    ```
    mkdir kubernetes
    touch kubernetes\build_and_push.yaml
    touch kubernetes\ingress.yaml
    touch kubernetes\service.yaml
    ```
  - windows (batch)
    ```
    mkdir kubernetes
    type nul > kubernetes\build_and_push.yaml
    type nul > kubernetes\ingress.yaml
    type nul > kubernetes\service.yaml
    ```
  - windows (powershell)
    ```
    New-Item -ItemType Directory -Path kubernetes
    New-Item -ItemType File -Path kubernetes\deployment.yaml
    New-Item -ItemType File -Path kubernetes\ingress.yaml
    New-Item -ItemType File -Path kubernetes\service.yaml
    ```

## Deployment
- deploy to Railway 
- deploy via Harness to Kubernetes on home server

