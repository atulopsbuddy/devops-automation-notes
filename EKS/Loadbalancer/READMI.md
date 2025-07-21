# 🚀 EKS Deployment with Public LoadBalancer

This repo contains everything you need to:

- Deploy an app to EKS
- Expose it via a public AWS NLB (type: LoadBalancer)
- Tag subnets correctly for AWS ELB provisioning
- Verify deployment access

---

## 📂 Files

- `setup.yaml`: All required Kubernetes resources and subnet setup steps.

---

## 🛠️ How to Use

### 1. Apply the Kubernetes Resources

```bash
kubectl apply -f setup.yaml
