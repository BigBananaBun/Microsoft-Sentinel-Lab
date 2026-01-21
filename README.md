# Microsoft Sentinel/Azure Home Lab

## Objective

When I worked as a Data Center Tech and deployed servers for clients, I noticed that right after I would install the OS and get the netork working, there were always several failed login attempts from attackers trying to brute force their way into the server.  With this project, I wanted to create a Honey Pot using Azzure and forward the Windows security event logs to a log analytics workspace with Sentinel.

### Skills Learned

- Deploying VM's in Microsoft Azure.
- Forwarding Logs to the Microsoft Sentinel SIEM.
- Creating and modifying firewall rules.
- Using KQL to query specific log entries.

### Tools Used

- Microsoft Azure
- Microsoft Sentinel
- Windows Defender Firewall

## Steps


I kept it pretty simple for this project. I created one Windows 10 VM with almost no security that was open to the internet.  That way, I could atract as many people as possible.

*Project Network Topology*

<img width="1030" height="510" alt="Screenshot 2026-01-21 134802" src="https://github.com/user-attachments/assets/17dbbfc2-fab9-43d5-a414-7442ab147897" />

