# Deploying to Heroku

There are two ways to deploy to Heroku.  This assumes `HEROKU_APP` is the name of your Heroku app.

1. Build a Docker container locally (does not need `heroku.yml`).

    ```sh
    docker buildx build --platform linux/amd64 -t registry.heroku.com/$HEROKU_APP/web . --push && \
        heroku container:release web && \\
        heroku open
    ```

2. Ask Heroku to build the container (requires `heroku.yml`).  

    ```sh
    heroku git:remote -a $HEROKU_APP
    git push heroku main
    ```
