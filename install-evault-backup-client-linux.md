---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Installing the EVault Backup Client in Linux 

Installing the EVault Backup client on a Linux-based operating system can be done through a series of commands in the shell or terminal within the OS. This procedure outlines the steps required to install the EVault Backup client on any of the following Linux-based operating systems:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

After completing the procedure, the automated process will register the Agent service with WebCC, then download and install the files needed to run the service. Follow the steps below to install the EVault Backup client to your Linux-based OS.

1. Run the following command to download the EVault shell script in the terminal.

    `wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh`

2. Execute the following shell script in the terminal:

    `~]# sh ./evault_manual.sh`

    **Note**: The shell script will request the EVault username and password with the following prompts:

    `Enter the WebCC username for this server:`
    
    `Enter the WebCC password for this server:`
3. Enter the **EVault Backup Username** as the input for the prompt requesting the WebCC username. 
4. Enter the **EVault Backup Password** as the input for the prompt requesting the WebCC password. <br/>
   **Note**: Refer to the [Getting Started with Backup Services](/docs/infrastructure/Backup/index.html) article for instructions to view the EVault Backup Username and Password.

