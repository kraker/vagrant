# Vagrant

Vagrant project for spinning up test VMs.

## Prerequisites

1. Install the latest version of [Vagrant](https://developer.hashicorp.com/vagrant/install)
2. Install Oracle's [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Make sure that you install a _compatible_ [version](https://developer.hashicorp.com/vagrant/docs/providers/virtualbox). Vagrant tends to lag behind by 1-2 minor release versions for VB support...

> NOTE: For best results install the official VirtualBox package from Oracle's site. Some distributions or community repo's (e.g. rpmfusion) packages may not work with Vagrant.

### RHEL boxes

1. Register for a [Red Hat Developer Subscription for Individuals](https://developers.redhat.com/blog/2021/02/10/how-to-activate-your-no-cost-red-hat-enterprise-linux-subscription).
2. In order to register RHEL boxes instll the [vagrant-registration](https://github.com/projectatomic/adb-vagrant-registration) plugin.

```bash
vagrant plugin install vagrant-registration
```

## Usage

```bash
vagrant up         # Create and start VMs
vagrant ssh rocky8 # SSH into a VM
vagrant halt       # Stop VMs
vagrant destroy    # Destroy VMs
```

### RHEL

Setup your Red Hat credentials environment variables.

```bash
export SUB_USERNAME=rhusername
export SUB_USERNAME=rhpassword
```

Create and start RHEL boxes:

```bash
cd RHEL
vagrant up
```

## Author

* Alex Kraker (github.com/kraker)
