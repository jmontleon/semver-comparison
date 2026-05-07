# PatternFly 5 to 6 Migration: Tool Comparison

Comparison of two automated migration tools — **pf-codemods** and **fix-engine** — across 19 OpenShift console plugin repositories.

> **Last updated:** 2026-05-06

## Summary

|                          | pf-codemods | fix-engine |
|--------------------------|:-----------:|:----------:|
| PF6 Dependency Update    | 0 / 19      | 18 / 19    |
| Build passing            | 0 / 19      | 13 / 19    |
| Tests passing            | 1 / 10      | 8 / 10     |

## Results by Repository

| Repository | PF6 Dep Update | Build | Tests | Runtime | PF6 Dep Update | Build | Tests | Runtime | Runtime |
|:-----------|:--------------:|:-----:|:-----:|--------:|:--------------:|:-----:|:-----:|--------:|--------:|
| | **pf-codemods** | | | | **fix-engine** | | | | **pf-codemods + goose** |
| [console](https://github.com/jmontleon/console) | :x: | :x: | :x: [[1]](#console) | 54s | :x: [[1]](#console) | :x: | :white_check_mark: | N/A | 3h 10m |
| [console-plugin](https://github.com/jmontleon/console-plugin) | :x: | :x: | :x: | 16s | :white_check_mark: | :x: | :white_check_mark: | 37m 34s | 41m 36s |
| [console-plugin-template](https://github.com/jmontleon/console-plugin-template) | :x: | :x: | — | 4s | :white_check_mark: | :white_check_mark: | — | 4m 43s | 2m 30s |
| [distributed-tracing-console-plugin](https://github.com/jmontleon/distributed-tracing-console-plugin) | :x: | :x: | — | 41s | :white_check_mark: | :white_check_mark: | — | 10m 59s | 3m 25s |
| [forklift-console-plugin](https://github.com/jmontleon/forklift-console-plugin) | :x: | :x: | :x: | 1m 6s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 52m 1s | 22m 40s |
| [gitops-console-plugin](https://github.com/jmontleon/gitops-console-plugin) | :x: | :x: | — | 3s | :white_check_mark: | :white_check_mark: | — | 8m 12s | 3m 27s |
| [kuadrant-console-plugin](https://github.com/jmontleon/kuadrant-console-plugin) | :x: | :x: | — | 22s | :white_check_mark: | :x: | — | 10m 14s | 2m 33s |
| [kubevirt-plugin](https://github.com/jmontleon/kubevirt-plugin) | :x: | :x: | :white_check_mark: | 25s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 1h 21m | 8m 57s |
| [lightspeed-console](https://github.com/jmontleon/lightspeed-console) | :x: | :x: | — | 14s | :white_check_mark: | :white_check_mark: | — | 5m 8s | 3m 35s |
| [logging-view-plugin](https://github.com/jmontleon/logging-view-plugin) | :x: | :x: | :x: | 40s | :white_check_mark: | :x: | :x: | 9m 50s | 15m 9s |
| [monitoring-plugin](https://github.com/jmontleon/monitoring-plugin) | :x: | :x: | :x: | 1m 7s | :white_check_mark: | :white_check_mark: | :x: | 31m 37s | 11m 46s |
| [netobserv-web-console](https://github.com/jmontleon/netobserv-web-console) | :x: | :x: | :x: | 58s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 47m 24s | 12m 49s |
| [networking-console-plugin](https://github.com/jmontleon/networking-console-plugin) | :x: | :x: | — | 7s | :white_check_mark: | :white_check_mark: | — | 24m 40s | 6m 44s |
| [nmstate-console-plugin](https://github.com/jmontleon/nmstate-console-plugin) | :x: | :x: | :x: | 6s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 9m 13s | 2m 2s |
| [node-remediation-console](https://github.com/jmontleon/node-remediation-console) | :x: | :x: | — | 18s | :white_check_mark: | :white_check_mark: | — | 16m 18s | 6m 54s |
| [odf-console](https://github.com/jmontleon/odf-console) | :x: | :x: | :x: | 25s | :white_check_mark: | :x: | :white_check_mark: | 1h 50m | 1h 11m |
| [openshift-servicemesh-plugin](https://github.com/jmontleon/openshift-servicemesh-plugin) | :x: | :x: | — | 20s | :white_check_mark: | :x: | — | 36m 38s | 1h 32m |
| [openshift-site-plugin](https://github.com/jmontleon/openshift-site-plugin) | :x: | :x: | :x: | 17s | :white_check_mark: | :white_check_mark: | :white_check_mark: | 13m 27s | 8m 57s |
| [troubleshooting-panel-console-plugin](https://github.com/jmontleon/troubleshooting-panel-console-plugin) | :x: | :x: | — | 14s | :white_check_mark: | :x: | — | 6m 25s | 4m 30s |

**Legend:** :white_check_mark: = Pass | :x: = Fail | — = No test suite

## Branch Links

| Repository | pf-codemods | fix-engine |
|:-----------|:----------:|:----------:|
| console | [branch](https://github.com/jmontleon/console/tree/pf-codemods) | [branch](https://github.com/jmontleon/console/tree/fix-engine) |
| console-plugin | [branch](https://github.com/jmontleon/console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/console-plugin/tree/fix-engine) |
| console-plugin-template | [branch](https://github.com/jmontleon/console-plugin-template/tree/pf-codemods) | [branch](https://github.com/jmontleon/console-plugin-template/tree/fix-engine) |
| distributed-tracing-console-plugin | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/distributed-tracing-console-plugin/tree/fix-engine) |
| forklift-console-plugin | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/forklift-console-plugin/tree/fix-engine) |
| gitops-console-plugin | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/gitops-console-plugin/tree/fix-engine) |
| kuadrant-console-plugin | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/kuadrant-console-plugin/tree/fix-engine) |
| kubevirt-plugin | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/kubevirt-plugin/tree/fix-engine) |
| lightspeed-console | [branch](https://github.com/jmontleon/lightspeed-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/lightspeed-console/tree/fix-engine) |
| logging-view-plugin | [branch](https://github.com/jmontleon/logging-view-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/logging-view-plugin/tree/fix-engine) |
| monitoring-plugin | [branch](https://github.com/jmontleon/monitoring-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/monitoring-plugin/tree/fix-engine) |
| netobserv-web-console | [branch](https://github.com/jmontleon/netobserv-web-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/netobserv-web-console/tree/fix-engine) |
| networking-console-plugin | [branch](https://github.com/jmontleon/networking-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/networking-console-plugin/tree/fix-engine) |
| nmstate-console-plugin | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/nmstate-console-plugin/tree/fix-engine) |
| node-remediation-console | [branch](https://github.com/jmontleon/node-remediation-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/node-remediation-console/tree/fix-engine) |
| odf-console | [branch](https://github.com/jmontleon/odf-console/tree/pf-codemods) | [branch](https://github.com/jmontleon/odf-console/tree/fix-engine) |
| openshift-servicemesh-plugin | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/openshift-servicemesh-plugin/tree/fix-engine) |
| openshift-site-plugin | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/openshift-site-plugin/tree/fix-engine) |
| troubleshooting-panel-console-plugin | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/pf-codemods) | [branch](https://github.com/jmontleon/troubleshooting-panel-console-plugin/tree/fix-engine) |

## Notes

<a id="console"></a>
**[1] console:** This is a monorepo. The main frontend package (`frontend/package.json`) remains on PF5 (`^5.4.10`) on both branches. Some sub-packages (`multicluster-sdk`, `react-form-wizard`) are already on PF6 in both branches. Neither tool fully updated the main frontend package to PF6.
