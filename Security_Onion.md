**Security Onion**

Security Onion is a Linux distribution focused on intrusion detection, network security monitoring, and log management.

### Key Features:

- **Intrusion Detection Systems (IDS):** Integrates tools like Suricata and Zeek (formerly known as Bro) for real-time network traffic analysis and threat detection.
- **Network Security Monitoring (NSM):** Collects and analyzes network traffic to detect and respond to security incidents.
- **Log Management:** Centralizes and analyzes logs from various sources for forensic analysis and compliance.
- **Visualization and Analysis:** Provides tools like Kibana and Squert for visualizing security data and conducting investigations.
- **Scalability:** Scales from small environments to large enterprise networks with distributed sensor deployments.

### Components:

- **Suricata:** IDS/IPS engine for detecting intrusions and monitoring network traffic.
- **Zeek (Bro):** Network analysis framework for traffic inspection, protocol analysis, and logging.
- **Elastic Stack:** Includes Elasticsearch, Logstash, and Kibana for data indexing, parsing, storage, and visualization.
- **Wazuh:** Host-based intrusion detection system (HIDS) for endpoint security monitoring and threat detection.
- **Grafana:** Grafana displays wonderful dashboards to visualize the data and interpret the trafiic.

### Use Cases:

- **Threat Detection:** Proactively identifies and responds to network threats and security incidents.
- **Incident Response:** Facilitates investigation and analysis of security events for rapid response and mitigation.
- **Compliance:** Helps organizations meet regulatory compliance requirements by monitoring and managing security logs.

### Learn More:

- [Security Onion Official Website](https://securityonion.net/)
- [Security Onion GitHub Repository](https://github.com/Security-Onion-Solutions/securityonion)

Security Onion provides a comprehensive suite of tools and capabilities for network security monitoring and intrusion detection, making it suitable for both small deployments and large-scale enterprise environments.
<a name="install"></a>
# Installation of Security Onion


<!-- -------------------------- -->
- Security Onion requires two NICs: one for monitoring traffic and another for management.

<img align="center" src="" /><br>

- In my case, I only have a single NIC, so I will assign it to both networks.
- I will enable `promiscuous mode` on one NIC to function as a span port.
- After configuring, start the VM.
- Installing Security Onion is time-consuming and depends on internet speed and server resources.
- During installation, agree to terms by typing `AGREE`.
- Set up an administrator `username` and `password`, then press Enter to continue.
- The installation completes after some time and requires a reboot.
- Post-reboot, configuration begins.
- It's advisable to take a `snapshot` at this stage in case of issues, allowing you to revert.
- Continue with the installation and configuration wizard.
- Choose `Standalone installation` for installation type.
- Opt for `Standard` in the install conditions.
- Select `Automatic` for OS patch schedule.
- Choose DHCP for IPv4 configuration.
- This interface manages Security Onion.
- Enter the Gateway address; in my case, it's my Pfsense IP address.
- For DNS, I will use the standard IP ` 8.8.8.8 ` and ` 8.8.4.4 `
- Specify an IP or network for monitoring traffic.
- Provide an `email address` and `password` for accessing `web interfaces` of all services.
- The installation process begins, which may take some time.
- Once installation is complete, details will be provided.
- Access the web interface from a device on the specified network.
- I'll use my Ubuntu Desktop or Kali, configured as the Security Onion Management Terminal.
- Enter the email and password to access the Security Onion Dashboard.
- After authentication, an overview of Security Onion with its services will be displayed.
- Various services can be accessed from the left-hand menu.
- On the right, click on `Configuration` to configure Security Onion with sensors for monitoring.
- Management device IP address can also be specified.
- All configurations can be done via the command line interface using SSH.
