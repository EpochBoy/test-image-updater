# test-image-updater

Demo app for **ArgoCD Image Updater** automatic image updates.

This is a minimal Go application that displays version, commit, and build time info.

## Purpose

Demonstrates ArgoCD Image Updater's ability to:

- Watch Harbor registry for new images
- Automatically update the ArgoCD Application with new digests
- Deploy without manual intervention

## Endpoints

| Path | Description |
| ---- | ----------- |
| `/` | HTML page with version info |
| `/health` | Health check (JSON) |
| `/version` | Version details (JSON) |

## How It Works

1. Push code to this repo
2. GitHub webhook triggers Argo Workflows CI
3. CI builds image, pushes to Harbor
4. ArgoCD Image Updater detects new image
5. Updates the Application, ArgoCD deploys

## Local Development

```bash
go run main.go
# Open http://localhost:8080
```

## Related

- **[epochcloud-test](https://github.com/EpochBoy/epochcloud-test)**: Kargo multi-stage promotion demo
- **[epochcloud](https://github.com/EpochBoy/epochcloud)**: Main infrastructure repo
