# CKS Prep Roadmap

**Candidate:** ravindert · **CKA:** active · **Level:** strong k8s · **Pace:** 8+ weeks, relaxed · **Style:** concepts-first, labs layered in
**Exam:** 2h, performance-based, 15–16 tasks, pass ≥ 67%, k8s ~v1.32/1.33, open-book (kubernetes.io/docs, k8s GitHub, Falco/Trivy/AppArmor docs)

## Domain weights
- Cluster Setup — 15%
- Cluster Hardening — 15%
- System Hardening — 10%
- Minimize Microservice Vulnerabilities — 20%
- Supply Chain Security — 20%
- Monitoring, Logging & Runtime Security — 20%

## 8-week plan (1 module per ~week, adjustable)

| Wk | Module | Focus | Status |
|----|--------|-------|--------|
| 1 | Cluster Setup | NetworkPolicy deep-dive, Ingress TLS, kube-bench/CIS, API server flags, kubelet hardening | ☐ |
| 2 | Cluster Hardening | RBAC (least privilege), ServiceAccounts, restrict API access, k8s upgrade, anonymous auth | ☐ |
| 3 | System Hardening | AppArmor, seccomp, minimize host footprint, kernel modules, IAM/privilege reduction | ☐ |
| 4 | Microservice Vulns I | Pod Security Standards & Admission, security contexts, secrets management | ☐ |
| 5 | Microservice Vulns II | Sandboxing (gVisor/runtimeClass, Kata), mTLS, OPA/Gatekeeper or Kyverno | ☐ |
| 6 | Supply Chain Security | Trivy image scanning, minimize base images, ImagePolicyWebhook, SBOM, image signing | ☐ |
| 7 | Monitoring & Runtime | Falco rules, audit logging (policy + backend), immutability, behavioral detection | ☐ |
| 8 | Consolidation | Timed mock exams, weak-spot drills, docs-navigation speed, kubectl efficiency | ☐ |

## Cross-cutting exam skills (drilled throughout)
- Fast docs navigation within allowed sites
- `kubectl` speed: aliases, `--dry-run=client -o yaml`, `-o jsonpath`, `explain`
- Context switching between clusters; always confirm `kubectl config use-context`
- Read the task's namespace/cluster carefully; verify your change actually took effect

## Progress log
- 2026-07-06 — Kickoff. Profile set. Roadmap created.
