# Work Highlights - 2026-04

A reverse-chronological log of significant engineering accomplishments for April 2026.

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
