# 🏗️ GitOps Infrastructure Repository

This repository manages the Kubernetes cluster infrastructure and FluxCD configuration for my GitOps deployment pipeline.

## 📁 Repository Structure

```
GitOps_Infra/
├── clusters/
│ └── dev/
│ ├── flux-system/
│ │ ├── gotk-components.yaml
│ │ ├── gotk-sync.yaml
│ │ └── kustomization.yaml
│ ├── app-repo-source.yaml
│ ├── image-update.yaml
│ └── kustomization.yaml
├── infrastructure/
│ └── dev/
│ ├── ingress.yaml
│ ├── kustomization.yaml
│ └── namespace.yaml
└── README.md
```

## 🔄 How It Works

1. **FluxCD Management**: This repository is the source of truth for my cluster state
2. **Infrastructure Configuration**: Manages namespaces, ingress, and other infrastructure components
3. **App Deployment**: References the `GitOps_Apps` repository to deploy applications
4. **Image Automation**: Automatically updates application images when new versions are available

## 🚀 Bootstrap FluxCD

To bootstrap FluxCD with this infrastructure repository:

```bash
flux bootstrap github \
  --owner=Balen-Dev \
  --repository=GitOps_Infra \
  --branch=main \
  --path=clusters/dev \
  --personal
```

## 🔗 Related Repository

- [GitOps_Apps](https://github.com/Balen-Dev/GitOps_Apps) - Application Configurations and source code
