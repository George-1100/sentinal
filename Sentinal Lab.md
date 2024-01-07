# Azure Sentinel MAP with LIVE CYBER ATTACKS
# Description
The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.

The script is used in this demo where I setup Azure Sentinel (SIEM) and connect it to a live virtual machine acting as a honey pot. We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to look up the attackers Geolocation information and plot it on an Azure Sentinel Map

# Steps to procedure

1. sign in to Azure portal.com
2. Create resource group
   
   ![sc soc 1](https://github.com/George-1100/sentinal/assets/76154087/c2bda0a1-2703-4716-8c73-c4c26c83d982)

3. Create virtual mission with No firewall rules which is allow to open all ports and allow all traffic into the virtual machine.

   ![sc soc 2](https://github.com/George-1100/sentinal/assets/76154087/cd448c52-feda-43af-91c0-88762bc7a1f7)
  
4. Disable Microsoft defender Plan

   ![scsoc 3](https://github.com/George-1100/sentinal/assets/76154087/5fa023d6-1fb1-4fa7-a0c3-1870ae0c471e)

5. Create Log analatics workspace for analyze windows event logs
   
   ![SC soc 5](https://github.com/George-1100/sentinal/assets/76154087/565aa542-01fc-4cb9-a0fd-0d0d3dbba50b)
   
7. Create data collection rule to select all windows logs
8. Conect  Virual machine to log anlaytics for get logs from VM
9. login to Vitual machine
10. open powershell ISE and paste the Script for taking logs with geo location using ip geolocation API
    
    ![sc fo honey pot](https://github.com/George-1100/sentinal/assets/76154087/9a3abcbe-15c6-4ea9-90c9-6d9a7a41b956)
    
12. Copy and pase api key from ip golocation io website

![SC soc 5](https://github.com/George-1100/sentinal/assets/76154087/e42fa69f-b221-484d-a17c-6b2e941c1b2d)

13. Run the Script 
14. Logs stored in c:\programData\faild_rdp_log
    
    ![faild rdp](https://github.com/George-1100/sentinal/assets/76154087/404def22-b9e8-4f32-af0c-7cbe6c4b5fde)

15. Create custom log in log analytics worikspace(Log analytics workspace > tables > create custom log) and give windows log location c:\programData\faild_rdp_log
16. Setup azure sentinal
17. Create new workbook and add a new query
    
    ![SC soc 6](https://github.com/George-1100/sentinal/assets/76154087/9b14d5c1-351d-4ec2-942c-59eb81083fb9)

19. Enter the query for Visualize the ip address with respective geo location based on the Security logs
    
    ![sc soc 7](https://github.com/George-1100/sentinal/assets/76154087/a432ddab-a74b-4fa2-8115-0a0b13eec3b1)

20. Select map visualization and its settings
    
    ![geo location map](https://github.com/George-1100/sentinal/assets/76154087/dbf019ff-32c9-413a-aa72-314adde0b18d)

    

 

   

   
   
       
      



