# github-actions-capstone

End-to-end CI/CD pipeline using GitHub Actions — Day 48 & 49 DevOps Capstone

![PR Pipeline](https://github.com/Devel955/github-actions-capstone/actions/workflows/pr-pipeline.yml/badge.svg)
![Main Pipeline](https://github.com/Devel955/github-actions-capstone/actions/workflows/main-pipeline.yml/badge.svg)
![Health Check](https://github.com/Devel955/github-actions-capstone/actions/workflows/health-check.yml/badge.svg)

## What This Does

A production-style CI/CD pipeline that automatically:
- Tests code on every PR
- Scans dependencies for vulnerabilities
- Builds and pushes Docker image on merge to main
- Scans Docker image with Trivy for CVEs
- Deploys to production with manual approval

## Running Locally

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Start the app:
```bash
uvicorn app.main:app --host 0.0.0.0 --port 8000
```

3. Check health:
```bash
curl http://localhost:8000/health
```

## Running with Docker

1. Build image:
```bash
docker build -t github-actions-capstone .
```

2. Run container:
```bash
docker run -p 8000:8000 github-actions-capstone
```

3. Check health:
```bash
curl http://localhost:8000/health
```

## Docker Hub

Image: [anan623/github-actions-capstone](https://hub.docker.com/r/anan623/github-actions-capstone)