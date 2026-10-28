# Networkwalks-Week-1-Project---Cybersecurity-Lab-Setup
# Cybersecurity Home Lab (VirtualBox)

## Overview
A virtualized lab built in Oracle VirtualBox for hands-on cybersecurity practice, consisting of three machines:

| VM | Role |
|----|------|
| **Kali Linux** | Attacker machine (penetration testing and security tools) |
| **Windows** | Target machine (vulnerability assessment, hardening, log analysis) |
| **Android** | Mobile target (mobile app and device security testing) |

## Why This Lab Matters
- **Safe environment:** Test attacks and tools without risking real systems or breaking the law.
- **Realistic practice:** Simulates attacker-versus-target scenarios across desktop and mobile platforms.
- **Skill development:** Builds practical experience in reconnaissance, exploitation, and defense.
- **Reproducible:** Snapshots allow quick rollback after every experiment.
- **Cost-effective:** Runs on a single host machine with free, open-source software.

## Prerequisites
- Host machine with at least 16 GB RAM, 100 GB free disk space, and virtualization (VT-x/AMD-V) enabled in BIOS
- [Oracle VirtualBox](https://www.virtualbox.org/) and its Extension Pack installed

## Installation Steps

### 1. Kali Linux
1. Download the pre-built **VirtualBox image** from [kali.org/get-kali](https://www.kali.org/get-kali/#kali-virtual-machines).
2. Extract the archive and double-click the `.vbox` file (or use **File > Import Appliance** for an `.ova`).
3. Allocate 4 GB RAM and 2 CPUs under **Settings > System**.
4. Start the VM and log in (default credentials: `kali` / `kali`), then change the password.
5. Run `sudo apt update && sudo apt full-upgrade -y`.

### 2. Windows
1. Download a Windows 10/11 ISO from [Microsoft](https://www.microsoft.com/software-download).
2. In VirtualBox, click **New**, select the ISO, and choose type **Microsoft Windows**.
3. Allocate 4 GB RAM, 2 CPUs, and 50 GB disk.
4. Complete the Windows installation.
5. Install **Guest Additions** (**Devices > Insert Guest Additions CD Image**) and reboot.

### 3. Android
1. Download the [Android-x86](https://www.android-x86.org/) ISO.
2. Click **New**, select type **Linux** and version **Other Linux (64-bit)**.
3. Allocate 2 GB RAM, 2 CPUs, and 16 GB disk. Under **Display**, set graphics controller to **VMSVGA**.
4. Boot from the ISO and choose **Installation**.
5. Partition the disk (`cfdisk`), format as `ext4`, install GRUB when prompted, then reboot after removing the ISO.

## Network Configuration
1. For each VM, go to **Settings > Network**.
2. Set the adapter to **Host-Only** or **Internal Network** so all VMs communicate with each other but stay isolated from the internet and your home network.
3. Add a second **NAT** adapter to Kali only when it needs internet for updates.
4. Verify connectivity with `ping` between machines.

## Note: Find the Screenshots of the steps on 

## Best Practices
- Take a **snapshot** of each VM after setup (clean baseline).
- Never expose vulnerable VMs to a public network.
- Only test systems you own or have explicit permission to test.

## Disclaimer
This lab is for educational purposes only.
