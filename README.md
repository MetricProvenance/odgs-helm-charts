# ODGS Helm Charts (The Vending Machine)

Welcome to the **Metric Provenance ODGS Helm Repository**. This repository hosts the public Helm chart releases for the Open Data Governance Standard (ODGS) Universal Validation Engine.

> **Note:** This repository is strictly a static Helm repository (The "Vending Machine"). It only contains `.tgz` artifacts and an `index.yaml` mapping file. The source code and build pipelines are kept privately by Metric Provenance.

## 🚀 Installation

To deploy the ODGS Validation Engine on your Kubernetes cluster, add this repository to your local Helm client:

```bash
# 1. Add the Metric Provenance Helm repository
helm repo add metricprovenance https://MetricProvenance.github.io/odgs-helm-charts/

# 2. Update your local Helm cache
helm repo update

# 3. Install the Engine (Community/Showcase Edition)
helm install odgs-engine metricprovenance/odgs-engine
```

## ⚙️ Configuration

You can customize the deployment by inspecting the default values or requesting the official `values.yaml` from your Metric Provenance integration specialist. 

To upgrade an existing installation:
```bash
helm upgrade odgs-engine metricprovenance/odgs-engine --version 4.0.0
```

## 🛒 Commercial Law Packs (S-Cert)

For enterprise clusters mounting proprietary Law Packs (e.g., EU AI Act, FIBO, Basel IV) bounded to Semantic Certificates (`urn:odgs:sov:*`), ensure you configure your PVC mounts in `values.yaml` before deployment:

```yaml
lawPacks:
  enabled: true
  existingClaim: "odgs-law-packs-pvc"
```

Please consult the [Metric Provenance Enterprise Portal](https://platform.metricprovenance.com) for architectural clearance and to license Sovereign Law Packs.
