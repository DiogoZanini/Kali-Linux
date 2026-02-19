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

  > 💡 **Note:** If you're using the Pre-built VM image instead of installing from ISO, the default credentials are:
  > - Username: `kali`
  > - Password: `kali`

</details>

## Usage
<details>
  <summary>Managing Network</summary>

  You can toggle the network connection by checking or unchecking `[ ] Virtual Cable Connection` in the Kali Linux VM network settings for each adapter.

  - **Internet access:**
  Enable cable connection on Adapter 1 (External/Internet). Used for CTF challenges on online study platforms.

  - **Isolated environment:**
  Disable cable connection on Adapter 1 and enable Adapter 2 (Internal Network - homelab). Used for isolated lab environment, safe malware analysis, or controlled testing.
</details>

<details>
  <summary>Updating Kali Linux</summary>

  Kali is a rolling release distribution, meaning it receives continuous updates. Keep your system up to date for the latest security patches and features.

  - **System update (rolling release):**
  Updates the entire system to the latest rolling release version.
  ```bash
  sudo apt update && sudo apt full-upgrade -y
  ```
  ```bash
  sudo apt autoremove -y && sudo apt autoclean
  ```

  - **Package update only:**
  Updates only installed packages without major system changes.
```bash
  sudo apt update && sudo apt upgrade -y
```

  **Note:** Run system updates regularly, especially before starting security assessments or CTF challenges.
</details>