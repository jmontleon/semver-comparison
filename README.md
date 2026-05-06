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

| Repository | PF6 Dep Update | Build | Tests | PF6 Dep Update | Build | Tests |
|:-----------|:--------------:|:-----:|:-----:|:--------------:|:-----:|:-----:|
| | **pf-codemods** | | | **fix-engine** | | |
| [console](https://github.com/jmontleon/console) | :x: | :x: | :x: [[1]](#console) | :x: [[1]](#console) | :x: | :white_check_mark: |
| [console-plugin](https://github.com/jmontleon/console-plugin) | :x: | :x: | :x: | :white_check_mark: | :x: | :white_check_mark: |
| [console-plugin-template](https://github.com/jmontleon/console-plugin-template) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [distributed-tracing-console-plugin](https://github.com/jmontleon/distributed-tracing-console-plugin) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [forklift-console-plugin](https://github.com/jmontleon/forklift-console-plugin) | :x: | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| [gitops-console-plugin](https://github.com/jmontleon/gitops-console-plugin) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [kuadrant-console-plugin](https://github.com/jmontleon/kuadrant-console-plugin) | :x: | :x: | — | :white_check_mark: | :x: | — |
| [kubevirt-plugin](https://github.com/jmontleon/kubevirt-plugin) | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| [lightspeed-console](https://github.com/jmontleon/lightspeed-console) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [logging-view-plugin](https://github.com/jmontleon/logging-view-plugin) | :x: | :x: | :x: | :white_check_mark: | :x: | :x: |
| [monitoring-plugin](https://github.com/jmontleon/monitoring-plugin) | :x: | :x: | :x: | :white_check_mark: | :white_check_mark: | :x: |
| [netobserv-web-console](https://github.com/jmontleon/netobserv-web-console) | :x: | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| [networking-console-plugin](https://github.com/jmontleon/networking-console-plugin) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [nmstate-console-plugin](https://github.com/jmontleon/nmstate-console-plugin) | :x: | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| [node-remediation-console](https://github.com/jmontleon/node-remediation-console) | :x: | :x: | — | :white_check_mark: | :white_check_mark: | — |
| [odf-console](https://github.com/jmontleon/odf-console) | :x: | :x: | :x: | :white_check_mark: | :x: | :white_check_mark: |
| [openshift-servicemesh-plugin](https://github.com/jmontleon/openshift-servicemesh-plugin) | :x: | :x: | — | :white_check_mark: | :x: | — |
| [openshift-site-plugin](https://github.com/jmontleon/openshift-site-plugin) | :x: | :x: | :x: | :white_check_mark: | :white_check_mark: | :white_check_mark: |
| [troubleshooting-panel-console-plugin](https://github.com/jmontleon/troubleshooting-panel-console-plugin) | :x: | :x: | — | :white_check_mark: | :x: | — |

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
