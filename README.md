# NETWORKWALKS-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP



## 📌 Project Overview

This project focuses on setting up a **virtual cybersecurity and penetration-testing laboratory** using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

---


## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install/import Kali Linux as a virtual machine.
- Create a private **NAT Network** for the cybersecurity lab.
- Configure network connectivity for Kali Linux.

---


## Install and configure VirtualBox.

![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-and-configure-VirtualBox.png)
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-and-configure-Virtual-Box1.png)
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-and-configure-VirtualBox-2.png)


---

## Install/import Kali Linux as a virtual machine.
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-import-Kali-Linux-as-a-virtual-machine.png)
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-import-Kali-Linux-as-a-virtual-machine1.png)
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Install-import-Kali-Linux-as-a-virtual-machine2.png)

---
## Create a private NAT Network for the cybersecurity lab.
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Create-a-private-NAT-Network-for-the-cybersecurity-lab.png)

---
## Configure the Kali Linux Network

![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Configure-the-Kali-Linux-Network.png)
![NETWORKWALKS-B082-WK1-PM1-CYBERSECURITY-LAB-SETUP](Configure-the-Kali-Linux-Network2.png)

---




## Issues Encountered and Solutions

### 1. Kali Linux Installation Failed

**Issue:**  
The Kali Linux installation failed twice while attempting to install the operating system on the virtual machine.

**Cause:**  
The virtual machine's resource allocation and network configuration may have contributed to the installation failures.

**Solution Implemented:**
- Adjusted the number of CPUs allocated to the virtual machine.
- Modified the virtual machine's network connection settings.
- Retried the installation after making the configuration changes.

**Outcome:**  
The configuration changes allowed me to proceed with the Kali Linux installation successfully.

### 2. No Internet Connectivity in Kali Linux

**Issue:**  
After installing Kali Linux, the virtual machine could not access the internet.

**Cause:**  
The IPv4 settings on the host computer's network adapter had been modified, affecting network connectivity.

**Solution Implemented:**
- Opened the IPv4 properties for the network adapter on the host computer.
- Reverted the IPv4 configuration to its previous settings.
- Tested network connectivity again after restoring the original configuration.

**Outcome:**  
Restoring the previous IPv4 settings addressed the network configuration issue and helped restore connectivity.

### 3. Destination Host Unreachable Error

**Issue:**  
While testing network connectivity using the `ping` command, the following error appeared:

```text
PING 10.0.0.1 (10.0.0.1) 56(84) bytes of data.
From 10.0.0.2 icmp_seq=1 Destination Host Unreachable
From 10.0.0.2 icmp_seq=2 Destination Host Unreachable
```

**Possible Cause:**  
The Kali Linux virtual machine could not reach the target IP address. Potential causes include an incorrect gateway address, an IP configuration issue, or an incorrectly configured virtual network adapter.

**Troubleshooting Steps:**

1. Checked the network interface configuration:
   ```bash
   ip -br addr
   ```

2. Inspected the routing table:
   ```bash
   ip route
   ```

3. Checked the neighbor table:
   ```bash
   ip neigh show
   ```

4. Reviewed the virtual machine's network adapter configuration to verify that the adapter was enabled and connected.

**Next Step:**  
Confirm the correct gateway address and virtual network mode, then retest connectivity.

> Note: The `Destination Host Unreachable` error has been observed, but a final resolution for this specific error has not yet been confirmed.

## Lessons Learned

- Virtual machine resource allocation can affect operating system installation.
- Network adapter settings should be reviewed when troubleshooting virtual machine connectivity.
- Changes to IPv4 configuration can affect network access.
- Restoring previously working network settings can help isolate configuration-related problems.
- Network troubleshooting should begin with basic diagnostic commands before making additional configuration changes.

## Useful Network Troubleshooting Commands

| Command | Purpose |
|---|---|
| `ip -br addr` | Displays network interfaces and IP addresses |
| `ip route` | Displays routing information |
| `ip neigh show` | Displays neighboring devices and their reachability states |
| `ping -c 4 10.0.0.1` | Tests connectivity to the target IP address |
| `ip link show` | Displays network interface status |

## Conclusion

The main challenges during this setup involved the initial Kali Linux installation and network connectivity. Adjusting the virtual machine's CPU allocation and network settings helped resolve the installation problem. Restoring the host computer's original IPv4 configuration helped address the internet connectivity issue.

Further troubleshooting is required to confirm the cause and resolution of the `Destination Host Unreachable` error.

This experience reinforced the importance of checking virtual machine resources, network adapter configurations, IP addressing, and routing when setting up and troubleshooting a Kali Linux environment.



## 📌 Security and Ethical Considerations

This environment is intended for authorized cybersecurity learning and testing.

Cybersecurity tools should only be used against systems and networks for which permission has been granted.

## 🖋️ ****Author****

Rishauna Gunning     

Cybersecurity Trainee B084

https://www.linkedin.com/in/rishauna-gunning-876ab9109/
