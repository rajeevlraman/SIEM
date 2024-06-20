# WINDOWS ACTIVE DIRECTORY MONITORING USING SPLUNK ENTERPISE


![image](/assets/images/image1.png)

### Objectives
- ## Set up virtual machines (VMs) for Windows 10, Kali Linux, Ubuntu Server, and Windows Server 2022.

### Installing Virtual Machines (VMs)
1. **Download ISOs:**
     - Obtain ISO files from the respective official websites:
     - **Windows 10:** [Microsoft](https://www.microsoft.com/en-us/software-download/windows10ISO)
     - **Kali Linux:** [Kali Linux](https://www.kali.org/get-kali/)
     - **Ubuntu Server:** [Ubuntu](https://ubuntu.com/download/server)
     - **Windows Server 2022:** [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022)

2. **Create Virtual Machines:**
   - **Windows 10 VM:**
     - Open VirtualBox.
     - Create a new VM and select Windows 10 as the OS.

     - Allocate resources (2-4 GB RAM, 40-60 GB storage).

     - Attach the Windows 10 ISO and start the installation.<br><br>

   - **Kali Linux VM:**

     - Create a new VM, select Linux and Debian (64-bit).

     - Allocate resources (2 GB RAM, 20 GB storage).

     - Attach the Kali ISO and proceed with the installation.<br><br>
     
   - **Ubuntu Server VM:**

     - Create a new VM, select Linux and Ubuntu (64-bit).
     - Allocate resources (2 GB RAM, 20 GB storage).
     - Attach the Ubuntu ISO and follow the installation steps.<br><br>
   - **Windows Server 2022 VM:**
     - Create a new VM, select Windows Server 2022.
     - Allocate resources (4 GB RAM, 40 GB storage).
     - Attach the Windows Server ISO and start the installation.<br><br>

### Post-Installation Configuration

- **Network Setup:**

  - Configure each VM’s network adapter to use the appropriate network type (NAT, Bridged, or Host-only).

  - I have all my VMs on Host only adaptors.

  - I have my Pfsense as a Gateway to all except the windows 10 pc.<br><br>

- **Install Updates and Tools:**

  - After installation, update each VM with the latest patches.

  - Install guest additions/tools provided by VirtualBox/VMware for better performance and integration.
