# WINDOWS ACTIVE DIRECTORY MONITORING USING SPLUNK ENTERPISE

## OBJECTIVE:<br>

- Setting up and IDS for Windows machines using Splunk Enterprise
- Redatomic Testing on windows using MITRE ATT&CK framework.
- Automating Alerts using atomicred team<br><br>

## TASKS:<br>

- ### Task 1:
     - Creating a Network toplogy for the lab
     - Creating a logical workflow Diagram for the lab
     - Setting up the Virtual environment for the lab<br><br>
- ### Task 2:
     - Installing Virtual Machines<br><br>
 - ### Task 3:
     - Setup Windows Active Directory
     - Domain join windows 10 pc
     - Create Organizational Units and users
     - Install and configure Sysmon <br><br>
- ### Task 4:
     - Install and configure Splunk Enterprise
     - Install and configure Splunk Forwarder<br><br> 
- ### Task 5:
     - Setup Kali Linux for Brute force attack
     - Monitor Splunk for the attack events
     - setup redatomic team on windows
     - Perform Test using redatomic team using MITRE ATT&CK <br><br>

# TAKEAWAY FROM THE LAB


![image](https://github.com/rajeevlraman/SIEM/assets/85452477/bcb3bf3a-7658-4b88-a852-a4266d28eb1a)



## Task 1: Creating a Logical Diagram and Hardware Requirements


### Objectives
- Understand the overall architecture and purpose of the Active Directory setup.
- Create a logical network diagram to plan the virtual infrastructure.
- Determine the hardware and software requirements for the project.

### Creating a Logical Diagram
1. **Tools Needed:**
   - Use tools like Microsoft Visio, Lucidchart, or draw.io to create your network diagram.
   - I have used draw.io app in windows / also can be used online.

![image](/assets/images/Image2.jpg)

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

![image](/assets/images/Image2.jpg)

4. **Example Logical Diagram:**
   - **Router/Gateway:** Connects the internal network to the internet.
   - **Switch:** Manages internal network connections.
   - **VMs:**
     - Windows Server 2022 (AD DS)
     - Windows 10 Client
     - Kali Linux
     - Ubuntu Server

5. **Save and Document:**
   - Save your diagram for reference.
   - Document each VM’s purpose and network configuration.

### Hardware Requirements
- **Minimum Specifications:**
  - **Processor:** Quad-core CPU (e.g., Intel i5/i7 or AMD Ryzen 5/7).
  - **Memory:** At least 16 GB of RAM (32 GB recommended for smoother performance).
  - **Storage:** SSD with at least 200 GB free space.
- **Virtualization Platform:**
  - Ensure you have VMware Workstation or VirtualBox installed and configured.
- **Network Configuration:**
  - Ensure your network interface card (NIC) supports multiple virtual adapters.
  - Plan network settings for internal VM communication.
