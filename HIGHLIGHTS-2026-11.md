# Work Highlights - 2026-11

A reverse-chronological log of significant engineering accomplishments for November 2026.

---
## 2026-11-25: Prevented Disk-Wipe Data Loss - [vsno](https://github.com/sebrandon1/vsno)

Eliminated a data-loss risk in the virtual single-node OpenShift lab tool: its cluster precheck now proves a disk is blank before recommending it for LVM Storage, so a live Ceph storage disk can no longer be erased. [PR #164](https://github.com/sebrandon1/vsno/pull/164) [v0.1.3](https://github.com/sebrandon1/vsno/releases/tag/v0.1.3) [CNF-30463](https://redhat.atlassian.net/browse/CNF-30463)

## 2026-11-24: Shipped vSNO Usability Release v0.1.2 - [vsno](https://github.com/sebrandon1/vsno)

Cut manual polling and guesswork from virtual single-node OpenShift lab operations: one-command inspection (describe), scriptable waits, shell completion, list filters and dry-run planning, then released v0.1.2 with binaries for four platforms. [PR #159](https://github.com/sebrandon1/vsno/pull/159) [PR #163](https://github.com/sebrandon1/vsno/pull/163) [v0.1.2](https://github.com/sebrandon1/vsno/releases/tag/v0.1.2)

## 2026-11-24: Unblocked Performance API Development - [oran-o2ims](https://github.com/openshift-kni/oran-o2ims)

Delivered the first building block for the O-RAN Performance API by making the cluster and resource clients shareable across O-Cloud Manager services. Removed duplicated authentication setup, fixed a latent namespace bug that breaks token requests in non-default namespaces, and added 10 unit tests. [PR #5494](https://github.com/openshift-kni/oran-o2ims/pull/5494) [CNF-30450](https://redhat.atlassian.net/browse/CNF-30450)

## 2026-11-24: Hardened Dashboard and Shipped v1.0.0 - [ztp-dashboard](https://github.com/sebrandon1/ztp-dashboard)

Closed all 10 remaining open issues in one batch and cut the first stable release: opt-in authentication, origin-restricted CORS and WebSockets, request-body caps, AI rate limiting, and durable event storage. 10 PRs merged, all checks green. [v1.0.0](https://github.com/sebrandon1/ztp-dashboard/releases/tag/v1.0.0)

## 2026-11-24: Shipped Self-Diagnosing vSNO v0.1.1 - [vsno](https://github.com/sebrandon1/vsno)

Removed the config-file barrier to first use of the virtual single-node OpenShift (vSNO) lab tool and released v0.1.1: 70 changes, including doctor and report commands that turn stalled upgrades from hours of log reading into one diagnostic command. [PR #157](https://github.com/sebrandon1/vsno/pull/157) [v0.1.1](https://github.com/sebrandon1/vsno/releases/tag/v0.1.1)

## 2026-11-24: Restored Lab CLI Docs Accuracy - [succulent-cli](https://github.com/sebrandon1/succulent-cli)

Restored trust in the lab provisioning CLI's documentation, which still described pre-`--follow` log streaming and omitted environment groups, audit logging, and container builds — corrected stale guidance across four docs, all five CI checks green. [PR #232](https://github.com/sebrandon1/succulent-cli/pull/232)

## 2026-11-24: Fixed Four vSNO Lifecycle Defects - [vsno](https://github.com/sebrandon1/vsno)

Eliminated four defects that stalled virtual single-node OpenShift upgrades: stuck Image Based Upgrades now fail in seconds with a recovery path, interrupted seed builds stay visible instead of appearing dead, and stopping a cluster mid-generation is refused. 980 tests; verified live. [PR #153](https://github.com/sebrandon1/vsno/pull/153) [PR #154](https://github.com/sebrandon1/vsno/pull/154) [PR #155](https://github.com/sebrandon1/vsno/pull/155) [PR #156](https://github.com/sebrandon1/vsno/pull/156)

## 2026-11-24: Consoleless Install Fix Now Shipping - [cert-manager-operator](https://github.com/openshift/cert-manager-operator)

Customers running consoleless clusters, such as Radio Access Network (RAN) telco deployments, can now install cert-manager straight from the Red Hat catalog. Released v1.20.1 includes the fix moving Console resources out of the install bundle, removing the manual cluster-patching workaround. [PR #455](https://github.com/openshift/cert-manager-operator/pull/455) [PR #467](https://github.com/openshift/cert-manager-operator/pull/467) [OCPBUGS-85579](https://redhat.atlassian.net/browse/OCPBUGS-85579)

## 2026-11-23: Hardened OLM Against Crashes and Bad Labels - [operator-lifecycle-manager](https://github.com/operator-framework/operator-lifecycle-manager)

Eliminated two classes of Operator Lifecycle Manager failures: invalid API keys no longer leak malformed strings into RBAC labels and annotations, and serving-certificate generation now returns an error instead of panicking, with a new 16-test suite covering previously untested certificate rotation code. [PR #3933](https://github.com/operator-framework/operator-lifecycle-manager/pull/3933) [PR #3944](https://github.com/operator-framework/operator-lifecycle-manager/pull/3944) [CNF-27963](https://redhat.atlassian.net/browse/CNF-27963) [CNF-28768](https://redhat.atlassian.net/browse/CNF-28768)

## 2026-11-23: Shipped CI Triage Release v0.1.0 - [whyfail](https://github.com/sebrandon1/whyfail)

Released whyfail v0.1.0, seven changes making OpenShift CI triage trustworthy: job health now says when a verdict came from a partial read instead of miscounting failures, AI agents can search CI and read bounded logs, and the daily board flags jobs that newly broke. [v0.1.0](https://github.com/sebrandon1/whyfail/releases/tag/v0.1.0) [PR #82](https://github.com/sebrandon1/whyfail/pull/82) [PR #81](https://github.com/sebrandon1/whyfail/pull/81)

## 2026-11-20: Closed 12 Operator Enhancements - [imagecertinfo-operator](https://github.com/sebrandon1/imagecertinfo-operator)

Closed 14 open enhancement issues for the image certification operator in one pass. New orphan cleanup reclaims stale inventory automatically, credential rotation no longer needs a restart, and GitHub Container Registry images are now enriched alongside Red Hat and Quay. [PR #283](https://github.com/sebrandon1/imagecertinfo-operator/pull/283) [PR #286](https://github.com/sebrandon1/imagecertinfo-operator/pull/286) [PR #289](https://github.com/sebrandon1/imagecertinfo-operator/pull/289)

## 2026-11-19: Shipped CI Flake Triage v0.0.2 - [whyfail](https://github.com/sebrandon1/whyfail)

Released whyfail v0.0.2, twelve changes making CI flake triage a one-command answer: failing checks name the PRs behind them, logs are grep-able, runs can gate CI with an exit code, and a daily dashboard tracks job health past Prow's 90-day retention. [v0.0.2](https://github.com/sebrandon1/whyfail/releases/tag/v0.0.2) [PR #68](https://github.com/sebrandon1/whyfail/pull/68)

## 2026-11-19: Hardened TLS Scanning Coverage - [tls-config-lint](https://github.com/sebrandon1/tls-config-lint)

Shipped tls-config-lint v1.2.5, closing nine open issues: scans now cover C, JSX/TSX, and Kotlin scripts, detect deeper repositories, and stop reporting commented-out code and ecosystem test files. Teams relying on it as a TLS security gate get accurate results instead of silent or noisy scans. [v1.2.5](https://github.com/sebrandon1/tls-config-lint/releases/tag/v1.2.5) [PR #135](https://github.com/sebrandon1/tls-config-lint/pull/135)

## 2026-11-18: Enabled Upgrade Testing Without Hardware - [lifecycle-agent](https://github.com/openshift-kni/lifecycle-agent)

Proved Image Based Upgrades (IBU) can be tested on virtual single-node OpenShift clusters inside an existing lab cluster, with no reprovisioning or spare servers. Completed a full 4.20.45→4.20.46 upgrade, published a step-by-step team guide, and fixed a documentation bug that broke node boots. [PR #10670](https://github.com/openshift-kni/lifecycle-agent/pull/10670) [CNF-30291](https://redhat.atlassian.net/browse/CNF-30291)

## 2026-11-17: Delivered OpenShift 5.0-Ready Release - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Shipped certsuite v5.5.27, the first release validated against OpenShift 5.0, so partners can test workloads on the next platform version. Also closed a credential leak in result files and cut smoke-test runtime 41%, making every certification run faster and safer. [v5.5.27](https://github.com/redhat-best-practices-for-k8s/certsuite/releases/tag/v5.5.27) [CNFCERT-1543](https://redhat.atlassian.net/browse/CNFCERT-1543)

## 2026-11-17: Made Lab CLI Timeouts Configurable - [succulent-cli](https://github.com/sebrandon1/succulent-cli)

Removed hardcoded network and cache settings from the lab provisioning CLI, so CI runs can disable caching and long-running jobs can raise timeouts without code changes — fewer failed automated runs. Shipped v0.1.5 with both changes and five bug fixes. [PR #229](https://github.com/sebrandon1/succulent-cli/pull/229) [PR #230](https://github.com/sebrandon1/succulent-cli/pull/230) [v0.1.5](https://github.com/sebrandon1/succulent-cli/releases/tag/v0.1.5)

## 2026-11-17: Refreshed Kubernetes Networking Defaults - [quick-k8s](https://github.com/palmsoftware/quick-k8s)

Shipped release v1.0.13, keeping the Kubernetes test harness on current networking components: Calico v3.33.1 and Cilium CLI v0.20.3 defaults, plus a CI fix that stops version bumps from landing before the upstream mirror publishes them, preventing wasted failed builds. [PR #514](https://github.com/palmsoftware/quick-k8s/pull/514) [PR #513](https://github.com/palmsoftware/quick-k8s/pull/513) [v1.0.13](https://github.com/palmsoftware/quick-k8s/releases/tag/v1.0.13) [CNF-30255](https://redhat.atlassian.net/browse/CNF-30255)

## 2026-11-17: Shipped CI Flake Triage Tool - [whyfail](https://github.com/sebrandon1/whyfail)

Released whyfail v0.0.1, which separates broken CI jobs from flaky ones using Prow's own retained history, so reviewers stop chasing false failures. Merged two improvements and added a one-command PR comment that flags historically flaky checks. [v0.0.1](https://github.com/sebrandon1/whyfail/releases/tag/v0.0.1) [PR #46](https://github.com/sebrandon1/whyfail/pull/46) [PR #47](https://github.com/sebrandon1/whyfail/pull/47)

## 2026-11-17: Added OpenShift 5.0 Nightly Coverage - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Started daily certification testing against OpenShift 5.0, the first 5.x release, and retired 4.14/4.16 nightlies that depended on hand-maintained lab machines. Moving all nightlies to GitHub-hosted runners removes lab upkeep and frees two lab machines. [PR #4026](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/4026)

## 2026-11-16: Remediated Go CVE Across 17 Repos - [certsuite-qe](https://github.com/redhat-best-practices-for-k8s/certsuite-qe)

Eliminated a known Go standard-library vulnerability (GO-2026-6859) across 17 repositories by pinning Go 1.27.4 — 18 pull requests merged in one pass — and turned on patch-level drift detection so the next stale toolchain is caught before a security scan fails. [PR #1698](https://github.com/redhat-best-practices-for-k8s/certsuite-qe/pull/1698) [CNFCERT-1542](https://redhat.atlassian.net/browse/CNFCERT-1542)

## 2026-11-16: Fixed Misdiagnosed Cluster Failures - [quick-ocp](https://github.com/palmsoftware/quick-ocp)

Released v1.1.1 after proving from raw CI logs that a reported "silent setup crash" was really two post-startup failures, so none of the requested fixes would have helped. Added automatic retries for transient API (Application Programming Interface) errors, timeout diagnostics, and an unstable-cluster warning, with 8 new tests. [PR #229](https://github.com/palmsoftware/quick-ocp/pull/229) [v1.1.1](https://github.com/palmsoftware/quick-ocp/releases/tag/v1.1.1) [CNF-30256](https://redhat.atlassian.net/browse/CNF-30256)

## 2026-11-13: Backported Operator Stability Fixes - [cert-manager-operator](https://github.com/openshift/cert-manager-operator)

Opened backports so customers on cert-manager Operator 1.20 get three stability fixes without waiting for the next release: a crash (nil-pointer panic), lost error details, and skipped retries. Resolved conflicts manually where automation failed, and rebased 6 open pull requests onto master. [PR #546](https://github.com/openshift/cert-manager-operator/pull/546) [PR #547](https://github.com/openshift/cert-manager-operator/pull/547) [PR #548](https://github.com/openshift/cert-manager-operator/pull/548) [CNF-26102](https://redhat.atlassian.net/browse/CNF-26102) [CNF-29074](https://redhat.atlassian.net/browse/CNF-29074)

## 2026-11-12: Hardened Fleet Upgrade Orchestration - [cluster-group-upgrades-operator](https://github.com/openshift-kni/cluster-group-upgrades-operator)

Prevented silent upgrade failures and controller crashes in TALM (Topology Aware Lifecycle Manager), which rolls updates across thousands of edge clusters. Fixed 8 bugs, including partially failed rollouts reported as successful, and added unit tests for 60+ untested functions, now in review as 8 upstream pull requests. [PR #14500](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14500) [PR #14534](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14534) [PR #14535](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14535) [PR #14536](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14536) [PR #14537](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14537) [PR #14538](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14538) [PR #14539](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14539) [PR #14540](https://github.com/openshift-kni/cluster-group-upgrades-operator/pull/14540) [CNF-30144](https://redhat.atlassian.net/browse/CNF-30144) [CNF-30139](https://redhat.atlassian.net/browse/CNF-30139) [CNF-30170](https://redhat.atlassian.net/browse/CNF-30170) [CNF-30171](https://redhat.atlassian.net/browse/CNF-30171) [CNF-30172](https://redhat.atlassian.net/browse/CNF-30172) [CNF-30173](https://redhat.atlassian.net/browse/CNF-30173) [CNF-30174](https://redhat.atlassian.net/browse/CNF-30174) [CNF-30175](https://redhat.atlassian.net/browse/CNF-30175)

## 2026-11-12: Made Test Coverage Gaps Visible - [certsuite](https://github.com/redhat-best-practices-for-k8s/certsuite)

Merged a reworked smoke-scenario coverage report so engineers can see at a glance which of 124 tests are covered and why the other 38 cannot run. Replaced ~87 repeated scenario names with linked IDs, added per-scenario links to the scripts that run, and cut the file size. [PR #4019](https://github.com/redhat-best-practices-for-k8s/certsuite/pull/4019) (merged)

## 2026-11-12: Hardened Cluster Reconfiguration Tool - [recert](https://github.com/rh-ecosystem-edge/recert)

Closed major test gaps in recert, the tool that reconfigures pre-built OpenShift single-node clusters for each site. 10 new integration scenarios now cover cluster, IP, proxy and certificate renames. The scenarios exposed and fixed 19 crash and silent-failure bugs, including IP renames that corrupted similar addresses. [PR #2364](https://github.com/rh-ecosystem-edge/recert/pull/2364) [CNF-30065](https://redhat.atlassian.net/browse/CNF-30065)

## 2026-11-12: Unblocked TLS Operator OpenShift Release - [community-operators-prod](https://github.com/redhat-openshift-ecosystem/community-operators-prod)

Caught that OpenShift users could not install the latest TLS Compliance Operator: two releases (1.1.20, 1.2.0) were merged but never published to the OpenShift community catalog. Opened the catalog update with a direct upgrade path from any prior version, bringing custom security profiles and localhost-listener detection to OpenShift. [PR #12002](https://github.com/redhat-openshift-ecosystem/community-operators-prod/pull/12002) [PR #11989](https://github.com/redhat-openshift-ecosystem/community-operators-prod/pull/11989) [v1.2.0](https://github.com/sebrandon1/tls-compliance-operator/releases/tag/v1.2.0)

## 2026-11-11: Shipped Compliance-Scripts v1.2.4 - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts)

Released 20 merged changes that restore trust in OpenShift compliance reporting: scheduled image mirroring now installs its required tool, verification fails when nothing was applied, and the dashboard validator reports only real problems. [Release v1.2.4](https://github.com/sebrandon1/compliance-scripts/releases/tag/v1.2.4) [PR #456](https://github.com/sebrandon1/compliance-scripts/pull/456) [PR #457](https://github.com/sebrandon1/compliance-scripts/pull/457)

## 2026-11-10: Eliminated Broken OCP Version Bumps - [quick-k8s](https://github.com/palmsoftware/quick-k8s)

Prevented deployment automation from publishing unusable OpenShift release levels: the nightly updater now waits until Red Hat's mirror actually carries a version, eliminating update PRs that failed all 31 CI checks. Shipped in v1.0.12 alongside Istio and MetalLB bumps. [PR #512](https://github.com/palmsoftware/quick-k8s/pull/512) [v1.0.12](https://github.com/palmsoftware/quick-k8s/releases/tag/v1.0.12)

## 2026-11-09: Hardened cert-manager Test Cleanup - [cert-manager-scripts](https://github.com/sebrandon1/cert-manager-scripts)

Prevented destructive cleanup on shared OpenShift test clusters: fake-DNS setup now preserves existing DNS forwarding and restores it, `make clean` removes only certificates this toolkit created, and the operator uninstall target now actually uninstalls. Four bug fixes with regression tests. [PR #238](https://github.com/sebrandon1/cert-manager-scripts/pull/238) [PR #239](https://github.com/sebrandon1/cert-manager-scripts/pull/239) [PR #240](https://github.com/sebrandon1/cert-manager-scripts/pull/240) [PR #241](https://github.com/sebrandon1/cert-manager-scripts/pull/241)


## 2026-11-09: Eliminated Five Silent CI Failures - [compliance-scripts](https://github.com/sebrandon1/compliance-scripts)

Restored OpenShift compliance automation that silently reported success: both image-mirroring pipelines lacked a required tool, a verification job could pass after applying nothing, and the dashboard showed a six-fold-undercounted result. Fixed all five defects with regression coverage; 550 tests pass. [PR #451](https://github.com/sebrandon1/compliance-scripts/pull/451) [PR #452](https://github.com/sebrandon1/compliance-scripts/pull/452) [PR #453](https://github.com/sebrandon1/compliance-scripts/pull/453) [PR #454](https://github.com/sebrandon1/compliance-scripts/pull/454) [PR #455](https://github.com/sebrandon1/compliance-scripts/pull/455)

## 2026-11-06: Shipped Quay Traffic Analytics - [go-quay](https://github.com/sebrandon1/go-quay)

Enabled teams to see which images and clusters drive registry load. New `list pull-traffic` and `report consumers` commands rank image pulls by repository, tag, puller identity, and source IP, with CSV export for spreadsheets — turning a manual 90-day investigation into one command. Released as v1.3.0. [PR #302](https://github.com/sebrandon1/go-quay/pull/302) [v1.3.0](https://github.com/sebrandon1/go-quay/releases/tag/v1.3.0)

## 2026-11-05: Six-Repo Go Toolchain Standardization - [grab](https://github.com/sebrandon1/grab)

Removed a hard Go patch-version requirement that blocked the CRC integration build, so any Go 1.26.x/1.27.x consumer can build while CI and release binaries still use patched compilers. Rolled the fix across six Go libraries, shipped patch releases, and eliminated flaky network-dependent CI tests. [PR #92](https://github.com/sebrandon1/grab/pull/92) [v1.2.4](https://github.com/sebrandon1/grab/releases/tag/v1.2.4) [go-dci PR #257](https://github.com/sebrandon1/go-dci/pull/257) [go-enphase PR #111](https://github.com/sebrandon1/go-enphase/pull/111)

## 2026-11-04: Closed CVE in grab Release - [grab](https://github.com/sebrandon1/grab)

Shipped grab v1.2.3, closing a Go standard-library vulnerability (GO-2026-6809) before it could reach downstream automation, and modernizing HTTP handling via go-toolbox. The patch is now available for Linux, macOS, and Windows with verified binaries. [v1.2.3](https://github.com/sebrandon1/grab/releases/tag/v1.2.3) [PR #90](https://github.com/sebrandon1/grab/pull/90) [PR #91](https://github.com/sebrandon1/grab/pull/91)

## 2026-11-04: Cut Flaky CI With Data - [quick-ocp](https://github.com/palmsoftware/quick-ocp)

Measured 1,300 CI runs to prove a single OpenShift version caused most flaky failures — a 7.7% failure rate versus 0.6% for every other version — then retired it and dropped its wasted jobs. Also taught the cache check to survive runner disk and network faults. [PR #225](https://github.com/palmsoftware/quick-ocp/pull/225) [PR #226](https://github.com/palmsoftware/quick-ocp/pull/226) [v1.0.10](https://github.com/palmsoftware/quick-ocp/releases/tag/v1.0.10) [v1.0.11](https://github.com/palmsoftware/quick-ocp/releases/tag/v1.0.11) | [CNF-29533](https://redhat.atlassian.net/browse/CNF-29533) [CNF-29535](https://redhat.atlassian.net/browse/CNF-29535)

## 2026-11-04: Dependable cert-manager Test Toolkit - [cert-manager-scripts](https://github.com/sebrandon1/cert-manager-scripts)

Made the cert-manager test toolkit dependable outside default setups: it now honors custom namespaces, fully cleans up after itself, stops leaking test resources, and its version-bump script works on macOS. Traced intermittent CI failures to undersized build machines, then shipped four fixes as v0.0.25. [v0.0.25](https://github.com/sebrandon1/cert-manager-scripts/releases/tag/v0.0.25) | [PR #228](https://github.com/sebrandon1/cert-manager-scripts/pull/228) [PR #229](https://github.com/sebrandon1/cert-manager-scripts/pull/229) [PR #230](https://github.com/sebrandon1/cert-manager-scripts/pull/230) [PR #231](https://github.com/sebrandon1/cert-manager-scripts/pull/231) | [CNF-29689](https://redhat.atlassian.net/browse/CNF-29689)

## 2026-11-03: Prevented Fleet-Wide Spoke Disconnects - [telco-reference](https://github.com/openshift-kni/telco-reference)

Caught a flaw in the Telco hub reference configuration that would disconnect every managed cluster within minutes when adopting cert-manager certificates on an existing hub. Validated the corrected rollout and recovery steps three times on a live OpenShift 4.22 lab, then gave quality engineering (QE) a step-by-step guide with automated health checks. [PR #1027](https://github.com/openshift-kni/telco-reference/pull/1027) | [Guide](https://github.com/sebrandon1/cert-manager-poc/blob/main/docs/hub-spoke-cert-rotation.md) | [OCPBUGS-85774](https://redhat.atlassian.net/browse/OCPBUGS-85774)

## 2026-11-03: Unblocked Compliance Lane, 60x Faster Scans - [tls-compliance-operator](https://github.com/sebrandon1/tls-compliance-operator)

Unblocked the cluster-network-addons-operator (CNAO) s390x compliance lane, which timed out because TLS scans stalled on stale endpoints. A full scan on a 300-endpoint cluster now finishes in 38 seconds instead of 40 minutes, and namespace filtering is applied consistently across the operator. Released and adopted upstream. [v1.1.22](https://github.com/sebrandon1/tls-compliance-operator/releases/tag/v1.1.22) [PR #648](https://github.com/sebrandon1/tls-compliance-operator/pull/648) [PR #651](https://github.com/sebrandon1/tls-compliance-operator/pull/651) [CNAO #2942](https://github.com/kubevirt/cluster-network-addons-operator/pull/2942)

## 2026-11-02: Branch Cleanup Across 26 Repos - [redhat-best-practices-for-k8s](https://github.com/redhat-best-practices-for-k8s)

Reduced repository clutter so contributors and automation see only active work. Removed 189 already-merged branches across 26 Red Hat Best Practices for Kubernetes repositories (135 on GitHub, 142 local), with no work lost. Kept every unmerged or open-PR branch for review. [Org](https://github.com/redhat-best-practices-for-k8s)

## 2026-11-02: Hardened Image Inventory Release - [imagecertinfo-operator](https://github.com/sebrandon1/imagecertinfo-operator)

Made the cluster image certification inventory more dependable: it now rides out temporary registry outages, keeps memory use bounded, no longer loses updates, and closes a Go security vulnerability. Released as v0.2.27, bundling over a dozen reliability and security fixes with a one-command install. [v0.2.27](https://github.com/sebrandon1/imagecertinfo-operator/releases/tag/v0.2.27)
