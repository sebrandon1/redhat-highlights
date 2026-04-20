# Work Highlights - 2026-04

A reverse-chronological log of significant engineering accomplishments for April 2026.

---

## 2026-04-20: BPS Operator Release Readiness - [bps-operator](https://github.com/sebrandon1/bps-operator)

Accelerated the Best Practices Scanner operator toward production readiness by boosting test coverage from 49% to 65%, automating the release pipeline (single-command tag-to-release-to-image), and adding automatic result cleanup to prevent unbounded Custom Resource growth in long-running deployments. Cleaned up 18 stale branches. [PR #84](https://github.com/sebrandon1/bps-operator/pull/84), [PR #85](https://github.com/sebrandon1/bps-operator/pull/85), [PR #86](https://github.com/sebrandon1/bps-operator/pull/86), [CNF-23058](https://issues.redhat.com/browse/CNF-23058), [CNF-23059](https://issues.redhat.com/browse/CNF-23059), [CNF-23060](https://issues.redhat.com/browse/CNF-23060)

---

## 2026-04-20: Cert-Manager Certificate Preservation for Image-Based Upgrades - [recert](https://github.com/rh-ecosystem-edge/recert), [lifecycle-agent](https://github.com/openshift-kni/lifecycle-agent)

Unblocked the 4.22 epic for testing by delivering coordinated changes across two repos that preserve cert-manager TLS certificates during Image-Based Upgrades (IBU). Eliminates post-upgrade certificate reissuance that broke key continuity, ensuring addon certificates survive cluster upgrades intact. Validated end-to-end on OCP 4.20→4.21 with cert-manager v1.17.2. [recert #1192](https://github.com/rh-ecosystem-edge/recert/pull/1192), [lifecycle-agent #5174](https://github.com/openshift-kni/lifecycle-agent/pull/5174), [CNF-21719](https://issues.redhat.com/browse/CNF-21719)

---

## 2026-04-20: Jira Tracking for ioutil Deprecation Campaign - [cluster-samples-operator](https://github.com/openshift/cluster-samples-operator)

Created 10 CNF Jira stories to track deprecated `io/ioutil` migration efforts across 10 OpenShift repositories, providing traceability for PRs that previously had no issue tracking. Updated all PR titles with Jira references to satisfy OpenShift CI requirements. [CNF-23044](https://issues.redhat.com/browse/CNF-23044) through [CNF-23053](https://issues.redhat.com/browse/CNF-23053), [tracking issue #52](https://github.com/redhat-best-practices-for-k8s/telco-bot/issues/52)

---

## 2026-04-20: Cluster Monitoring Support for CI Pipelines - [quick-ocp](https://github.com/palmsoftware/quick-ocp)

Enabled CI pipelines to deploy OpenShift with the full monitoring stack (Prometheus, Alertmanager) by adding an `enableClusterMonitoring` option to the quick-ocp GitHub Action. Automatically enforces minimum memory requirements, preventing silent deployment failures. Teams testing monitoring-dependent workloads can now validate in CI instead of manual clusters. [PR #51](https://github.com/palmsoftware/quick-ocp/pull/51), [CNFCERT-1394](https://issues.redhat.com/browse/CNFCERT-1394)

---

## 2026-04-17: Cert-Manager Test Scripts Consolidation - [cert-manager-scripts](https://github.com/sebrandon1/cert-manager-scripts)

Reduced maintenance burden across 32 cert-manager automation scripts by consolidating ~1,000 lines of duplicated code into a shared library with 8 reusable functions. Fixed inefficient API call patterns (21 calls to 1) and replaced custom polling loops with native OpenShift tooling. Released as [v0.0.6](https://github.com/sebrandon1/cert-manager-scripts/releases/tag/v0.0.6). [PR #26](https://github.com/sebrandon1/cert-manager-scripts/pull/26)

---

## 2026-04-17: Compliance Scripts Code Quality Overhaul - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts)

Improved maintainability of 28 OpenShift compliance automation scripts by consolidating duplicated code into a shared library, rewriting the README for user-friendliness, and conducting a full codebase audit. Eliminated 239 lines of redundant logging, role detection, and polling logic across 27 files. Released as [v1.0.3](https://github.com/sebrandon1/compliance-scripts/releases/tag/v1.0.3). [PR #89](https://github.com/sebrandon1/compliance-scripts/pull/89), [PR #90](https://github.com/sebrandon1/compliance-scripts/pull/90)

---

## 2026-04-17: GolangCI-Lint v2 Upgrade Campaign - [telco-bot](https://github.com/redhat-best-practices-for-k8s/telco-bot)

Modernized linting infrastructure across 6 OpenShift repositories by upgrading golangci-lint from v2.0.2 to v2.11.4, rebasing stale PRs, and fixing 55 newly-surfaced lint violations in cluster-image-registry-operator. Reduces static analysis gaps and aligns repos with current tooling standards. [Tracking issue #49](https://github.com/redhat-best-practices-for-k8s/telco-bot/issues/49), [backplane-tools #84](https://github.com/openshift/backplane-tools/pull/84), [cluster-image-registry-operator #1279](https://github.com/openshift/cluster-image-registry-operator/pull/1279), [telemeter #576](https://github.com/openshift/telemeter/pull/576), [zero-trust-workload-identity-manager #90](https://github.com/openshift/zero-trust-workload-identity-manager/pull/90), [ingress-node-firewall #692](https://github.com/openshift/ingress-node-firewall/pull/692), [cloud-provider-powervs #92](https://github.com/openshift/cloud-provider-powervs/pull/92)

---

## 2026-04-17: Restored Slack Team Notifications - [telco-bot](https://github.com/redhat-best-practices-for-k8s/telco-bot)

Fixed the broken weekly Jira team update that had been failing silently, restored visibility into team workload across 10 engineers. Upgraded all 4 Slack notification scripts (DCI stats, Quay pulls, Jira updates, x/crypto security) with improved formatting, error handling, and new metrics like migration percentage and outdated dependency rates. Created a shared notification library to reduce duplication. [PR #132](https://github.com/redhat-best-practices-for-k8s/telco-bot/pull/132)

---

## 2026-04-16: New Informational Config Category for RAN Hardening - [telco-reference](https://github.com/openshift-kni/telco-reference)

Introduced a new "informational" configuration category to the RAN Reference Design Specification (RDS), enabling security hardening configs to be shared as warn-only guidance rather than required or optional. Migrated 28 compliance branches to the new directory structure, fixed CI validation, and updated SSHD hardening to a drop-in approach verified with compliance-operator v1.8.2. [PR #529](https://github.com/openshift-kni/telco-reference/pull/529), [PR #466](https://github.com/openshift-kni/telco-reference/pull/466), [RDS MR !184](https://gitlab.cee.redhat.com/reference-configurations/reference-design-specifications/-/merge_requests/184), [CNF-19031](https://issues.redhat.com/browse/CNF-19031)

---

## 2026-04-15: Prebuilt Image for QE CI Pipelines - [bps-operator](https://github.com/sebrandon1/bps-operator)

Streamlined end-to-end test pipelines by replacing clone-and-compile steps with a prebuilt checks-qe container image. Eliminates source-level build dependency, reduces CI complexity, and saves ~1 minute per workflow across both Kubernetes and OpenShift pipelines. Leverages new image publishing from [checks-qe PR #13](https://github.com/redhat-best-practices-for-k8s/checks-qe/pull/13). [PR #77](https://github.com/sebrandon1/bps-operator/pull/77)

---

## 2026-04-15: Simplified BPS Operator Developer Experience - [bps-operator](https://github.com/sebrandon1/bps-operator)

Reduced the Best Practices Scanner operator quick start from a multi-step, multi-terminal workflow to a single command (`make deploy-scan`). Eliminated local process management by deploying the operator in-cluster, auto-configured OpenShift security privileges, fixed noisy Operator Lifecycle Manager (OLM) cache errors, and corrected outdated documentation (57 checks listed vs. 105 actual). New users can now run a full compliance scan in one step. [PR #75](https://github.com/sebrandon1/bps-operator/pull/75)

---

## 2026-04-15: End-to-End Quality Engineering for BPS Operator - [bps-operator](https://github.com/sebrandon1/bps-operator), [checks-qe](https://github.com/redhat-best-practices-for-k8s/checks-qe)

Established automated quality engineering coverage for the Best Practices Scanner operator by integrating the checks-qe test framework in operator mode. 146 scenarios now validate the operator end-to-end on every PR across both Kubernetes (Kind) and OpenShift (CRC) clusters, catching regressions like missing Role-Based Access Control (RBAC) permissions and check behavior changes from dependency updates. Also bumped the checks library to v0.0.23, replaced a 2-minute blocking reconciliation loop with an idiomatic non-blocking requeue pattern, and resolved all open issues. [bps-operator PRs #71-#74](https://github.com/sebrandon1/bps-operator/pulls?q=is%3Apr+is%3Amerged+number%3A71..74), [checks-qe PRs #9-#12](https://github.com/redhat-best-practices-for-k8s/checks-qe/pulls?q=is%3Apr+is%3Amerged+number%3A9..12)

---

## 2026-04-14: Disconnected Environment Support Guide - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Enabled partners with air-gapped OpenShift clusters to run the certification test suite by creating comprehensive disconnected environment documentation. Covers oc-mirror v2 and skopeo workflows for mirroring the certsuite-probe image, validated end-to-end against a local cluster. Unblocks users who were previously unable to certify workloads in restricted networks. [PR #3573](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3573), [CNFCERT-1390](https://issues.redhat.com/browse/CNFCERT-1390)

---

## 2026-04-14: Patch Releases Across 17 Repositories

Reduced dependency drift and security exposure by cutting patch releases across 17 repositories in the redhat-best-practices-for-k8s and sebrandon1 organizations. Covers Go 1.26.2 upgrades, dependency bumps, CI action updates, and feature improvements that had accumulated since March. Keeps downstream consumers on supported, CVE-patched versions.

---

## 2026-04-14: k3s Cluster Provider for CI Pipelines - [quick-k8s](https://github.com/palmsoftware/quick-k8s)

Added k3s as a third cluster provider in quick-k8s, giving CI pipelines a lightweight Kubernetes option that starts in under 30 seconds on ~512MB RAM. Enables faster, cheaper test runs on GitHub Actions free-tier runners. Fully tested across 4 Ubuntu variants with nightly version updates. [PR #111](https://github.com/palmsoftware/quick-k8s/pull/111), [CNFCERT-1389](https://issues.redhat.com/browse/CNFCERT-1389)

---

## 2026-04-13: Operator SDK v1.42.2 Dependency Update - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Updated operator-sdk from v1.41.1 to v1.42.2 across certsuite and certsuite-sample-workload, picking up a gRPC security bump. End-to-end: created Jira, opened PRs in both repos, verified CI across all test suites, merged, and closed the ticket. [certsuite #3563](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3563), [sample-workload #676](https://github.com/redhat-best-practices-for-k8s/certsuite-sample-workload/pull/676), [CNFCERT-1387](https://issues.redhat.com/browse/CNFCERT-1387)

---

## 2026-04-10: TLS Scanner Feature Parity and Beyond - [tls-compliance-operator](https://github.com/sebrandon1/tls-compliance-operator)

Closed 8 of 10 feature gaps against the upstream OpenShift tls-scanner in a single session, shipping 6 PRs as release v0.0.14. Added post-quantum cryptography (PQC) compliance classification, forward secrecy reporting, key exchange type details, SSLv3 detection via raw socket probing, health probe port filtering to eliminate false positives, and IPv6 dual-stack support. The operator now exceeds the upstream scanner's capabilities while providing continuous monitoring, Prometheus metrics, and Kubernetes-native reporting that the upstream batch-mode scanner lacks. [v0.0.14](https://github.com/sebrandon1/tls-compliance-operator/releases/tag/v0.0.14), [PR #87](https://github.com/sebrandon1/tls-compliance-operator/pull/87), [PR #88](https://github.com/sebrandon1/tls-compliance-operator/pull/88), [PR #89](https://github.com/sebrandon1/tls-compliance-operator/pull/89), [PR #90](https://github.com/sebrandon1/tls-compliance-operator/pull/90), [PR #91](https://github.com/sebrandon1/tls-compliance-operator/pull/91), [PR #92](https://github.com/sebrandon1/tls-compliance-operator/pull/92)

---

## 2026-04-10: Full-Profile Compliance Scanning and Mirror CI - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts)

Expanded compliance validation from 106 checks (one profile) to 910 checks across all four security profiles (E8, CIS, Moderate, PCI-DSS), eliminating blind spots in our hardening baseline. Reprovisioned cnfdt16 with OCP 4.22 nightly and confirmed zero regressions. Fixed multi-architecture image mirroring CI that was silently producing arm64-only bundles, added nightly architecture verification, and resolved a podman 4.x auth bug that blocked all image pushes from GitHub Actions. [PR #81](https://github.com/sebrandon1/compliance-scripts/pull/81), [CNF-19031](https://issues.redhat.com/browse/CNF-19031)

---

## 2026-04-10: Environment-Aware QE Test Assertions - [certsuite-qe](https://github.com/redhat-best-practices-for-k8s/certsuite-qe)

Eliminated false nightly failures on OCP 4.14, 4.16, and 4.17 by making QE tests detect cluster state before asserting certsuite outcomes. The scheduling policy test now runs `chrt` to detect RT scheduling, and the lifecycle test checks OCP end-of-life dates — ensuring each test expects the correct result for its environment instead of assuming a fixed outcome. [PR #1435](https://github.com/redhat-best-practices-for-k8s/certsuite-qe/pull/1435)

---

## 2026-04-10: Cert-Manager Operator Code Health Campaign - [cert-manager-operator](https://github.com/openshift/cert-manager-operator)

Improved code maintainability across the OpenShift cert-manager operator by rebasing 2 stale community PRs, conducting a full codebase audit that identified 22 cleanup opportunities, and shipping 5 PRs covering logging consolidation, context consistency, typo fixes, error handling, and magic string elimination. Created Jira tracking and CI-verified all changes. [PR #314](https://github.com/openshift/cert-manager-operator/pull/314), [PR #242](https://github.com/openshift/cert-manager-operator/pull/242), [PR #399](https://github.com/openshift/cert-manager-operator/pull/399), [PR #400](https://github.com/openshift/cert-manager-operator/pull/400), [PR #404](https://github.com/openshift/cert-manager-operator/pull/404), [CNF-22825](https://issues.redhat.com/browse/CNF-22825), [CNF-22826](https://issues.redhat.com/browse/CNF-22826), [CNF-22831](https://issues.redhat.com/browse/CNF-22831), [CNF-22833](https://issues.redhat.com/browse/CNF-22833), [CNF-22870](https://issues.redhat.com/browse/CNF-22870)

---

## 2026-04-10: Codebase Simplification Audit and Cleanup - [eco-goinfra](https://github.com/openshift-kni/eco-goinfra)

Reduced technical debt across eco-goinfra (282K lines, 80+ packages) by conducting a full codebase audit that identified 22 improvement items across code reuse, quality, and efficiency. Removed 21 redundant nil-slice checks across 11 files (-114 lines), created a reusable `/simplify-audit` skill for future audits, and confirmed alignment with Kirsten Laskoski's ongoing common builder migration to avoid duplicate effort. [PR #1321](https://github.com/rh-ecosystem-edge/eco-goinfra/pull/1321), [CNF-22884](https://issues.redhat.com/browse/CNF-22884)

---

## 2026-04-09: Codebase Health Audit and Bug Fixes - [cnf-features-deploy](https://github.com/openshift-kni/cnf-features-deploy)

Improved codebase reliability and maintainability across cnf-features-deploy by conducting a full-repo audit that identified 54 improvement items. Fixed 2 bugs (missing variable reference, DPDK version typo), corrected typos across 8 files, migrated 51 deprecated kustomize configs, addressed security review findings on kustomize CI, and closed 4 obsolete PRs. Created Jira tracking for all work. [PR #3956](https://github.com/openshift-kni/cnf-features-deploy/pull/3956), [PR #3957](https://github.com/openshift-kni/cnf-features-deploy/pull/3957), [PR #3958](https://github.com/openshift-kni/cnf-features-deploy/pull/3958), [PR #3097](https://github.com/openshift-kni/cnf-features-deploy/pull/3097), [CNF-22868](https://issues.redhat.com/browse/CNF-22868), [CNF-22869](https://issues.redhat.com/browse/CNF-22869), [CNF-22873](https://issues.redhat.com/browse/CNF-22873)

---

## 2026-04-09: RAN Hardening Reference Design Specification - [telco-reference](https://github.com/openshift-kni/telco-reference)

Enabled telco partners to adopt HIGH severity security compliance remediations by documenting crypto policy, PAM, and SSHD hardening in the RAN Reference Design Specification (RDS). Created the RDS Merge Request, linked traceability across Jira and GitHub, and rebased 33 compliance branches with corrected directory structure for the 4.23 release. [RDS MR !184](https://gitlab.cee.redhat.com/reference-configurations/reference-design-specifications/-/merge_requests/184), [PR #529](https://github.com/openshift-kni/telco-reference/pull/529), [PR #466](https://github.com/openshift-kni/telco-reference/pull/466), [CNF-19031](https://issues.redhat.com/browse/CNF-19031)

---

## 2026-04-08: Go 1.26.2 Security Upgrade Across 27 Repos

Eliminated exposure to 10 CVEs — including code execution, memory corruption, and XSS vulnerabilities — by upgrading Go to 1.26.2 across 27 repositories in the sebrandon1 and redhat-best-practices-for-k8s organizations. Added `toolchain` directives for developer compatibility, updated Dockerfiles, and cut 13 patch releases. [Go 1.26.2 announcement](https://groups.google.com/g/golang-announce/c/EdhZqrQ98hk/m/41DopX_WAAAJ), [certsuite #3555](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3555), [checks #31](https://github.com/redhat-best-practices-for-k8s/checks/pull/31), [bps-operator #67](https://github.com/sebrandon1/bps-operator/pull/67)

---

## 2026-04-08: Restored 14 Nightly QE Pipelines - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Restored all 14 nightly Quality Engineering (QE) pipelines across 7 OpenShift versions after overly aggressive timeout reductions left 42 of 70 runs (60%) failing via cancellation. Audited CI timing data, right-sized job and step timeouts, and verified fixes across every pipeline. Eliminates daily false-failure noise for the team and restores confidence in nightly regression signals. [PR #3553](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3553), [PR #3556](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3556)

---

## 2026-04-08: Checks Library Migration Proof of Concept - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Consolidated check metadata and test logic into a shared library, eliminating ~3,200 lines of duplicated code from the certification test suite. Establishes a single source of truth for 102 compliance checks, enabling both the CLI tool and the Kubernetes operator to share identical validation logic. [checks v0.0.6](https://github.com/redhat-best-practices-for-k8s/checks/releases/tag/v0.0.6), [checks #30](https://github.com/redhat-best-practices-for-k8s/checks/pull/30), [certsuite #3554](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3554)

---

## 2026-04-07: Red Hat Status Pre-Flight Action for CI - [redhat-status](https://github.com/palmsoftware/redhat-status)

Created a reusable GitHub Action that checks [status.redhat.com](https://status.redhat.com/) before CI workflows run, giving teams instant visibility into Red Hat infrastructure outages that could cause failures. Rolled out across 21 workflows in 10 repositories spanning 3 organizations (palmsoftware, sebrandon1, redhat-best-practices-for-k8s), covering OpenShift, Quay.io, and Red Hat registry dependencies. Reduces wasted CI minutes and developer time spent debugging infrastructure-caused failures. [redhat-status v0.0.2](https://github.com/palmsoftware/redhat-status/releases/tag/v0.0.2), [quick-ocp #50](https://github.com/palmsoftware/quick-ocp/pull/50), [quick-k8s #105](https://github.com/palmsoftware/quick-k8s/pull/105), [compliance-scripts #79](https://github.com/sebrandon1/compliance-scripts/pull/79), [certsuite #3551](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/3551), [certsuite-qe #1432](https://github.com/redhat-best-practices-for-k8s/certsuite-qe/pull/1432), [CNFCERT-1385](https://issues.redhat.com/browse/CNFCERT-1385)

---

## 2026-04-07: RAN Hardening PR Maintenance - [telco-reference](https://github.com/openshift-kni/telco-reference)

Maintained 8 open RAN hardening Pull Requests — squashed commits, rebased against upstream, and addressed CodeRabbit security reviews on HIGH severity compliance remediations (crypto policy, PAM). Documented intentional design decisions where the Compliance Operator's own remediations are broken on Red Hat Enterprise Linux CoreOS (RHCOS) 9, linking to our upstream fix at [ComplianceAsCode/content#14602](https://github.com/ComplianceAsCode/content/pull/14602). [PR #529](https://github.com/openshift-kni/telco-reference/pull/529), [CNF-21212](https://issues.redhat.com/browse/CNF-21212)

---

## 2026-04-07: Nightly Compliance CI for Operator v1.8.2 - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts)

Expanded nightly compliance testing to cover Compliance Operator v1.8.2 alongside v1.7.0, consolidating two separate CI workflows into a single matrix-driven pipeline. Automated baseline regression detection and artifact collection now run daily across both operator versions, catching breakages before they reach clusters. [PR #78](https://github.com/sebrandon1/compliance-scripts/pull/78)

---
