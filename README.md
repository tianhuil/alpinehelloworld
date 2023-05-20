# Deploying to Heroku

To deploy to Heroku, set `HEROKU_APP` and run the following

```sh
docker buildx build --platform linux/amd64 -t registry.heroku.com/$HEROKU_APP/web . --push && \
    heroku container:release web && \\
    heroku open
```
