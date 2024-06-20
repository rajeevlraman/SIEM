# WINDOWS ACTIVE DIRECTORY MONITORING USING SPLUNK ENTERPISE


## Task 1: Creating a Logical Diagram and Hardware Requirements


### Objectives
- Understand the overall architecture and purpose of the Active Directory setup.
- Create a logical network diagram to plan the virtual infrastructure.
- Determine the hardware and software requirements for the project.

### Creating a Logical Diagram
1. **Tools Needed:**
   - Use tools like Microsoft Visio, Lucidchart, or draw.io to create your network diagram.
   - I have used draw.io app in windows / also can be used online.

2. **Design Your Network Topology:**
   - Map out the placement of each virtual machine and its role:
     - **Windows Server 2022:** Primary Domain Controller.
     - **Windows 10 Client:** Workstation for domain joining.
     - **Kali Linux:** For penetration testing.
     - **Ubuntu Server:** For additional services.
   - Include network elements like routers, switches, and IP addressing schemes.
   - I have a Pfsense as a firewall and all traffic is through pfsense.

3. **Diagram Elements:**
   - Represent each VM with clear icons and labels.
   - Connect the VMs to depict their network relationships.
   - provide the IP address of each machine if possible.
   - provide the data flow in dotted lines.

![image](/assets/images/image1.png)

4. **Example Logical Diagram:**
   - **Router/Gateway:** Connects the internal network to the internet. (Pfsense)
   - **Switch:** Manages internal network connections. (Pfsense)
   - **VMs:**
     - ***Windows Server 2022 (AD DS)***  Domain Controller
     - ***Windows 10 Client***  Domain joinr PC
     - ***Kali Linux***  Attacker Machine
     - ***Ubuntu Server***  Splunk Server

5. **Save and Document:**
   - Save your diagram for reference.
   - Draw.io has plenty of save and export options.
   - Document each VM’s purpose and network configuration.

### Hardware Requirements
- **My hardware Specifications:**
  - **Processor:** Quad-core CPU AMD Ryzen 5 5600X.
  - **Memory:** 64GB RAM.
  - **Storage:** 1TB for OS and 2TB M.2 drive.
- **Virtualization Platform:**
  - **VirtualBox** installed and configured.
- **Network Configuration:**
  - One NIC for NAT / WAN
  - One NIC for LAN
  - Host only Adaptor with Promiscous mode enabled for all.
