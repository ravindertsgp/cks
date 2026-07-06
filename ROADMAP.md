# CKS Prep Roadmap

**Candidate:** ravindert · **CKA:** active · **Level:** strong k8s · **Pace:** 8+ weeks, relaxed · **Style:** concepts-first, labs layered in
**Exam:** 2h, performance-based, 15–16 tasks, pass ≥ ~66%, **k8s v1.35** (env tracks latest minor ~4–8 wks post-release), curriculum **v1.34** (cncf/curriculum), open-book (kubernetes.io/docs, k8s GitHub, Falco/Trivy/AppArmor docs)
**Sourcing rule:** teach only from current official docs (kubernetes.io, cncf/curriculum, Falco/Trivy/AppArmor). Verify versions; never teach from stale memory.
**Method:** interactive teach→check loop. Gear 1 = fast full-curriculum sweep to reactivate + surface weak spots; Gear 2 = depth/drills/timed mocks on the gaps.

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
| 1 | Cluster Setup | NetworkPolicy deep-dive, Ingress TLS, kube-bench/CIS, API server flags, kubelet hardening | ◑ swept |
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

## Weak spots (Gear-2 drill targets)
- Writing NetworkPolicy YAML from memory (concepts solid, syntax rusty)
- TLS secret trivia: type `kubernetes.io/tls`, keys `tls.crt`/`tls.key` (lookup-able)
- Node authorizer vs RBAC distinction — reinforced, recheck later

## Strengths observed
- NetworkPolicy AND/OR selector logic — solid
- Static-pod edit workflow (no `apply`, kubelet reconciles) — solid
- Ingress pathType Prefix/Exact — solid

## Progress log
- 2026-07-06 — Kickoff. Profile set. Roadmap created.
- 2026-07-06 — Verified curriculum vs official sources (k8s v1.35, curriculum v1.34, pass ~66%).
- 2026-07-06 — Gear-1 sweep of Domain 1 (Cluster Setup) complete: NetworkPolicy, Ingress TLS, kube-bench/CIS, API server + kubelet hardening.
