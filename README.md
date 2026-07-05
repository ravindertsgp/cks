# CKS Prep

My study repo for the **Certified Kubernetes Security Specialist (CKS)** exam.
Concepts, exam-style YAML, lab manifests, and mock exams — built module by module.

See [ROADMAP.md](./ROADMAP.md) for the full plan and progress tracker.

## Layout

| Path | Contents |
|------|----------|
| `01-cluster-setup/` | NetworkPolicy, Ingress TLS, kube-bench/CIS, API server & kubelet hardening |
| `02-cluster-hardening/` | RBAC, ServiceAccounts, restrict API access, upgrades |
| `03-system-hardening/` | AppArmor, seccomp, host/kernel hardening |
| `04-microservice-vulns/` | Pod Security Standards, security contexts, secrets, sandboxing (gVisor), mTLS, admission (OPA/Kyverno) |
| `05-supply-chain/` | Trivy scanning, minimal base images, ImagePolicyWebhook, SBOM, signing |
| `06-monitoring-runtime/` | Falco, audit logging, immutability, runtime detection |
| `labs/` | Reproducible hands-on labs (kind cluster setup, exercises) |
| `mock-exams/` | Timed practice exams and answer keys |

## Exam quick facts
- Hands-on, 2h, ~15–16 tasks, pass **≥ 67%**, k8s ~v1.32/1.33
- Prereq: active CKA · Open-book: kubernetes.io/docs, k8s GitHub, Falco/Trivy/AppArmor docs

## Efficiency setup (drill this)
```bash
alias k=kubectl
export do="--dry-run=client -o yaml"
export now="--force --grace-period=0"
source <(kubectl completion bash)
complete -o default -F __start_kubectl k
```
