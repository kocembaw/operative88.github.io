---
title: SNPedia Knowledge Exporter
layout: hero
---

This is a custom Prometheus exporter written in Python that collects statistics about SNPedia, a wiki about human genetic variation, through the MediaWiki Action API. The exporter, Prometheus and Grafana are deployed to a single virtual machine with one Ansible playbook.

Once deployed, the exporter fetches data from SNPedia in the background every 30 minutes and exposes it on /metrics. Prometheus scrapes these metrics and evaluates alerting rules, while Grafana shows how many SNPs, genes and conditions the wiki describes, how actively it is edited, and how many days have passed since the last change. Because /metrics only serves cached values, Prometheus scrapes never generate traffic to SNPedia.

## Architecture

![Architecture diagram of the SNPedia Knowledge Exporter](/images/snpedia-architecture.png)

Source code: [github.com/kocembaw/SNPedia-Grafana](https://github.com/kocembaw/SNPedia-Grafana)

[← Back to projects](/projects/)
