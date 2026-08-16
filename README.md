# Vagrant VM Lab

## Purpose
This project creates a reusable Ubuntu-based virtual machine for local development, testing, and automation lab work. It provides a consistent environment for experimenting with Linux configuration, package installation, and web services without affecting the host machine.

## Code Summary
The Vagrant configuration defines an Ubuntu 22.04 Jammy virtual machine using the VirtualBox provider. The VM is named "vagrant-ubuntu-lab" and is provisioned with:

- 2 virtual CPUs
- 1024 MB of memory
- Ubuntu Jammy 64-bit base box
- Apache web server installed during setup
- A non-root user named "vagrantuser" created with a password for administrative access
- The user added to the sudo group

The provisioning script runs automatically when the VM is created, updating the system and installing Apache2. This gives the lab an operational Linux environment for testing configurations and services.

## Workstream
- Infrastructure automation
- Virtual machine provisioning
- Local development environment setup
- Linux system configuration and user management
- Web service validation

## Dev Process
1. Install Vagrant and VirtualBox on the host machine.
2. Clone or open the project directory containing the Vagrantfile.
3. Run `vagrant up` to create and provision the Ubuntu VM.
4. Use `vagrant ssh` to connect to the guest environment.
5. Make changes, install packages, and validate behavior inside the VM.
6. Stop or clean up the environment with `vagrant halt` or `vagrant destroy` when finished.

## Test Process
- Confirm the VM boots successfully with `vagrant up`.
- Verify the provisioner runs without errors.
- Check Apache installation with `apache2 -v`.
- Validate the created user with `id vagrantuser`.
- Confirm the user can use sudo with `sudo whoami`.
- Review the VM status with `vagrant status`.

## Future Implementation
- Add SSH key-based authentication for secure, passwordless access
- Configure private or bridged networking for host-to-guest connectivity
- Add synced folders to mount local project files into the VM
- Expand provisioning to include application stacks, monitoring, or automation tooling
- Create repeatable environment profiles for different lab use cases
- SSH key pairs for secure guest access and simplified administration
