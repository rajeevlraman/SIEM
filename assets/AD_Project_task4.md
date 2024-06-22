# Integrating Splunk with Active Directory for Enhanced Security and Insights
[Task 1](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task1.md), [Task 2](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_project_task2.md), [Task 3](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task3.md), [Task 4](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task4.md), [Task 5](https://github.com/rajeevlraman/SIEM/blob/main/assets/AD_Project_task5.md)<br><br>
![image](/assets/images/image1.png)

- ### Task 4:
     - Install and configure Splunk Enterprise
     - Install and configure Splunk Forwarder<br><br> 

1. **Download Splunk:**
   - Download from the [Splunk website](https://www.splunk.com/en_us/download/splunk-enterprise.html).

   - Create an account with splunk and you could use the Splunk Enterprise trial.
   
   - Once logged in you can use the trial and Download the installation package for various OS.
   
   - I need the  ` Linux package ` as I am using Ubuntu Server.

    ![image](/assets/images/image45a.png)<br>
   
   - you can download the ` .deb ` package or use the command ` wget ` command.
   
   - ```bash
     wget -O splunk-9.2.1-78803f08aabb-linux-2.6-amd64.deb "https://download.splunk.com/products/splunk/releases/9.2.1/linux/splunk-9.2.1-78803f08aabb-linux-2.6-amd64.deb"
     ```
    
    ![image](/assets/images/image45b.png)<br>

2. **Install Splunk:**
   - Follow the installation instructions and set up an admin account.

   - once installed you can open the server at ` 127.0.0.1:8000 ` locally, or

   - Using the IP of Ubuntu server, in my case ` 10.10.20.100:8000 1.

   - you will be presented with the login, provide admin credentials and login.<br><br>

    ![image](/assets/images/image45c.png)<br><br>

3. **Install Splunk Forwarders**

    ![image](/assets/images/image45d.png)<br>

    ![image](/assets/images/image45e.png)<br>

    ![image](/assets/images/image45f.png)<br>

     - once installed go to services and doubleclick on the splunk forwarder service

     - I the Log On tab change the account from ` NT SERVICE ` to local system account

     - This helps collect the logs better, because NT SERVICE might be bound by OS rules.

    ![image](/assets/images/image44.jpg)<br>

    ![image](/assets/images/image45.jpg)<br>

    ![image](/assets/images/image46.jpg)<br>   

     - You have to restart the the Splunk Forwarder Service.


4. **Configure Data Inputs for Sysmon:**
   - Go to “Settings” > “Data Inputs” in Splunk.
   - Add new inputs for monitoring Sysmon logs, typically from `XmlWinEventLog`.

   - You can clcik on ` Settings ` and then select ` Indexes `.

    ![image](/assets/images/image48.jpg)<br>

   - You can create a ` New Index ` and call it ` endpoint `

    ![image](/assets/images/image49.jpg)<br>

   - The default settings are fine, so you can save the Index.

    ![image](/assets/images/image50.jpg)<br>

    - In the Settings click on Forwarding and Recieving.

    ![image](/assets/images/image52.jpg)<br>

    - Click on Configure Recieving and add the Port specified in the Forwarder.

    - The Default Port is ` 9997 `

    - Now if You open a ` New Search `,  and filter ` Index = endpoint ` you can see there are events listed.

    ![image](/assets/images/image54.jpg)<br>

    - click on he Host on the left side menu and you can see 1 or 2 based on the forwarder services running.

    ![image](/assets/images/image56.jpg)<br>

    - you can see the Source as well.

    ![image](/assets/images/image57.jpg)<br>


   - Specify the input path and source type for Sysmon logs.<br><br>

### Testing and Verification
1. **Generate Test Logs:**
   - Perform typical activities on Windows machines to generate logs.<br><br>

2. **Monitor Logs in Splunk:**
   - Open Splunk’s search interface.
   - Use queries like `sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational"` to view logs.<br><br>

3. **Create Dashboards:**
   - Use Splunk’s dashboard feature to create visualizations and alerts based on Sysmon data.
