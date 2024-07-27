<h1>Wazuh</h1>

<h2>Description</h2>

<b>Wazuh is a free and open-source security platform that unifies XDR and SIEM capabilities. It protects workloads across on-premises, virtualized, containerized, and cloud-based environments. Wazuh helps organizations and individuals to protect their data assets against security threats.</b>
<ul>
  <li><b>Ubuntu Server with Wazuh:</b> This server will have Wazuh installed, acting as the central point for monitoring and management.</li>
  <li><b>Ubuntu Client (Agent):</b> This Ubuntu machine will have the Wazuh agent installed, sending data to the Wazuh server.</li>
  <li><b>Windows 10 Client (Agent):</b> This Windows 10 machine will also have the Wazuh agent installed, sending data to the Wazuh server.</li>

</ul>
Each of the clients (Ubuntu and Windows) communicates with the Wazuh server over the network to provide real-time data on system activities, security events, and other relevant information.
<br />
<h2>Network Diagram</h2>
-----
<h2>Tools and Utilities Used</h2>

- <b>-----</b>

<h2>Environments Used </h2>

- <b>VMware</b>
- <b>Ubuntu</b>
- <b>Windows 10</b>
- <b>PowerShell</b>
- <b>Linux Commands</b>

<h2>Here are the steps to install VMware, Ubuntu, and Wazuh on VMware</h2>

<b>Set Up VMware on Windows</b><br>
<b>Install Ubuntu as a Server on VMware</b><br>
<b>Deploy Wazuh on the Ubuntu Server</b><br>
<b>Install Ubuntu as an Agent on VMware</b>
<p><a href="https://www.youtube.com/watch?v=i68atPbB8uQ&ab_channel=JohnHammond">Refer to this video for installation instructions. </a></p>
<p><a href="https://documentation.wazuh.com/current/quickstart.html">Refer to the official Wazuh website for a quick setup </a></p>  

![image](https://github.com/user-attachments/assets/51a42ff0-c39b-49a6-a0d2-e53ec6fe5622)

Open Ubuntu terminal copy and paste the following commands.
<img width="645" alt="image" src="https://github.com/user-attachments/assets/ef802835-32e2-4ab8-9574-8f46910ef6d3">  
<img width="563" alt="image" src="https://github.com/user-attachments/assets/3ec10330-bdde-4011-a8c1-a508e69ea6db">  
After installation, write down the password.  

Check IP address with the following command and write down IP address on Ubuntu Wazu server:  
![image](https://github.com/user-attachments/assets/3fced076-929d-4e4d-b22f-f92f4efaaa2e)  

Open Firefox browser on Ubuntu Server and enter the IP address:
<img width="708" alt="image" src="https://github.com/user-attachments/assets/7b35ec4e-3232-4638-9b2c-b0d0c917642d">   
The username is 'admin' and the password was already copied during the installation on the terminal.

Add an agent (Ubuntu)  
![image](https://github.com/user-attachments/assets/73dc316e-105e-477b-b7af-89b5785699ee)  

Run the following commands on Ubuntu Agent terminal  
<img width="423" alt="image" src="https://github.com/user-attachments/assets/97bc51da-09bf-4340-8625-7020405b3326">  

Add another agent (Windows)  
<img width="410" alt="image" src="https://github.com/user-attachments/assets/0f7315b8-7803-4b9e-9aa0-8195eafa7e36">  
Open Windows PowerShell Terminal run as administrator and execute the following commands.  
![image](https://github.com/user-attachments/assets/fbadbcdb-c894-4e16-8dc3-760bd909c49f)  

Go and refresh Wazuh on dashboard we will see two agents:
![image](https://github.com/user-attachments/assets/68e243b5-d8ca-41aa-a565-0072997a7943)  

Windows user before event  
<img width="818" alt="image" src="https://github.com/user-attachments/assets/67673a1b-0679-4c7d-9feb-e8ec9fb98694">  


<h1>Events (Case Studies)</h1>  
<b>1.File Integrity</b>
File integrity monitoring
File Integrity Monitoring (FIM) helps in auditing sensitive files and meeting regulatory compliance requirements. Wazuh has an inbuilt FIM module that monitors file system changes to detect the creation, modification, and deletion of files.  

Perform the following steps to configure the Wazuh agent to monitor filesystem changes in the 'downloads' folder.

<h3>Ubuntu</h3>
Edit the Wazuh agent /var/ossec/etc/ossec.conf configuration file.
<directories check_all="yes" report_changes="yes" realtime="yes">/home/user/Downloads</directories>

![image](https://github.com/user-attachments/assets/4fbad7e6-6a40-4e1d-b9a0-7c31e6868484)  

Path: 'downloads' folder.  
![image](https://github.com/user-attachments/assets/b47522c3-8f75-443a-ab30-41964f4f3f95)  

<img width="484" alt="image" src="https://github.com/user-attachments/assets/cbf49e79-62e4-4598-8927-0d22d9a312bb">


<h3>Windows</h3>
Take the following steps to configure the Wazuh agent to monitor filesystem changes in the C:\Users\User\Desktop directory.

Edit the C:\Program Files (x86)\ossec-agent\ossec.conf configuration file on the monitored Windows endpoint. Add the directories for monitoring within the <syscheck> block. For this use case, you configure Wazuh to monitor the C:\Users\Administrator\Desktop directory. 
To get additional information about the user and process that made the changes, enable who-data audit:

<directories check_all="yes" report_changes="yes" realtime="yes">C:\Users\<USER_NAME>\Desktop</directories>  
![image](https://github.com/user-attachments/assets/d120d509-4deb-451d-8755-de86344d910e)  
<img width="492" alt="image" src="https://github.com/user-attachments/assets/d8fb55f0-e885-41e6-9ff7-c755e35784f1">  






































