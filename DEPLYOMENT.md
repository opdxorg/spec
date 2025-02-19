# Deployment

## Local Testing
```
uv run mkdocs serve
```

## Building
```
uv run mike deploy --push --update-aliases [VERSION] latest
uv run mike set-default --push latest
```