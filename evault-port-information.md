---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-22"

---
{:new_window: target="_blank"}

# EVault Port Information

The EVault agent that is installed on your server needs to be able to communicate with the vault that you purchased. EVault Director host information for an EVault user account can be found in the [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. Always register agents to the WebCC and the EVault directors by using the FQDN because the IP addresses for these services might change. 

Your servers must communicate with the WebCC and all AMP proxy servers for WebCC to work correctly, regardless of the data center location.

```
evregister.service.softlayer.com TCP 8086,8087
```

Extra AMP proxy servers can be added as needed to handle more EVault agents that are registered to the WebCC. 

TCP Port 8086, 8087 must have access to 10.0.0.0/8. 

If you need to use more restrictive firewall rules, you might lose access to the WebCC as the infrastructure is expanded. Currently, at minimum, your servers must allow access to the 10.0.82.0/24 and 10.2.118.0/24 subnets for TCP ports 8086, 8087. Other subnets might be used in the future as needed.

## Commercial:

### WebCC and AMP proxy servers:

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

### Commercial AMP proxy servers:

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federal:

### WebCC and AMP proxy:

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
The agent must allow the port TCP/2548 inbound on the private network. This setting allows CentralControl and WebCC to connect into the agent to manage it. Older versions of EVault used port 808.

The EVault management port (2548) can be changed by updating the registry key at: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (which is a `dword`) in Windows operating systems.

**Clarification**: When it comes to connection settings, the difference between desktop CentralControl and the Agent is often a point of confusion. The server-resident Agent connects to our EVault servers, while the desktop-utilized CentralControl actually connects to your server, by using its address and the server's credentials to access it.
