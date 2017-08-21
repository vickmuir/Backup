---

copyright:
  years: 1994, 2017
lastupdated: "2017-05-01"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Retrieve an R1Soft CDP Username and Password
## Overview

R1Soft Continuous Data Protection (CDP) credentials are found in one of two locations, based on how long the CDP has been active on the device and/or whether or not the CDP credentials were saved manually within the Customer Portal.  The CDP credentials default to the root username and credentials may be stored and tracked within the Customer Portal, however, updates to the CDP password will not sync with the credentials stored in the Portal.  Therefore, any changes to the CDP password must be manually entered within the Customer Portal.  Refer to Add, Delete and Update Software Users and Passwords for more information on updating the CDP password within the Customer Portal.  Follow the steps to retrieve the CDP credentials for a device.


## Retrieve the CDP Username and Password

1. Access the Device List in the [Customer Portal](https://control.softlayer.com/).  Refer to Access the Device List.
2. Determine if the CDP credentials have been manually changed.
   
   **Note**: CDP credentials can only be changed if CDP has been accessed.  If accessing CDP for the first time, the credentials have not been manually changed.
  - If the CDP credentials have been manually changed, then 
     - Click the Device Name to access the device.
     - Select the Passwords tab.
  - If the CDP credentials have **not** been manually changed, then
     - Proceed to Interact with a Device in the Snapshot View procedure and follow the instructions to **view the username and password** for a device.

**Note**:  Use the root username and password to log in to CDP unless the credentials have been manually changed.

## What Happens Next

Use the credentials for R1Soft CDP to log in to CDP on the device. If the credentials retrieved from the [Customer Portal](https://control.softlayer.com/) do not allow for login, it is possible that the password was updated in R1Soft CDP but not recorded using the Password Tracking tool. To reset a lost password, use the KVM functionality for your device to access the CDP server remotely and manually reset the password. For more information on interacting with R1Soft CDP, we recommend using [R1Soft's support wiki](http://wiki.r1soft.com/display/CDP3/Enterprise+Edition).
