# My App Helm Chart

A production-ready Helm chart for deploying a web application on Kubernetes.

## Prerequisites

- Kubernetes 1.19+
- Helm 3.2.0+

## Installing the Chart

To install the chart with the release name `my-release`:

\`\`\`bash
helm repo add rohin-charts https://rohin21.github.io/helm-public-repo
helm install my-release rohin-charts/my-app
\`\`\`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

\`\`\`bash
helm delete my-release
\`\`\`

## Configuration

The following table lists the configurable parameters and their default values.

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicaCount` | Number of replicas | `1` |
| `image.repository` | Image repository | `nginx` |
| `image.tag` | Image tag | `1.21` |
| `service.type` | Kubernetes service type | `ClusterIP` |
| `service.port` | Kubernetes service port | `80` |
| `ingress.enabled` | Enable ingress | `false` |
| `resources.limits.cpu` | CPU limit | `100m` |
| `resources.limits.memory` | Memory limit | `128Mi` |

## Examples

### Basic Installation
\`\`\`bash
helm install my-app rohin-charts/my-app
\`\`\`

### With Custom Values
\`\`\`bash
helm install my-app rohin-charts/my-app \\
  --set replicaCount=3 \\
  --set ingress.enabled=true \\