# PatternFly 5 to 6 Migration: Tool Comparison

Comparison of automated migration tools — **semver+goose**, **pf-codemods**, **fix-engine**, and **pf-codemods + goose** — across 19 OpenShift console plugin repositories.

> **Last updated:** 2026-06-10

## Summary

|                          | semver+goose 2026-06-04 | pf-codemods | fix-engine | pf-codemods + goose |
|--------------------------|:-----------------------:|:-----------:|:----------:|:-------------------:|
| PF6 Dependency Update    | 16 / 17 [[2]](#batch)   | 0 / 19      | 18 / 19    | 3 / 19              |
| Build passing            | 17 / 17 [[2]](#batch)   | 0 / 19      | 13 / 19    | 6 / 19              |
| Tests passing            | 8 / 9 [[2]](#batch)     | 1 / 10      | 8 / 10     | 2 / 10              |

## Results by Repository

| Repository | PF6 Dep Update | Build | Tests | Runtime | PF6 Dep Update | Build | Tests | Runtime | PF6 Dep Update | Build | Tests | Runtime | PF6 Dep Update | Build | Tests | Runtime |
|:-----------|:--------------:|:-----:|:-----:|--------:|:--------------:|:-----:|:-----:|--------:|:--------------:|:-----:|:-----:|--------:|:--------------:|:-----:|:-----:|--------:|
| | **semver+goose 2026-06-04** | | | | **pf-codemods** | | | | **fix-engine** | | | | **pf-codemods + goose** | | | |
| [console](https://github.com/jmontleon/console) | — | — | — | — | :x: | :x: | :x: [[1]](#console) | 54s | :x: [[1]](#console) | :x: | :white_check_mark: | N/A | :white_check_mark: | :x: | :x: | 3h 10m |
| [console-plugin](https://github.com/jmontleon/console-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 7h 40m | :x: | :x: | :x: | 16s | :white_check_mark: | :x: | :white_check_mark: | 37m 34s | :x: | :x: | :x: | 41m 36s |
| [console-plugin-template](https://github.com/jmontleon/console-plugin-template) | — | — | — | — | :x: | :x: | — | 4s | :white_check_mark: | :white_check_mark: | — | 4m 43s | :x: | :x: | — | 2m 30s |
| [distributed-tracing-console-plugin](https://github.com/jmontleon/distributed-tracing-console-plugin) | :white_check_mark: | :white_check_mark: | — | 11m 6s | :x: | :x: | — | 41s | :white_check_mark: | :white_check_mark: | — | 10m 59s | :x: | :x: | — | 3m 25s |
| [forklift-console-plugin](https://github.com/jmontleon/forklift-console-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 1h 28m | :x: | :x: | :x: | 1m 6s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 52m 1s | :x: | :white_check_mark: | :x: | 22m 40s |
| [gitops-console-plugin](https://github.com/jmontleon/gitops-console-plugin) | :white_check_mark: | :white_check_mark: | — | 9m 22s | :x: | :x: | — | 3s | :white_check_mark: | :white_check_mark: | — | 8m 12s | :x: | :x: | — | 3m 27s |
| [kuadrant-console-plugin](https://github.com/jmontleon/kuadrant-console-plugin) | :white_check_mark: | :white_check_mark: | — | 17m 36s | :x: | :x: | — | 22s | :white_check_mark: | :x: | — | 10m 14s | :x: | :x: | — | 2m 33s |
| [kubevirt-plugin](https://github.com/jmontleon/kubevirt-plugin) | :x: | :white_check_mark: | :white_check_mark: | 2h 55m | :x: | :x: | :white_check_mark: | 25s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 1h 21m | :x: | :white_check_mark: | :white_check_mark: | 8m 57s |
| [lightspeed-console](https://github.com/jmontleon/lightspeed-console) | :white_check_mark: | :white_check_mark: | — | 20m 25s | :x: | :x: | — | 14s | :white_check_mark: | :white_check_mark: | — | 5m 8s | :x: | :x: | — | 3m 35s |
| [logging-view-plugin](https://github.com/jmontleon/logging-view-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 16m 34s | :x: | :x: | :x: | 40s | :white_check_mark: | :x: | :x: | 9m 50s | :x: | :white_check_mark: | :white_check_mark: | 15m 9s |
| [monitoring-plugin](https://github.com/jmontleon/monitoring-plugin) | :white_check_mark: | :white_check_mark: | — | 40m 32s | :x: | :x: | :x: | 1m 7s | :white_check_mark: | :white_check_mark: | :x: | 31m 37s | :x: | :x: | :x: | 11m 46s |
| [netobserv-web-console](https://github.com/jmontleon/netobserv-web-console) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 1h 1m | :x: | :x: | :x: | 58s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 47m 24s | :x: | :x: | :x: | 12m 49s |
| [networking-console-plugin](https://github.com/jmontleon/networking-console-plugin) | :white_check_mark: | :white_check_mark: | — | 41m 35s | :x: | :x: | — | 7s | :white_check_mark: | :white_check_mark: | — | 24m 40s | :x: | :x: | — | 6m 44s |
| [nmstate-console-plugin](https://github.com/jmontleon/nmstate-console-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 26m 36s | :x: | :x: | :x: | 6s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 9m 13s | :x: | :x: | :x: | 2m 2s |
| [node-remediation-console](https://github.com/jmontleon/node-remediation-console) | :white_check_mark: | :white_check_mark: | — | 1h 3m | :x: | :x: | — | 18s | :white_check_mark: | :white_check_mark: | — | 16m 18s | :x: | :x: | — | 6m 54s |
| [odf-console](https://github.com/jmontleon/odf-console) | :white_check_mark: | :white_check_mark: | :x: | 3h 42m | :x: | :x: | :x: | 25s | :white_check_mark: | :x: | :white_check_mark: | 1h 50m | :white_check_mark: | :white_check_mark: | :x: | 1h 11m |
| [openshift-servicemesh-plugin](https://github.com/jmontleon/openshift-servicemesh-plugin) | :white_check_mark: | :white_check_mark: | — | 1h 9m | :x: | :x: | — | 20s | :white_check_mark: | :x: | — | 36m 38s | :white_check_mark: | :white_check_mark: | — | 1h 32m |
| [openshift-site-plugin](https://github.com/jmontleon/openshift-site-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 32m 5s | :x: | :x: | :x: | 17s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 13m 27s | :x: | :x: | :x: | 8m 57s |
| [troubleshooting-panel-console-plugin](https://github.com/jmontleon/troubleshooting-panel-console-plugin) | :white_check_mark: | :white_check_mark: | :white_check_mark: | 9m 47s | :x: | :x: | — | 14s | :white_check_mark: | :x: | — | 6m 25s | :x: | :white_check_mark: | — | 4m 30s |

**Legend:** :white_check_mark: = Pass | :x: = Fail | — = No test suite / Not run

## Branch Links

| Repository | semver+goose 2026-06-04 | pf-codemods | fix-engine | pf-codemods + goose |
|:-----------|:-----------------------:|:----------:|:----------:|:-------------------:|
| console | — | [branch](https://github.com/jmontleon/console/tree/pf-codemods) | [branch](https://github.com/jmontleon/console/tree/fix-engine) | [branch](https://github.com/jmontleon/console/tree/pf-codemods-plus-goose) |
| console-plugin | [branch](https://github.com/jmontleon/console-plugin/tree/semver/goose/060526-0300) | [branch](https://github.com/jmontleon/console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/console-plugin/tree/pf-codemods-plus-goose) |
| console-plugin-template | — | [branch](https://github.com/jmontleon/console-plugin-template/tree/pf-codemods) | [branch](https://github.com/jmontleon/console-plugin-template/tree/fix-engine) | [branch](https://github.com/jmontleon/console-plugin-template/tree/pf-codemods-plus-goose) |
| distributed-tracing-console-plugin | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/semver/goose/060426-2234) | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/pf-codemods-plus-goose) |
| forklift-console-plugin | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/semver/goose/060426-2234) | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/pf-codemods-plus-goose) |
| gitops-console-plugin | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/semver/goose/060426-2234) | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/pf-codemods-plus-goose) |
| kuadrant-console-plugin | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/semver/goose/060426-1851) | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/pf-codemods-plus-goose) |
| kubevirt-plugin | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/semver/goose/060826-1455) | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/pf-codemods-plus-goose) |
| lightspeed-console | [branch](https://github.com/jmontleon/lightspeed-console/tree/semver/goose/060826-1455) | [branch](https://github.com/jmontleon/lightspeed-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/lightspeed-console/tree/fix-engine) | [branch](https://github.com/jmontleon/lightspeed-console/tree/pf-codemods-plus-goose) |
| logging-view-plugin | [branch](https://github.com/jmontleon/logging-view-plugin/tree/semver/goose/060526-0019) | [branch](https://github.com/jmontleon/logging-view-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/logging-view-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/logging-view-plugin/tree/pf-codemods-plus-goose) |
| monitoring-plugin | [branch](https://github.com/jmontleon/monitoring-plugin/tree/semver/goose/060526-0300) | [branch](https://github.com/jmontleon/monitoring-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/monitoring-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/monitoring-plugin/tree/pf-codemods-plus-goose) |
| netobserv-web-console | [branch](https://github.com/jmontleon/netobserv-web-console/tree/semver/goose/060526-0019) | [branch](https://github.com/jmontleon/netobserv-web-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/netobserv-web-console/tree/fix-engine) | [branch](https://github.com/jmontleon/netobserv-web-console/tree/pf-codemods-plus-goose) |
| networking-console-plugin | [branch](https://github.com/jmontleon/networking-console-plugin/tree/semver/goose/060526-0300) | [branch](https://github.com/jmontleon/networking-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/networking-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/networking-console-plugin/tree/pf-codemods-plus-goose) |
| nmstate-console-plugin | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/semver/goose/060426-1851) | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/pf-codemods-plus-goose) |
| node-remediation-console | [branch](https://github.com/jmontleon/node-remediation-console/tree/semver/goose/060526-0136) | [branch](https://github.com/jmontleon/node-remediation-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/node-remediation-console/tree/fix-engine) | [branch](https://github.com/jmontleon/node-remediation-console/tree/pf-codemods-plus-goose) |
| odf-console | [branch](https://github.com/jmontleon/odf-console/tree/semver/goose/060426-1851) | [branch](https://github.com/jmontleon/odf-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/odf-console/tree/fix-engine) | [branch](https://github.com/jmontleon/odf-console/tree/pf-codemods-plus-goose) |
| openshift-servicemesh-plugin | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/semver/goose/060526-0136) | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/pf-codemods-plus-goose) |
| openshift-site-plugin | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/semver/goose/060526-0136) | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/pf-codemods-plus-goose) |
| troubleshooting-panel-console-plugin | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/semver/goose/060526-0019) | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/fix-engine) | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/pf-codemods-plus-goose) |

## Notes

<a id="console"></a>
**[1] console:** This is a monorepo. The main frontend package (`frontend/package.json`) remains on PF5 (`^5.4.10`) on both branches. Some sub-packages (`multicluster-sdk`, `react-form-wizard`) are already on PF6 in both branches. Neither tool fully updated the main frontend package to PF6.

<a id="batch"></a>
**[2] semver+goose 2026-06-04:** This batch run covered 17 of 19 repos (console and console-plugin-template were not included). Totals are out of the 17 repos run. The 9 repos with unit test suites in this batch were: console-plugin, forklift-console-plugin, kubevirt-plugin, logging-view-plugin, netobserv-web-console, nmstate-console-plugin, odf-console, openshift-site-plugin, troubleshooting-panel-console-plugin. odf-console was the only test failure (338/365 tests passing, 21 failing due to PF6 component behavior changes in tests). kubevirt-plugin was the only repo where core PF packages were not upgraded to v6 (build and tests still pass against PF5).
