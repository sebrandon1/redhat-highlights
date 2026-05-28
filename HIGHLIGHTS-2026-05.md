# Work Highlights - 2026-05

A reverse-chronological log of significant engineering accomplishments for May 2026.

---

## 2026-05-28: DCI Client v1.0.3 Quality & Reliability Overhaul - [go-dci](https://github.com/sebrandon1/go-dci)

Improved DCI API client reliability and maintainability through 12 PRs: added automatic retry with exponential backoff for transient failures, context-based request cancellation, and proper error exit codes. Increased test coverage from 18% to 85%, reduced client code by 21%, and added multi-arch container image releases to quay.io. [v1.0.3](https://github.com/sebrandon1/go-dci/releases/tag/v1.0.3) | [PR #114](https://github.com/sebrandon1/go-dci/pull/114) - [PR #125](https://github.com/sebrandon1/go-dci/pull/125)

---

## 2026-05-27: Certsuite v5.5.20 Release - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Published certsuite v5.5.20 with probe daemonset skip improvements, a per-node mutex bug fix for platform-alteration-base-image, and preflight 1.19.0 update. Includes 24 merged changes across features, bug fixes, and dependency updates. [v5.5.20](https://github.com/redhat-best-practices-for-k8s/certsuite/releases/tag/v5.5.20) | [CNFCERT-1420](https://redhat.atlassian.net/browse/CNFCERT-1420)

---

## 2026-05-27: OLM Annotation Linter v1.0.5 - [olm-annotation-lint](https://github.com/openshift-kni/olm-annotation-lint)

Strengthened Kubernetes operator validation by adding JSON, template, and semver range format checking to the OLM annotation linter, catching invalid annotations before they reach clusters. Also fixed exclude pattern bugs and added CLI short flags for faster developer workflows. [PR #19](https://github.com/openshift-kni/olm-annotation-lint/pull/19) | [PR #20](https://github.com/openshift-kni/olm-annotation-lint/pull/20) | [PR #21](https://github.com/openshift-kni/olm-annotation-lint/pull/21) | [v1.0.5](https://github.com/openshift-kni/olm-annotation-lint/releases/tag/v1.0.5)

---

## 2026-05-27: cert-manager Hub-Spoke Trust Validation - [telco-reference](https://github.com/openshift-kni/telco-reference)

Proved cert-manager's production viability for ACM hub-spoke deployments through 3 live ZTP tests on bare metal, resolving a reviewer blocker on the reference configuration. Key finding: greenfield deployments work automatically (ACM handles CA trust via ManifestWork), but brownfield adoption breaks existing spokes and requires cluster reimport. Documented the full trust flow mechanism and slimmed down the PR to address all reviewer concerns. [PR #773](https://github.com/openshift-kni/telco-reference/pull/773) | [MR !192](https://gitlab.cee.redhat.com/reference-configurations/reference-design-specifications/-/merge_requests/192) | [Test Results](https://gist.github.com/sebrandon1/483180614951d23174c4e365a9a02a34) | [OCPBUGS-85773](https://issues.redhat.com/browse/OCPBUGS-85773)

---

## 2026-05-26: go-quay Test Coverage from 0% to 85.5% - [go-quay](https://github.com/sebrandon1/go-quay)

Improved go-quay library reliability by adding 120 unit tests covering all previously untested code — client HTTP helpers, billing, and the 59-function organization package — plus error path tests for every lib function. Coverage rose from 0% (3 core files untested) to 85.5% across the entire library. Also added robot federation and registry capabilities endpoints, reaching 94.4% API coverage. [PR #100](https://github.com/sebrandon1/go-quay/pull/100) | [PR #103](https://github.com/sebrandon1/go-quay/pull/103) | [PR #105](https://github.com/sebrandon1/go-quay/pull/105) | [PR #106](https://github.com/sebrandon1/go-quay/pull/106) | [#104](https://github.com/sebrandon1/go-quay/issues/104)

---

## 2026-05-21: Quay.io CLI as Shared AI Skill - [go-quay](https://github.com/sebrandon1/go-quay)

Enabled AI assistants to manage Quay.io container registries through natural language by extending the go-quay CLI with log analysis, date filtering, container image publishing, and environment-based authentication, then packaging it as a shared AI skill for the team. Released v1.0.1-v1.0.3 with multi-arch images at `quay.io/bapalm/go-quay`. [PR #87](https://github.com/sebrandon1/go-quay/pull/87) | [PR #88](https://github.com/sebrandon1/go-quay/pull/88) | [PR #89](https://github.com/sebrandon1/go-quay/pull/89) | [PR #90](https://github.com/sebrandon1/go-quay/pull/90) | [PR #91](https://github.com/sebrandon1/go-quay/pull/91) | [MR !19](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/19) | [CNF-24115](https://redhat.atlassian.net/browse/CNF-24115)

---

## 2026-05-21: Reproducible Cert-Manager CI with Version Pinning - [cert-manager-scripts](https://github.com/sebrandon1/cert-manager-scripts)

Eliminated non-deterministic test results by pinning the cert-manager operator to a specific version (v1.19.0) and adding nightly CI that matrices across operator and OCP versions. Automated weekly version detection creates bump PRs, preventing manual tracking. Extracted shared CI into a reusable workflow, reducing duplication by 150+ lines. [PR #32](https://github.com/sebrandon1/cert-manager-scripts/pull/32)

---

## 2026-05-19: New TLS Audit Skill with Cross-Scanner Comparison - [shared-ai-skills](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills)

Created an interactive TLS auditing skill that provides a full compliance dashboard — compliance status, Post-Quantum Cryptography (PQC) readiness, certificate health, cipher grades, and forward secrecy — with drill-down analysis and remediation guidance. Includes cross-comparison between tls-compliance-operator and tls-scanner for ground-truth validation. Tested on OCP 4.22 scanning 104 endpoints. [MR !18](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/18) | [CNF-24072](https://redhat.atlassian.net/browse/CNF-24072)

---

## 2026-05-19: TLS Compliance Operator — 3 Releases Fixing OCP Compatibility - [tls-compliance-operator](https://github.com/sebrandon1/tls-compliance-operator)

Shipped three releases (v1.0.7–v1.0.9) fixing critical OpenShift deployment blockers: eliminated Security Context Constraint (SCC) failures preventing pod startup, reduced hostname match false positives from 63 to 8 by adding Kubernetes DNS suffix resolution, and expanded TLS port discovery from 7 to 18 ports covering kubelet, kube-apiserver, Prometheus, and etcd. [PR #164](https://github.com/sebrandon1/tls-compliance-operator/pull/164) | [PR #165](https://github.com/sebrandon1/tls-compliance-operator/pull/165) | [PR #166](https://github.com/sebrandon1/tls-compliance-operator/pull/166)

---

## 2026-05-14: Cert-Manager Certificate Preservation Backported to OCP 4.20/4.21 - [recert](https://github.com/rh-ecosystem-edge/recert) / [lifecycle-agent](https://github.com/openshift-kni/lifecycle-agent)

Backported cert-manager TLS certificate preservation to OCP 4.20 and 4.21 release branches, enabling Image-Based Upgrade (IBU) to maintain key continuity for addon certificates managed by cert-manager. Without this, cert-manager reissues certificates with new keys post-upgrade, breaking continuity. Four PRs across both recert and lifecycle-agent repos. [recert #1516](https://github.com/rh-ecosystem-edge/recert/pull/1516) | [recert #1517](https://github.com/rh-ecosystem-edge/recert/pull/1517) | [LCA #6633](https://github.com/openshift-kni/lifecycle-agent/pull/6633) | [LCA #6634](https://github.com/openshift-kni/lifecycle-agent/pull/6634) | [CNF-21564](https://redhat.atlassian.net/browse/CNF-21564)

---

## 2026-05-13: OLM Annotation Linter Prevents Silent Misconfigurations - [olm-annotation-lint](https://github.com/openshift-kni/olm-annotation-lint) / [telco-reference](https://github.com/openshift-kni/telco-reference)

Discovered an invalid OLM annotation silently ignored across 6 telco-reference config files since December 2025. Built and released [olm-annotation-lint](https://github.com/openshift-kni/olm-annotation-lint) v1.0.0 — a reusable GitHub Action that validates all OLM annotations against the upstream source of truth, catching unknown, misspelled, or misused annotations before they reach clusters. Integrated into telco-reference CI to prevent recurrence. [PR #759](https://github.com/openshift-kni/telco-reference/pull/759) | [PR #760](https://github.com/openshift-kni/telco-reference/pull/760) | [CNF-23812](https://redhat.atlassian.net/browse/CNF-23812)

---

## 2026-05-13: Shared ZTP Toolkit — 4 New Skills for Lab Management - [shared-ai-skills](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills)

Published four reusable Zero Touch Provisioning (ZTP) skills to the team's shared AI plugin marketplace, giving any team member self-service access to hub credential extraction, spoke cluster health monitoring, policy compliance checking, and Redfish BMC management. Completes a 6-skill ZTP toolkit (with the previously shared ztp-reprovision and ci-watch). [MR !9](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/9) | [MR !10](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/10) | [MR !11](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/11) | [MR !12](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/12)

---

## 2026-05-13: Completed Certsuite-to-Skills Epic — 98 Tests Covered - [prodsec-skills](https://github.com/RedHatProductSecurity/prodsec-skills)

Completed the full CNFCERT-1405 epic converting certsuite test requirements into 8 new prodsec-skills and 2 existing skill extensions, covering 98 of 121 certsuite tests across 10 suites. Two PRs merged (health-probes, container-hardening), 8 more open for review. Developers can now get pre-emptive guidance on probes, RBAC, capabilities, networking, observability, CPU performance, and platform integrity while writing Kubernetes manifests. [CNFCERT-1405](https://redhat.atlassian.net/browse/CNFCERT-1405) | PRs [#8](https://github.com/RedHatProductSecurity/prodsec-skills/pull/8)-[#17](https://github.com/RedHatProductSecurity/prodsec-skills/pull/17)

---

## 2026-05-13: Fix cert-manager Install on Console-less Clusters - [cert-manager-operator](https://github.com/openshift/cert-manager-operator)

Fixed a bug blocking cert-manager operator installation on clusters without the Console capability (e.g., RAN Reference Design Specification deployments). Three `ConsoleYAMLSample` bundle resources were missing the `capability.openshift.io/name: Console` annotation, causing OLM to fail when the Console CRD was absent. [PR #424](https://github.com/openshift/cert-manager-operator/pull/424) | [CNF-23785](https://redhat.atlassian.net/browse/CNF-23785)

---

## 2026-05-12: Shared CI Monitoring Skill - [shared-ai-skills](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills)

Published a reusable CI monitoring skill to the team's shared AI plugin marketplace, enabling any team member to watch GitHub pull request checks until completion with automatic failure diagnosis and suggested fixes. Reduces context-switching by letting the AI agent handle CI polling. [MR !8](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/8)

---

## 2026-05-12: Upstream RHCOS Hardening PR Accepted for Review - [rhel-coreos-config](https://github.com/coreos/rhel-coreos-config)

Submitted the first upstream hardening PR to the CoreOS base layer, adding authselect's `without-nullok` flag to disable empty password authentication in all RHCOS images. CoreOS maintainer confirmed the approach is valid and redirected from openshift/os to the base config repo for broader impact across Fedora and RHEL CoreOS. If merged, eliminates a HIGH severity compliance finding for every OCP cluster without per-node remediation. [PR #255](https://github.com/coreos/rhel-coreos-config/pull/255) | [CNF-21212](https://redhat.atlassian.net/browse/CNF-21212)

---

## 2026-05-12: Self-Signed CA and Monitoring for Disconnected Cert-Manager - [cert-manager-scripts](https://github.com/sebrandon1/cert-manager-scripts)

Enabled cert-manager testing in disconnected/air-gapped environments by adding self-signed Certificate Authority (CA) issuer support and Prometheus monitoring with four production-ready alerts. Provides reference configurations for RDS Core deployments where external ACME servers are unreachable, unblocking QE lab testing. [PR #29](https://github.com/sebrandon1/cert-manager-scripts/pull/29) | [PR #31](https://github.com/sebrandon1/cert-manager-scripts/pull/31)

---

## 2026-05-12: Structured Logging and Policy Hardening for TLS Scanner - [tls-scanner](https://github.com/openshift/tls-scanner)

Replaced ad-hoc logging across 14 files with Go's stdlib `log/slog` structured logging, enabling operators to filter scan output by level (`--log-level debug|info|warn|error`) and integrate with log aggregation systems. Also eliminated panics in policy parsing, preventing scanner crashes on malformed configuration. Consolidated from two PRs into one for cleaner review. [PR #60](https://github.com/openshift/tls-scanner/pull/60) | [CNF-23702](https://redhat.atlassian.net/browse/CNF-23702) | [CNF-23701](https://redhat.atlassian.net/browse/CNF-23701)

---

## 2026-05-12: Shared ZTP Reprovisioning Skill - [shared-ai-skills](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills)

Published a reusable Zero Touch Provisioning (ZTP) reprovisioning skill to the team's shared AI plugin marketplace, enabling any team member to safely tear down and rebuild spoke clusters through the Advanced Cluster Management/ArgoCD pipeline with guided confirmations and automated monitoring. [MR !6](https://gitlab.cee.redhat.com/telco-ai-projects/shared-ai-skills/-/merge_requests/6) | [CNF-23737](https://redhat.atlassian.net/browse/CNF-23737)

---

## 2026-05-11: Doubled E2E Coverage and Halved CI Time - [tls-compliance-operator](https://github.com/sebrandon1/tls-compliance-operator)

Expanded end-to-end test coverage from 13 to 21 scenarios with balanced positive/negative validation of TLS compliance reporting, then restructured CI into parallel matrix jobs cutting E2E execution from 21 minutes to 10 minutes. Each test group now shows as a separate PR check for immediate failure visibility. [PR #152](https://github.com/sebrandon1/tls-compliance-operator/pull/152) | [PR #155](https://github.com/sebrandon1/tls-compliance-operator/pull/155)

---

## 2026-05-12: Certsuite Best Practices as Proactive Developer Skills - [prodsec-skills](https://github.com/RedHatProductSecurity/prodsec-skills)

Established cross-team collaboration with Product Security to convert certsuite test requirements into pre-emptive AI-assisted developer guidance. Merged the first skill (health probes) covering 9 certsuite tests, with a roadmap for 10 skills covering 98 of 121 tests. Enables developers to build compliant workloads from the start instead of fixing failures after certification. [PR #4](https://github.com/RedHatProductSecurity/prodsec-skills/pull/4) | [CNFCERT-1405](https://redhat.atlassian.net/browse/CNFCERT-1405) | [CNFCERT-1406](https://redhat.atlassian.net/browse/CNFCERT-1406)

---

## 2026-05-08: TLS Compliance Operator Feature Sprint - [tls-compliance-operator](https://github.com/sebrandon1/tls-compliance-operator)

Shipped 8 improvements to the tls-compliance-operator across bug fixes, new features, testing, and documentation. Fixed reconciler concurrency and context cancellation bugs, added certificate hostname mismatch detection, kubectl plugin filters (PQC readiness, cert expiry), sort-by and markdown export capabilities, comprehensive env var configuration, and a full configuration reference guide. Published blog posts on both palmsoftware.org and the Red Hat engineering blog showcasing real-world cluster visibility with PQC readiness data from OCP 4.22. [PR #141](https://github.com/sebrandon1/tls-compliance-operator/pull/141) | [PR #142](https://github.com/sebrandon1/tls-compliance-operator/pull/142) | [PR #143](https://github.com/sebrandon1/tls-compliance-operator/pull/143) | [PR #144](https://github.com/sebrandon1/tls-compliance-operator/pull/144) | [PR #145](https://github.com/sebrandon1/tls-compliance-operator/pull/145) | [PR #146](https://github.com/sebrandon1/tls-compliance-operator/pull/146) | [PR #147](https://github.com/sebrandon1/tls-compliance-operator/pull/147) | [PR #148](https://github.com/sebrandon1/tls-compliance-operator/pull/148)

---

## 2026-05-08: Certsuite Quality and Usability Improvements - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Improved certsuite reliability and developer experience across 4 PRs: made the Kubernetes client timeout configurable to unblock remote cluster testing, fixed incorrect SIGKILL guidance in check descriptions, documented 13 previously undocumented CLI flags, and removed 11 dead code declarations across 7 files. [PR #3629](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3629) | [PR #3630](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3630) | [PR #3632](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3632)

---

## 2026-05-07: Parallelized Test Execution Saves 3 Hours Per CI Run - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Reduced nightly QE test execution time by 34% (558 min to 367 min) by parallelizing 13 I/O-heavy test functions with bounded concurrency. Networking suites alone dropped from 50 minutes to 28 minutes. Saves over 3 hours of CI compute per nightly run with zero test result regressions. [PR #3611](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3611) | [CNFCERT-1404](https://redhat.atlassian.net/browse/CNFCERT-1404)

---

## 2026-05-06: Standardized AI Tooling Across 5 Repositories - [sebrandon1](https://github.com/sebrandon1)

Added CLAUDE.md configuration files to 5 repositories lacking AI assistant context, enabling consistent Claude Code workflows across the portfolio. Covers build commands, linting, architecture, and project conventions so contributors get accurate, repo-aware assistance immediately. [bps-operator #92](https://github.com/sebrandon1/bps-operator/pull/92) | [ibu-test-harness #4](https://github.com/sebrandon1/ibu-test-harness/pull/4) | [openclaw-brain #1](https://github.com/sebrandon1/openclaw-brain/pull/1) | [security-fruit #1](https://github.com/sebrandon1/security-fruit/pull/1) | [traffic #1](https://github.com/sebrandon1/traffic/pull/1)

---

## 2026-05-06: Strengthened CI Quality Gates for Telco Reference - [telco-reference](https://github.com/openshift-kni/telco-reference)

Expanded CI validation coverage for the telco reference configuration repository by adding yamllint for 150+ previously unchecked RAN YAML files and introducing ShellCheck validation for 31 shell scripts via GitHub Actions. Fixed all pre-existing lint errors across source CRs and kube-compare references. These checks catch configuration defects before they reach production deployments. [PR #744](https://github.com/openshift-kni/telco-reference/pull/744) | [PR #745](https://github.com/openshift-kni/telco-reference/pull/745) | [CNF-23578](https://redhat.atlassian.net/browse/CNF-23578)

---

## 2026-05-06: Improved Error Diagnostics Across Certsuite - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Improved debuggability of certification test failures by wrapping 40+ bare error returns with actionable context across 12 files. Engineers investigating failures now see which specific Kubernetes operation failed (e.g., "failed to get deployment ns/name") instead of generic messages, reducing triage time. [PR #3627](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3627)

---

## 2026-05-05: Improved Dependency Update Grouping - [imagecertinfo-operator](https://github.com/sebrandon1/imagecertinfo-operator)

Streamlined Kubernetes dependency management by adding `sigs.k8s.io/controller-runtime` to the Dependabot grouping configuration. Ensures controller-runtime updates are batched with other Kubernetes dependencies, reducing PR noise and preventing version drift between tightly coupled packages. [PR #103](https://github.com/sebrandon1/imagecertinfo-operator/pull/103)

---

## 2026-05-05: Engaging RHCOS Team on Upstream Hardening - [openshift/os](https://github.com/openshift/os)

Initiated upstream discussions with the CoreOS team about shipping security hardening defaults in RHCOS base images. Identified 8 low-risk sysctl, PAM, and kernel boot argument changes that would eliminate MachineConfig remediation for all OCP clusters. Discovered that `authselect` already has a purpose-built `without-nullok` feature (added by Red Hat in 2018) that RHCOS could activate with a one-liner. Created proof-of-concept branches on [sebrandon1/os](https://github.com/openshift/os/compare/master...sebrandon1:os:hardening/pam-no-empty-passwords). [CNF-21212](https://redhat.atlassian.net/browse/CNF-21212)

---

## 2026-05-05: Stabilized CI Across 6 Repositories - [oct](https://github.com/redhat-best-practices-for-k8s/oct) / [collector](https://github.com/redhat-best-practices-for-k8s/collector) / [certsuite-operator](https://github.com/redhat-best-practices-for-k8s/certsuite-operator) / [ztp-dashboard](https://github.com/sebrandon1/ztp-dashboard)

Unblocked CI pipelines across 6 repositories by pinning golangci-lint to v2.12.1 and resolving lint violations introduced by the latest release. Prevented ongoing developer disruption from false failures affecting 14+ retriggered PR checks. [oct #439](https://github.com/redhat-best-practices-for-k8s/oct/pull/439) | [collector #683](https://github.com/redhat-best-practices-for-k8s/collector/pull/683) | [certsuite-operator #308](https://github.com/redhat-best-practices-for-k8s/certsuite-operator/pull/308) | [ztp-dashboard #76](https://github.com/sebrandon1/ztp-dashboard/pull/76)

---

## 2026-05-05: Verified 30 Compliance Hardening Groups - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts) / [telco-reference](https://github.com/openshift-kni/telco-reference)

Achieved 84.9% compliance coverage (up from 37.7%) by verifying 30 hardening groups across E8, CIS, Moderate, and PCI-DSS profiles on OCP 4.22. Created 20 new remediation branches, 32 Jira stories across two epics ([CNF-22573](https://redhat.atlassian.net/browse/CNF-22573), [CNF-23530](https://redhat.atlassian.net/browse/CNF-23530)), and a live [compliance dashboard](https://sebrandon1.github.io/compliance-scripts/) tracking all 40 groups. RHCOS E8 profile now fully compliant.

---

## 2026-05-04: Released quick-k8s v0.0.66 - [quick-k8s](https://github.com/palmsoftware/quick-k8s)

Released v0.0.66 of the quick-k8s GitHub Action, updating Calico CNI to v3.32.0. This keeps the CI/CD Kubernetes testing infrastructure current with the latest network policy engine, ensuring teams validate against production-aligned networking behavior. [Release v0.0.66](https://github.com/palmsoftware/quick-k8s/releases/tag/v0.0.66)

---

## 2026-05-01: Eliminated Hardcoded Protocol Strings - [commatrix](https://github.com/openshift-kni/commatrix)

Reduced risk of silent misconfigurations by centralizing ~138 hardcoded protocol string literals into typed constants across 9 files. Prevents typos in firewall rule generation where a single wrong character could block legitimate cluster traffic. [PR #487](https://github.com/openshift-kni/commatrix/pull/487) | [CNF-23435](https://redhat.atlassian.net/browse/CNF-23435)

---

## 2026-05-01: Simplified Cert-Manager Policy Rollout - [telco-reference](https://github.com/openshift-kni/telco-reference)

Consolidated cert-manager configuration from a standalone policy into the base overlay policy, reducing policy count and enabling faster, simpler rollout for telco core deployments. Aligns with team guidance to keep overlay config in a single policy for consistency. [PR #732](https://github.com/openshift-kni/telco-reference/pull/732) | [CNF-21719](https://redhat.atlassian.net/browse/CNF-21719)

---

## 2026-05-01: Unit Test Coverage for Critical Packages - [commatrix](https://github.com/openshift-kni/commatrix)

Added 38 unit tests across two previously untested core packages: `pkg/utils` (440+ lines of cluster introspection and pod management) and `pkg/matrix-diff` (critical diff logic for communication matrix comparison). Reduces regression risk in code that gates firewall policy generation. [PR #485](https://github.com/openshift-kni/commatrix/pull/485) | [PR #486](https://github.com/openshift-kni/commatrix/pull/486) | [CNF-23406](https://redhat.atlassian.net/browse/CNF-23406) | [CNF-23416](https://redhat.atlassian.net/browse/CNF-23416)

---
