# Microsoft Sentinel/Azure Project

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


I kept it pretty simple for this project. I created one Windows 10 VM with almost no security that was open to the internet.  That way, I could atract as many bad actors as possible.

*Project Network Topology*

<img width="1030" height="510" alt="Screenshot 2026-01-21 134802" src="https://github.com/user-attachments/assets/17dbbfc2-fab9-43d5-a414-7442ab147897" />

I created a rule in the cloud firewall to allow any traffic and I completely turned off the Windows host firewall.

*Cloud Firewall Rule*

<img width="1918" height="860" alt="Screenshot 2026-01-21 091419" src="https://github.com/user-attachments/assets/d35dc718-cc0d-41fe-892a-440de7bf7e04" />

*Windows VM Firewall*

<img width="1912" height="1042" alt="Screenshot 2026-01-21 095551" src="https://github.com/user-attachments/assets/e1e069ae-afb5-43b8-b554-70d39247764e" />

Next, I forwarded the security event logs from the Windows VM into Azure's log analytics workspace.  After an hour, I checked the logs to see who was trying to log in.

*Queried Logs*

<img width="1908" height="850" alt="Screenshot 2026-01-21 093110" src="https://github.com/user-attachments/assets/7234b9de-c5c6-45d0-8f66-01fa9af11c41" />

Finally, I used some JSON and KQL I found online to place the geographic locations of the attackers to a map using Microsoft Sentinel.

*The Specific KQL Query*

<img width="1914" height="857" alt="Screenshot 2026-01-21 094632" src="https://github.com/user-attachments/assets/725ade82-40dd-410c-a1ee-8c0757cdf675" />

*Microsoft Sentinel Map*

<img width="1489" height="711" alt="Screenshot 2026-01-21 095256" src="https://github.com/user-attachments/assets/55c5908d-31a9-417a-8aad-027f92333489" />

After a few more hours, I came back to see how many more attacks were run against my machine.  I noticed one specific IP was showing up a lot so I used KQL to get the exact number of attempts.  The total ended up being more than 15,000.  This guy (or probably a bot) really wanted access to this machine.

*Total Failed Attempts*

<img width="751" height="514" alt="Screenshot 2026-01-21 131120" src="https://github.com/user-attachments/assets/72a90537-3e38-4c0d-b5fa-e8e60b641286" />




