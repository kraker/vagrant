# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

A collection of Vagrant configurations for spinning up test VMs using VirtualBox as the provider.

## Prerequisites

- [Vagrant](https://developer.hashicorp.com/vagrant/install) (latest)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) — install from Oracle's official site, not distro repos
- For RHEL boxes: `vagrant plugin install vagrant-registration` and a Red Hat Developer Subscription

## Common Commands

```bash
vagrant up              # Create and start all VMs in current Vagrantfile
vagrant up <name>       # Start a specific VM (e.g., vagrant up rocky9)
vagrant ssh <name>      # SSH into a VM
vagrant halt            # Stop all VMs
vagrant destroy         # Destroy all VMs
vagrant status          # Show VM status
```

## Repository Structure

- **`Vagrantfile`** — Root config; defines general Linux test boxes (CentOS, Rocky, openSUSE, Debian, Ubuntu) on the `10.0.0.x` private network with 512MB RAM / 1 CPU defaults
- **`rhel/Vagrantfile`** — RHCSA lab environment; two RHEL 9 VMs (`rhel9a`, `rhel9b`), with `rhel9b` having additional disks for storage exercises. Requires `SUB_USERNAME`/`SUB_PASSWORD` env vars for Red Hat subscription registration
- **`windows/Vagrantfile`** — Windows Server 2022 box with 8GB RAM / 4 CPUs
- **`rhel/playbook.yml`** — Ansible playbook for RHEL provisioning (full system update)
- **`hosts`** — Ansible inventory file for managing VMs outside Vagrant

## RHEL Setup

```bash
export SUB_USERNAME=rhusername
export SUB_PASSWORD=rhpassword
cd rhel
vagrant up
```

## IP Address Assignments

| VM | IP |
|---|---|
| centos7 | 10.0.0.10 |
| rocky8 | 10.0.0.11 |
| rocky9 | 10.0.0.12 |
| opensuse15.5 | 10.0.0.21 |
| debian11 | 10.0.0.30 |
| debian12 | 10.0.0.31 |
| ubuntu2004 | 10.0.0.40 |
| ubuntu2204 | 10.0.0.41 |
| ubuntu2404 | 10.0.0.42 |
