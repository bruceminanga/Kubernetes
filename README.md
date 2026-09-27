# Reusable Kubernetes Manifests

> A collection of modular, production-grade Kubernetes base templates and overlays for standard application deployments.

---

## 🚀 Features

- **Environment-agnostic:** Designed for seamless multi-environment configuration (Dev, Staging, Prod).
- **Security-first:** Includes non-root security contexts, resource requests/limits, and read-only root filesystems by default.
- **Batteries included:** Ready-made configurations for Ingress, Horizontal Pod Autoscalers (HPA), and ConfigMaps.

## 🛠 Tech Stack & Prerequisites

- Kubernetes `v1.28+`
- [Kustomize](https://kustomize.io/) (built into `kubectl`)



## ⚡ Quickstart

### 1. Dry Run / Verify Manifests
Render and validate the generated manifests locally before applying:

```bash
kubectl kustomize overlays/prod | kubectl apply --dry-run=client -f -
```

### 2. Deploy an Environment
Apply the desired overlay directly to your cluster:

```bash
# Deploy to Dev
kubectl apply -k overlays/dev

# Deploy to Prod
kubectl apply -k overlays/prod
```

## ⚙️ How to Customize

1. **Clone the repository:**
   ```bash
   git clone https://github.com/git@github.com:bruceminanga/Kubernetes.git
   cd Kubernetes
   ```

2. **Update your configuration:**
   Edit the `kustomization.yaml` inside your target overlay directory (`overlays/dev` or `overlays/prod`) to customize:
   - Container image name and tags
   - Replica counts
   - Environment variables or secrets

3. **Deploy your changes:**
   ```bash
   kubectl apply -k overlays/<environment>
   ```

