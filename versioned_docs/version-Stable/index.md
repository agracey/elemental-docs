---
slug: /
sidebar_label: Overview
title: ''
---

# Overview

Elemental is a software stack enabling a centralized, full cloud-native OS management with Kubernetes.

The Elemental Stack consists of some packages on top of SLE Micro for Rancher:

- **elemental-toolkit** - includes a set of OS utilities to enable OS management via containers. Includes dracut modules, bootloader configuration, cloud-init style configuration services, etc.
- **elemental-operator** - this connects to Rancher Manager and handles MachineRegistration and MachineInventory CRDs
- **elemental-register** - this registers machines via machineRegistrations and installs them via elemental-cli
- **elemental-cli** - this installs any elemental-toolkit based derivative. Basically an installer based on our A/B install and upgrade system
- **rancher-system-agent** - runs on the installed system and gets instructions ("Plans") from Rancher Manager what to install and run on the system

Cluster Node OSes are built and maintained via container images through the <Vars name="elemental_cli_name" /> and they can be installed on new hosts using the <Vars link="elemental_ui_url" name="elemental_ui_name" /> for [Rancher Manager](https://www.rancher.com/products/rancher) or the <Vars link="elemental_cli_url" name="elemental_cli_name" />.

The <Vars link="elemental_operator_url" name="elemental_operator_name" /> and the <Vars link="ranchersystemagent_url" name="ranchersystemagent_name" /> enable Rancher Manager to fully control Elemental clusters, from the installation and management of the OS on the Nodes to the provisioning of new K3s or RKE2 clusters in a centralized way.

## What is Elemental Teal ?

Elemental Teal is the combination of "SLE Micro for Rancher" with the Rancher Elemental stack.

SLE Micro for Rancher is a containerized and "stripped to the bones"
operating system layer. At its core, it only requires grub2, dracut, a kernel, and systemd.

Its sole purpose is to run Kubernetes (k3s or RKE2), with everything controlled through Rancher Manager.

Elemental Teal is built in the [openSUSE Build Service](https://build.opensuse.org/package/show/isv:Rancher:Elemental:Stable:Teal53/node-image)
and available through the [openSUSE Registry](https://registry.opensuse.org/cgi-bin/cooverview?srch_term=project%3D%5Eisv%3ARancher%3AElemental%3AStable+container%3D.*).

### Elemental on x86-64 hardware

Elemental Teal is production ready and fully supported on x86-64 with Rancher v2.7.0.

### Elemental on ARM hardware

ARM (aarch64) is functional in the development version. ARM is currently only tested on Raspberry Pi 4 Model B with k3s 1.24.8 (or later). We welcome feedback !

### Elemental on other hardware

Elemental is currently targeting 'edge' scenarios and does therefore not support other hardware.
We will revise this as the market evolves.

## Ready to give it a try?

Get an Elemental Cluster up and running with your preferred method

* With Rancher manager [Elemental plugin](quickstart-ui.md)
* With the [Elemental CLI](quickstart-cli.md)

:::note What's next?
Want more details? Take a look at the [Architecture](architecture.md) section or reach out to the <Vars link="elemental_slack_url" name="elemental_slack_name" /> Slack channel.
:::
