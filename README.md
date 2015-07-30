# vagrant-nodejs-ubuntu

Vagrant-based Node.js development environment using [Lubuntu](http://lubuntu.net/), with GUI (i.e., not headless).

The Vagrant base box is a minimal (~600 MB) Lubuntu 14.04 64-bit installation, [available from Atlas](https://atlas.hashicorp.com/halvards/boxes/lubuntu64).

## Installation

Prerequisites:

* [VirtualBox](https://www.virtualbox.org/wiki/Downloads), at least version 4.3.28
* [Vagrant](https://vagrantup.com/downloads.html). This has been tested using version 1.7.4
* [Ansible](https://github.com/ansible/ansible). This has been tested using version 1.9.2

Clone this repository, then from the repository folder run this command:

    vagrant up

The `vagrant` user password is `vagrant`.

## Notes

* Edit `playbook.yml` to select your Node.js/io.js version. Options are `node_0.10`, `node_0.12`, `iojs_1.x`, and `iojs_2.x`
* [nvm](https://github.com/creationix/nvm) is also installed, so it provides another mechanism to switch to other Node.js/io.js versions.
* Don't log in as user `vagrant` via the GUI until provisioning is complete. `~/.profile` is modified as part of provisioning, so if you log in before this is finished
* The Vagrantfile assumes a directory on the host called `~/dev`, which will be shared with the VM. Edit this path in the `Vagrantfile` to suit your environment.
* The login form appears twice after the VM has been created the first time. On subsequent reboots, it only appears once.
* The Vagrantfile copies your private key to the VM so you can access Github et al. via SSH. It assumes the private key file can be found in `~/.ssh/id_rsa`
* You can also SSH to the VM, using `vagrant ssh`
* Only Mac OS X and Linux hosts are supported. See [this example](https://github.com/halvards/vagrant-vm/blob/ansible/nodejs-ubuntu64/Vagrantfile) for a Windows host workaround.

