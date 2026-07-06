# NetworkPolicy (Cluster Setup)

Most-tested CKS topic. L3/L4 allow-list firewall for pods. Namespaced, additive, needs an enforcing CNI (Calico/Cilium; not plain Flannel).

## Core rules
- Default (no policy): all pods talk to all pods.
- A pod becomes "isolated" for a direction the moment **any** policy selects it via `podSelector`; then only explicit `from`/`to` allows get through.
- `policyTypes` listed with **no matching rules** = deny that direction entirely.
- `podSelector: {}` = every pod in the namespace.

## Default-deny-all (memorize)
```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata: {name: default-deny-all, namespace: prod}
spec:
  podSelector: {}
  policyTypes: [Ingress, Egress]
```

## AND vs OR trap
Selectors in the **same** `- from` item = AND. Separate `-` items = OR.
```yaml
ingress:
- from:
  - namespaceSelector: {matchLabels: {team: blue}}   # AND
    podSelector: {matchLabels: {role: api}}
# ---
- from:
  - namespaceSelector: {matchLabels: {team: blue}}   # OR (item 1)
  - podSelector: {matchLabels: {role: api}}           # OR (item 2)
```

## Same vs cross namespace
- Same ns: `podSelector` alone (namespace implied — NOT "all namespaces").
- Cross ns: must add `namespaceSelector`.

## Docs (exam-allowed)
kubernetes.io/docs → "Network Policies". Copy the default-deny + selector examples straight from there.

---
**Weak spot flagged:** writing NetworkPolicy YAML from memory → Gear-2 drill.
