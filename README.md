Container Documentation for Kubectl Documentation

Official kubectl container image providing a secure, enterprise-ready command-line interface for managing Kubernetes clusters. Features FIPS-compliant cryptography, security hardening, and comprehensive cluster management capabilities for production environments.

📌 Base Foundation: Production-ready container from cleanstart.

Image Path: cleanstart/kubectl:latest Registry: Docker Hub

## Key Features
Core capabilities and strengths of this container



## Common Use Cases
Typical scenarios where this container excels



## Pull Latest Image
Download the container image from the registry

```bash
docker pull cleanstart/kubectl:latest
```
```bash
docker pull cleanstart/kubectl:latest-dev
```

## Basic Run
Run the container with basic configuration

```bash
docker run -it --name kubectl-test cleanstart/kubectl:latest
```

## Production Deployment
Deploy with production security settings

```bash
docker run -d --name kubectl-prod \
  --read-only \
  --security-opt=no-new-privileges \
  --user 1000:1000 \
  cleanstart/kubectl:latest
```

## Volume Mount
Mount local directory for persistent data

```bash
docker run -v ~/.kube:/root/.kube cleanstart/kubectl:latest
```

## Port Forwarding
Run with custom port mappings

```bash
docker run -p 8001:8001 cleanstart/kubectl:latest proxy
```

## Environment Variables
Configuration options available through environment variables

## Security Best Practices
Recommended security configurations and practices

Use specific image tags for production deployments
Mount read-only kubeconfig files
Implement RBAC policies for cluster access
Use separate service accounts with minimal privileges
Enable audit logging for kubectl operations
Regularly rotate kubeconfig credentials
Use network policies to restrict API server access
Implement proper secrets management

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

## Resources & Documentation
Essential links and resources for further information

Container Registry: https://www.cleanstart.com/
CleanStart Community Images: https://hub.docker.com/u/cleanstart
How-to-Run CleanStart images & sample projects: https://github.com/cleanstart-dev/cleanstart-containers
How to run sample projects using Dockerfile
How to deploy via Kubernetes YAML
How to migrate from public images to CleanStart images


## Vulnerability Disclaimer
CleanStart offers Docker images that include third-party open-source libraries and packages maintained by independent contributors. While CleanStart maintains these images and applies industry-standard security practices, it cannot guarantee the security or integrity of upstream components beyond its control.

Users acknowledge and agree that open-source software may contain undiscovered vulnerabilities or introduce new risks through updates. CleanStart shall not be liable for security issues originating from third-party libraries, including but not limited to zero-day exploits, supply chain attacks, or contributor-introduced risks.

Security remains a shared responsibility: CleanStart provides updated images and guidance where possible, while users are responsible for evaluating deployments and implementing appropriate controls.

