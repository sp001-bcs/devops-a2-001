# devops-a2-001

A simple personal portfolio page built with plain HTML and CSS for
DevOps for Cloud Computing, Assignment 2.

## What is in this repository

| File | Purpose |
|------|---------|
| `index.html` | The portfolio page |
| `style.css` | Colours and layout |
| `Dockerfile` | Packages the page in an nginx image |
| `.dockerignore` | Keeps Git and CI files out of the image |
| `.github/workflows/ci.yml` | Checks the page, builds the image and pushes it to Docker Hub |

## Run it locally with Docker

```bash
docker build -t <dockerhub-username>/devops-a2:manual .
docker run -d -p 8080:80 --name page <dockerhub-username>/devops-a2:manual
```

Then open http://localhost:8080 in your browser.

## CI/CD

Every push to `main` and every pull request runs the workflow.
It checks the page, builds the Docker image, and on `main` pushes it
to Docker Hub with the tag `latest`.
