## Container Documentation for Kubectl Documentation

Official kubectl container image providing a secure, enterprise-ready command-line interface for managing Kubernetes clusters. Features FIPS-compliant cryptography, security hardening, and comprehensive cluster management capabilities for production environments.

📌 **Base Foundation**: Production-ready container from cleanstart.

**Image Path**: `kubectl`

**Registry**: `cleanstart`

## Key Features
Core capabilities and strengths of this container



## Common Use Cases
Typical scenarios where this container excels



## Pull Latest Image
Download the container image from the registry

```bash
docker pull ghcr.io/cleanstart-containers/kubectl:latest
```
```bash
docker pull ghcr.io/cleanstart-containers/kubectl:latest-dev
```

## Basic Run
Run the container with basic configuration

```bash
docker run -it --name kubectl-test ghcr.io/cleanstart-containers/kubectl:latest
```

## Production Deployment
Deploy with production security settings

```bash
docker run -d --name kubectl-prod \
  --read-only \
  --security-opt=no-new-privileges \
  --user 1000:1000 \
  ghcr.io/cleanstart-containers/kubectl:latest
```

Volume Mount Mount local directory for persistent data

```bash
docker run -v ~/.kube:/root/.kube ghcr.io/cleanstart-containers/kubectl:latest
```

Port Forwarding Run with custom port mappings

```bash
docker run -p 8001:8001 ghcr.io/cleanstart-containers/kubectl:latest proxy
```

## Environment Variables
Configuration options available through environment variables

| Variable | Default | Description |
|----------|---------|-------------|
| ENV | production | Environment mode |
| LOG_LEVEL | info | Logging level |

## Security Best Practices
Recommended security configurations and practices



## Kubernetes Security Context
Recommended security context for Kubernetes deployments

```yaml
securityContext:
  allowPrivilegeEscalation: false
  capabilities:
    drop:
    - ALL
  readOnlyRootFilesystem: true
  runAsUser: 1000
  runAsGroup: 1000
```

## Documentation Resources
Essential links and resources for further information
 
**CleanStart Images**: https://images.cleanstart.com/
 
**Community Images**:<br>
**Docker Hub**: https://hub.docker.com/u/cleanstart<br>
**GitHub**: https://github.com/cleanstart-containers<br>
**AWS ECR Public Gallery**: https://gallery.ecr.aws/cleanstart/
 
**Presence on Social Media**:<br>
**Community**: https://www.linkedin.com/groups/18324021/<br>
**YouTube**: https://www.youtube.com/@CleanStartOfficial<br>
 
**Contribute to Container Use Cases**: https://github.com/cleanstart-dev/cleanstart-use-cases/
