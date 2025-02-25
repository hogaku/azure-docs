---
title: Overview of upgrading Azure Kubernetes Service (AKS) clusters and components
description: Learn about the various upgradeable components of an Azure Kubernetes Service (AKS) cluster and how to maintain them.
author: nickomang
ms.author: nickoman
ms.service: container-service
ms.topic: conceptual
ms.date: 11/11/2022
---

# Upgrading Azure Kubernetes Service clusters and node pools

An Azure Kubernetes Service (AKS) cluster will periodically need to be updated to ensure security and compatibility with the latest features. There are two components of an AKS cluster that are necessary to maintain:

- *Cluster Kubernetes version*: Part of the AKS cluster lifecycle involves performing upgrades to the latest Kubernetes version. It’s important you upgrade to apply the latest security releases and to get access to the latest Kubernetes features, as well as to stay within the [AKS support window][supported-k8s-versions].
- *Node image version*: AKS regularly provides new node images with the latest OS and runtime updates. It's beneficial to upgrade your nodes' images regularly to ensure support for the latest AKS features and to apply essential security patches and hot fixes.

The following table summarizes the details of updating each component:

|Component name|Frequency of upgrade|Planned Maintenance supported|Supported operation methods|Documentation link|
|--|--|--|--|--|
|Cluster Kubernetes version (minor) upgrade|Roughly every three months|Yes| Automatic, Manual|[Upgrade an AKS cluster][upgrade-cluster]|
|Cluster Kubernetes version upgrade to supported patch version|Approximately weekly. To determine the latest applicable version in your region, see the [AKS release tracker][release-tracker]|Yes|Automatic, Manual|[Upgrade an AKS cluster][upgrade-cluster]|
|Node image version upgrade|**Linux**: weekly<br>**Windows**: monthly|Yes|Automatic, Manual|[AKS node image upgrade][node-image-upgrade]|
|Security patches and hot fixes for node images|As-necessary||||

## Automatic upgrades

Automatic upgrades can be performed through [auto upgrade channels][auto-upgrade] or via [GitHub Actions][gh-actions-upgrade].

## Planned maintenance

 [Planned maintenance][planned-maintenance] allows you to schedule weekly maintenance windows that will update your control plane as well as your kube-system pods, helping to minimize workload impact.

## Troubleshooting

To find details and solutions to specific issues, view the following troubleshooting guides:

- [Upgrade fails because of NSG rules][ts-nsg]

- [PodDrainFailure error][ts-pod-drain]

- [PublicIPCountLimitReached error][ts-ip-limit]

- [QuotaExceeded error][ts-quota-exceeded]

- [SubnetIsFull error][ts-subnet-full]

## Next steps

For more information what cluster operations may trigger specific upgrade events, see the [AKS operator's guide on patching][operator-guide-patching].

<!-- LINKS -->
[auto-upgrade]: ./auto-upgrade-cluster.md
[planned-maintenance]: ./planned-maintenance.md
[upgrade-cluster]: ./upgrade-cluster.md
[release-tracker]: ./release-tracker.md
[node-image-upgrade]: ./node-image-upgrade.md
[gh-actions-upgrade]: ./node-upgrade-github-actions.md 
[operator-guide-patching]: /azure/architecture/operator-guides/aks/aks-upgrade-practices#considerations
[supported-k8s-versions]: ./supported-kubernetes-versions.md#kubernetes-version-support-policy
[ts-nsg]: /troubleshoot/azure/azure-kubernetes/upgrade-fails-because-of-nsg-rules
[ts-pod-drain]: /troubleshoot/azure/azure-kubernetes/error-code-poddrainfailure
[ts-ip-limit]: /troubleshoot/azure/azure-kubernetes/error-code-publicipcountlimitreached
[ts-quota-exceeded]: /troubleshoot/azure/azure-kubernetes/error-code-quotaexceeded
[ts-subnet-full]: /troubleshoot/azure/azure-kubernetes/error-code-subnetisfull-upgrade
