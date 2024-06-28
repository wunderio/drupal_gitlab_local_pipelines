# Drupal GitLab local pipelines

This is a small project to try and run Drupal GitLab tasks locally with
GrumpPHP via Docker.

## Installation

1. Install wunderio/drupal-gitlab-local-pipelines Composer package using our Docker image:

   ```bash
   docker run -it -v "$(pwd)":/app hkirsman/drupal-gitlab-local-pipelines composer require wunderio/drupal-gitlab-local-pipelines --dev
   ```

   or use your local Composer:

   ```bash
   composer require wunderio/drupal-gitlab-local-pipelines --dev
   ```

2. Add vendor and grumphp.yml to .gitignore file:

    ```bash
    # Composer
    vendor
    composer.lock
    ```

## Pushing Docker changes Docker Hub

1. Create image

    ```bash
    make build
    ```

2. Log in to Docker Hub:


    ```bash
    docker login
    ```

3. Tag Docker Image

    ```bash
    docker tag hkirsman/drupal-gitlab-local-pipelines hkirsman/drupal-gitlab-local-pipelines:latest
    ```

4. Push Docker Image

    ```bash
    docker push hkirsman/drupal-gitlab-local-pipelines:latest
    ```
