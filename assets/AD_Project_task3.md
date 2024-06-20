# WINDOWS ACTIVE DIRECTORY MONITORING USING SPLUNK ENTERPISE
[Task 1](https://github.com/rajeevlraman/SIEM/edit/main/assets/AD_Project_task1.md), [Task 2](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_project_task2.md), [Task 3](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task3.md), [Task 4](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task4.md), [Task 5](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task5.md)<br><br>

![image](/assets/images/image1.png)

- ### Task 3:
     - Setup Windows Active Directory
     - Domain join windows 10 pc
     - Create Organizational Units and users
     - Install and configure Sysmon <br><br>


### Installing Active Directory Domain Services (AD DS)
1. **Add AD DS Role:**
   - Open Server Manager and select “Add roles and features”.
   - Choose the AD DS role and complete the installation.

2. **Promote to Domain Controller:**
   - After AD DS installation, run the AD DS Configuration Wizard.
   - Select “Add a new forest” and specify the domain name (`SECUREDASHER.local`).
   - Configure DNS settings and Directory Services Restore Mode (DSRM) password.
   - Complete the setup and restart the server.

3. **Verify Installation:**
   - Use the “Active Directory Users and Computers” console to verify AD DS functionality.
   - Check DNS settings to confirm the server’s role as a Domain Controller.

4. **Create Organizational Units and users**
   - Open `Active Directory users and computers `
   - Right click on Domain Controller and select new Organizational Unit
   - Create IT and HR OU.

    ![image](/assets/images/image22.jpg)<br>

   - In each OU create a new user.<br>

    ![image](/assets/images/image23.jpg)<br>
    ![image](/assets/images/image25.jpg)<br>   

### Joining a Windows 10 PC to the Domain
1. **Network Configuration:**
   - Login to the Windows 10 PC.
   - Ensure the Windows 10 PC uses the Domain Controller’s IP as the primary DNS server
   
 2. **Join the Domain:**
   - Open System Properties > “Computer Name” > “Change”.
   - Select “Domain” and enter the domain name ` SECUREDASHER.LOCAL `.
   - Provide domain admin credentials to join the domain.

3. **Restart and Log In:**
   - Restart the PC.
   - Log in with a domain user account.

### Installing Sysmon on Windows machines

1. **Download Sysmon:**
   - Get Sysmon from the [Microsoft Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon) website.<br><bR>
   - Download a config file from github ` sysmonconfig.xml ` <br><br>    

    ![image](/assets/images/image38.jpg)<br>    



2. **Install Sysmon on Windows Machines:**
   
   - open powershell as administrator and go to the Sysmon folder.<br>

   - ```bash
     sysmon64.exe -i sysmonconfig.xml     
     ```
    ![image](/assets/images/image39.jpg)<br>

    ![image](/assets/images/image40.jpg)<br>


   - We need to ceate a inputs.conf file in the local directory of Sysmon.
   - copy this content from the github file
   ```bash

    [
    [WinEventLog://Application]

    index = endpoint

    disabled = false

    [WinEventLog://Security]

    index = endpoint

    disabled = false

    [WinEventLog://System]

    index = endpoint

    disabled = false

    [WinEventLog://Microsoft-Windows-Sysmon/Operational]

    index = endpoint

    disabled = false

    renderXml = true

    source = XmlWinEventLog:Microsoft-Windows-Sysmon/Operational

    ]

   ```
   - Open Command Prompt as Administrator.
   - Execute the Sysmon installation with a configuration file:<br>
   - Customize the `sysmonconfig.xml` file for your logging needs or use a standard config from trusted sources.

    ![image](/assets/images/image41.jpg)<br>

   - This completes the Sysmon installation.
   - just reboot the PC.
   - Similarly Install and configure the sysmon in the Windows server.

Now that the Active directory is setup and Sysmon is setup we can setup the Splunk Server.

