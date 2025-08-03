# Build with Docker

Assuming you have Docker installed, pull the following image:

```bash
docker pull jekyll/jekyll:latest
```

Run a container:

```bash
docker compose up
```

View the site here: `http://0.0.0.0:4000`

# Build locally

First install Jekyll according to [these instructions](https://jekyllrb.com/docs/installation/).

```bash
git clone git@github.com:AmeliaCMU/AmeliaCMU.github.io.git
cd AmeliaCMU.github.io
bundle install
bundle exec jekyll serve --watch --incremental
```

This should start the web server locally, and enables incremental build.
