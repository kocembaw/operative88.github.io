---
title: Vagus Nerve Stimulation Research Platform
layout: hero
---

it is a research platform that operates using only software and allows to browse the synthetic experiment data for vns (vagus nerve stimulation).

the hardware has been deliberately left out of consideration since the aim of this project is to gain an understanding of cloud and devops infrastructure by containerising a small service, orchestrating it on kubernetes, provisioning it on aws using terraform, and then delivering it via a jenkins pipeline.

just a few of the many interesting resources relating to vns:

- [transcutaneous auricular vagus nerve stimulation for working memory enhancement](https://www.sciencedirect.com/science/article/pii/S1094715926013292)
- [transcutaneous vagus nerve stimulation influences sleep quality and insomnia](https://www.sciencedirect.com/science/article/abs/pii/S1087079226000833)

## architecture

![architecture diagram of the vns research platform](/images/vns-architecture.png)

all the elements on the left have an effect on the platform: jenkins is responsible for building and deploying, terraform handles the provisioning of the infrastructure, and the user makes use of the api. all the components within the aws boundary are in the cloud; the eks cluster contains two workloads (the api and the generator), while the database is located separately on rds since it is a managed service outside the cluster.

source code: [github.com/kocembaw/platform-vns](https://github.com/kocembaw/platform-vns)

[← back to projects](/#projects)
