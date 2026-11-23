---
title: SNPedia Knowledge Exporter
layout: hero
---

this is a custom prometheus exporter written in python that collects statistics about snpedia, a wiki about human genetic variation, through the mediawiki action api. the exporter, prometheus and grafana are deployed to a single virtual machine with one ansible playbook.

once deployed, the exporter fetches data from snpedia in the background every 30 minutes and exposes it on /metrics. prometheus scrapes these metrics and evaluates alerting rules, while grafana shows how many snps, genes and conditions the wiki describes, how actively it is edited, and how many days have passed since the last change. because /metrics only serves cached values, prometheus scrapes never generate traffic to snpedia.

## architecture

![architecture diagram of the snpedia knowledge exporter](/images/snpedia-architecture.png)

source code: [github.com/kocembaw/snpedia-grafana](https://github.com/kocembaw/SNPedia-Grafana)

[← back to projects](/#projects)
