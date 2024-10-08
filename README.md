# This is Git Hub Repo to show My work in Microsoft Sharepoint O365

## Chapter 1 : How to install Sharepoint in Microsoft and Configure it from the begining

In this Chapter I will create the lab to show the How Sharepoint can be deployed in O365


### 1: First install Powershell 7.2.X or 7.4.X
install it through PS or Cmd 

    ```
    winget search Microsoft.PowerShell

    ```

or use this below to install the Msi package from Microsoft Website

"https://github.com/PowerShell/PowerShell/releases/download/v7.4.4/PowerShell-7.4.4-win-x64.msi"   for x64
"https://github.com/PowerShell/PowerShell/releases/download/v7.4.4/PowerShell-7.4.4-win-x86.msi"   for x86

once downloaded install it and check the version which you have installed


### 2: Install the module which you need work with Sharepoint PNP (PnP stands for Patterns & Practices)

    ```
     Install-Module PnP.Powershell -Scope CurrentUser

    ```

You will get warning to install it from PSgallery

```
 Are you sure you want to install the modules from
'PSGallery'?

```
 type "A" and trust installation policy to install that module

 ### 3:Now goto the Microsoft sharepoint 

 which is my URL 
                    alienpro0365.sharepoint.com
 copy the URL for that standard template which you have installed it before
example 
```
 "https://alienpro365.sharepoint.com/sites/Communications"

```

### 4:  To Download your desired sharepoint templates use Git Hub

Unfortunately Microsoft retired from Lookbook, so the templates have to be downloaded from git hub.
here is the github repo link

```
https://github.com/SharePoint/sp-dev-provisioning-templates/

```

Here I'm using commucation template from the below link

```
https://github.com/SharePoint/sp-dev-provisioning-templates/tree/master/tenant/communications

```
download the pnp file extension to your local drive 

communications.pnp (RAW file)

### 5 : To connect with sharepoint using powershell
First you have to connect sharepoint using PNP module using the below command to deploy this template 
    There is two methods to get online normal method would ask for username and password
    else use -interactive parameter to have window to type username and password

```
Connect-PnPOnline https://alienpro365.sharepoint.com/sites/Communications -Interactive 

```

after connectin PnP Online, now we have to deploy previously downloaded PnP (which Team Connection "connections.pnp" RAW file from their github) to the previously deployed 
default "Team" standrad Template. And replace with the current one.


## If you have any doubt about powerhell command follow this pipeline command to get all those commands

```
Get-Command | where name -Like *PnP*

```
Output will be like this

```
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        Disable-PnpDevice                                  1.0.0.0    PnpDevice
Function        Enable-PnpDevice                                   1.0.0.0    PnpDevice
Function        Get-PnpDevice                                      1.0.0.0    PnpDevice
Function        Get-PnpDeviceProperty                              1.0.0.0    PnpDevice

```

If you find error while you deploying another template over the same name. You will find error something like this

![Full layout](./Sharepoint_Site_error_duplicate.png)









