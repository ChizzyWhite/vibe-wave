# VibeWave — Music App Demo

A responsive, Spotify-inspired music discovery interface built with HTML, CSS, and JavaScript. It includes mood cards, search, genre filters, demo track playback, liked songs saved in browser storage, recently played tracks, shuffle, repeat, progress, and volume controls.

## Run locally

You can open `index.html` in a browser, or run it in Docker:

```bash
docker build -t vibewave .
docker run -d -p 8080:80 --name vibewave vibewave
```

Then open <http://localhost:8080>.

To stop and remove the container:

```bash
docker stop vibewave
docker rm vibewave
```

## Push to Docker Hub with GitHub Actions

1. Create a Docker Hub access token (PAT).
2. In your GitHub repository, open **Settings → Secrets and variables → Actions → New repository secret**.
3. Add:
   - `DOCKER_USERNAME` — your Docker Hub username.
   - `DOCKER_PASSWORD` — your Docker Hub access token (not your account password).
4. Push this project to the `main` branch. The workflow in `.github/workflows/docker.yml` builds and pushes `YOUR_DOCKERHUB_USERNAME/vibewave:latest`.

## Important notes

- This is a front-end demo, not a production streaming service. It does not include user accounts, a backend, a database, real playlist creation, or paid subscriptions.
- The sample audio and artwork load from external public URLs and may change, be unavailable, or have usage restrictions. Replace them with media you own or are licensed to use before public/commercial release.
- The page is static; the Dockerfile uses Nginx only to serve your own HTML, CSS, and JavaScript files. Nginx is not the music application itself.
