<p align="center">
  <a href="https://unbyte.de">
    <img src="https://www.unbyte.de/wp-content/uploads/2024/12/unbyte_logo.svg" alt="unbyte GmbH" width="300">
  </a>
</p>

# Container Images

A centralized collection of container images for DevOps workflows, infrastructure services, and utility tooling.

## Image Catalog

| Image Name | Type | Description |
| :--- | :--- | :--- |
| `bootstrap` | Tooling | For bootstrapping unbyte-orbit platform |
| `helm` | Workflow | For releasing helm charts |
| `helm-kubectl` | Tooling | For running `install` k8s job in cluster charts |
| `kubectl` | Tooling | For `ip-injector` k8s job |
| `kubectl-tools` | Tooling | CLI tools bundle for various PBM chart k8s jobs |
| `opentofu` | Tooling | For local development in TF repositories |
| `pbm-release` | Workflow | For PBM release pipelines |
| `powerdns-auth` | Service | Authoritative DNS server |
| `powerdns-recursor` | Service | DNS Recursor |
| `pre-commit` | Workflow | For running pre-commit in GitLab pipelines |
| `s3-bucket-manager` | Tooling | For k8s jobs to manage buckets |

## Usage

Images are built automatically and stored in the [GitHub Container Registry](https://github.com/orgs/unbyte-de/packages?repo_name=container-images).

Pulling an image:

```bash
docker pull ghcr.io/unbyte-de/container-images/<image-name>:latest
```

## Development

To add a new image:

1. Create a new directory in `images/`.
2. Add your `Dockerfile` and a `VERSION` file.
3. Open a Pull Request.
4. The CI/CD pipeline will automatically detect the new folder and build the image.
  **Note that the pipeline will build and push a new tag only when version is bumped in `VERSION` file.
