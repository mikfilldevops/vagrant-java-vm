# Vagrant Java App Setup for VirtualBox

Configurations:

- **Private Networking** with IP address `192.168.57.10`.
- **VirtualBox Configuration**:
  - **2 CPUs**.
  - **1024 MB** of memory.
- **Provisioning**:
  - Installs **OpenJDK 17**.
  - Configures environment variables (`APP_ENV=staging`).
  - Syncs a folder from the host to the VM (`./javavm-data` to `/vagrant_data`).

## Requirements

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)