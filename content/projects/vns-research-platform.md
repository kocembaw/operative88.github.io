---
title: Vagus Nerve Stimulation Research Platform
layout: hero
---

It is a research platform that operates using only software and allows to browse the synthetic experiment data for VNS (vagus-nerve-stimulation).

The hardware has been deliberately left out of consideration since the aim of this project is to gain an understanding of cloud and DevOps infrastructure by containerising a small service, orchestrating it on Kubernetes, provisioning it on AWS using Terraform, and then delivering it via a Jenkins pipeline.

Just a few of the many interesting resources relating to VNS:

- [Transcutaneous auricular Vagus nerve stimulation for working memory enhancement](https://www.sciencedirect.com/science/article/pii/S1094715926013292)
- [Transcutaneous vagus nerve stimulation influences sleep quality and insomnia](https://www.sciencedirect.com/science/article/abs/pii/S1087079226000833)

## Architecture

![Architecture diagram of the VNS Research Platform](/images/vns-architecture.png)

All the elements on the left have an effect on the platform: Jenkins is responsible for building and deploying, Terraform handles the provisioning of the infrastructure, and the user makes use of the API. All the components within the AWS boundary are in the cloud; the EKS cluster contains two workloads (the API and the generator), while the database is located separately on RDS since it is a managed service outside the cluster.

Source code: [github.com/kocembaw/platform-vns](https://github.com/kocembaw/platform-vns)

[← Back to projects](/projects/)
