---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Evault Port Information

The EVault agent installed on your server needs to be able to communicate with the vault you have purchased. EVault Director host information for an EVault user account can be found in the customer portal. Here are some examples, the host name depends on the Data Center they are in:

    ev-director01.service.softlayer.com TCP/2546
    ev-director201.service.softlayer.com TCP/2546
    ev-director301.service.softlayer.com TCP/2546
    ev-vaultlon0201.service.softlayer.com TCP/2546
    ev-vaulthkg0201.service.softlayer.com TCP/2546

Fedpod Vaults:

    Dallas 8 ev-vaultdal0801.service.usgov.softlayer.com 100.100.6.30
    Ashburn, VA 3 ev-vaultwdc0301.service.usgov.softlayer.com 100.100.38.30

Always register agents to the WebCC and the EVault directors using the FQDN as the IPs for these services could change. Your servers must communicate with the WebCC and all AMP proxy servers for WebCC to work correctly, regardless of the data center location: ev-webcc01.service.softlayer.com TCP 8086,8087. Additional AMP proxy servers may be added as needed to handle additional EVault agents registered to the WebCC. TCP Port 8086, 8087 should have access to 10.0.0.0/8. If you need to use more restrictive firewall rules you may lose access to the WebCC as the infrastructure is expanded. Currently at minimum, your servers should allow access to the 10.0.82.0/24 and 10.2.118.0/24 subnets for TCP ports 8086,8087. Additional subnets may be used in the future as needed.

## Commercial:

WebCC and AMP proxy servers:

    ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087

Commercial AMP proxy servers:

    ev-webamp0901.service.softlayer.com [10.2.118.12] 8087
    ev-webamp0902.service.softlayer.com [10.2.118.13] 8087
    ev-webamp0903.service.softlayer.com [10.2.118.14] 8087
    ev-webamp0904.service.softlayer.com [10.2.118.15] 8087
    ev-webamp0905.service.softlayer.com [10.2.118.16] 8087
    ev-webamp0906.service.softlayer.com [10.2.118.17] 8087
    ev-webamp0907.service.softlayer.com [10.2.118.18] 8087
    ev-webamp0908.service.softlayer.com [10.2.118.19] 8087


## Fedpod:

WebCC and AMP proxy:

    webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

## Commercial ADN:

WebCC and AMP proxy:

    ev-webccadn.adn.networklayer.com [161.26.4.101] 8086, 8087

The agent must allow port TCP/2548 inbound on the private network. This allows CentralControl and WebCC to connect into the agent to manage it. Older versions of EVault used port 808.

The EVault management port (2548) can be changed by updating registry key at:HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber (which is a dword) in Windows OS's.

**Additional Clarification**: The difference between using desktop CentralControl and the Agent in regards to connection settings is often a point of confusion. The server-resident agent will connect to our EVault servers, while the desktop-utilized CentralControl actually connects to your server, using that address and the server's credentials to access it.
 
