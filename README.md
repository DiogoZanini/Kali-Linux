# Kali-Linux
Kali Linux analyst virtual machine for security analysis of the homelab environment and CTF challenges on online study platforms.

[**PT-BR**](./docs/README.pt-br.md)

![Kali Login](./docs/kali_login.png)

## Dependencies
- [Oracle VirtualBox](https://www.virtualbox.org/) — Virtualization platform;
- [Kali Linux](https://www.kali.org/get-kali/#kali-platforms) ISO or Pre-built Virtual Machine;

## Getting Started
<details>
  <summary>Virtual Machine configuration</summary>

  - Base Memory: 2048 MB; (adaptable depending on the use)
  - Number of CPUs: 2 CPUs; (adaptable depending on the use)
  - Disk Size: 100 GB. (adaptable depending on stored data)

  Create a new VM and attach two Network Interface Cards (NICs):
  1. **Adapter 1** — External/Internet (NAT or Bridged) for CTF platforms and internet access;
  2. **Adapter 2** — Internal Network (homelab) for isolated lab environment.

</details>