# Team Highlights - 2026-07

Collaborative team accomplishments for July 2026.

## 2026-07-21: Recert Cert-Manager Integration Hardened — Full SAN Field Coverage Validated on Live Cluster

The CNF Cert Team closed a gap in recert's cert-manager Certificate CR handling where `spec.ipAddresses`, `spec.uris`, and `spec.emailAddresses` were not updated during IBU IP/domain rename — causing cert-manager to silently reissue certificates with stale values. Fix verified against a live OCP 4.x cluster confirming all 5 cert-manager Certificate spec fields are correctly handled. This complements the ongoing Ed25519, P-384, and EC PEM tag PRs (#1817, #1827, #1829) expanding recert's cryptographic algorithm coverage. [PR #1833](https://github.com/rh-ecosystem-edge/recert/pull/1833)

---

## 2026-07-08: Cert-Manager Hub-Spoke Trust Configuration Validated for Production

The CNF Cert Team validated the cert-manager hub-spoke trust implementation across OCP 4.21→4.22 with ACM 2.13, confirming zero-downtime certificate rotation without manual intervention. This validation de-risks production deployments by verifying the ConfigMap label fix enables seamless spoke reconnection during hub cert rollout and certificate rotation. [PR #773](https://github.com/openshift-kni/telco-reference/pull/773) | [Verification](https://gist.github.com/sebrandon1/bba27f3e662c16e62fb552ea24c90d02)

---

---

