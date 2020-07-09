---
title: "Windows 10 Speedup Registry Tweaks"
date: 2020-07-09T10:12:44+05:30
Description: "Speedup your windows 10 PC with this speedup Trick with Registry"
Tags: ["Windows","Registry","Tweaks"]
Categories: []
DisableComments: false
---
# Introduction
Windows based PCs have a registry system to take control over the system wide operations and most of the times windows default operations are useless to most of us and somewhat annoying. So to be cleared, I made this easy to install Registry file to speed up your PC in matter of seconds.

## What Does It Do?
Well, here comes the boring part. If you don't want to know what this file does to your PC, just skip this section and use the link below to download the program.

* Adds **Copy To** and **Move To** options in files and folders context menu, so that you can easily copy and move them to other locations.
* **AutoEndTasks** - Forces Windows to automatically end user services when the user logs off or shuts down the computer. It'll prevent the "Closing apps and shutting down, This app is preventing shutdown" screen from appearing. Check this topic for detailed info.
* **HungAppTimeout** - Reduces system waiting time before killing user processes when the user clicks on "End Task" button in Task Manager.
* **MenuShowDelay** - Decreases menus show delay time, it'll make the menus show faster upon clicking.
* **WaitToKillAppTimeout** - Reduces system waiting time before killing user processes when the user logs off or shuts down the computer.
* **LowLevelHooksTimeout** - Reduces system waiting time before killing not responding services.
* **MouseHoverTime** - Reduces popup delay time to show popup description faster when you move mouse cursor over an item.
* **NoLowDiskSpaceChecks** - Disables the low disk space check so that you don't get the annoying low disk space notification in system tray.
* **LinkResolveIgnoreLinkInfo** - Prevents Windows from wasting time in searching for a program which no longer exists in your system when you try to open its shortcut.
* **NoResolveSearch** - Prevents Windows from searching for the disk drive to resolve a shortcut.
* **NoResolveTrack** - Prevents Windows from using NTFS file system's tracking feature to resolve a shortcut.
* **NoInternetOpenWith** - Disables "Search on Internet" prompt in "Open with" window so that you can directly see available programs list.
* **WaitToKillServiceTimeout** - Reduces system waiting time before stopping services when the services are notified about shut down process.
* **Change to Photo Viewer** - In Windows 10 It's default to use the photo app and that app is Eating resourcess as hell, so I decided to retrive the defaults
* **Enable Last Active Click** - So You can switch windows with a single click
* **Disable Lockscreen** - Most of us dosent even need the lock screen, and why should we keep it?
* **Disable Cortana** - Cortana is a pain in the head as it dosent even work very well
* **Delete paging on Shutdown** - Windows use this to be an alternative to the ram but we shouldn't keep it after the machine shuts down itself
* **Disable the Startup Delay** - Windows has a startup delay in default to pre-load apps and so on, but it annoys and dosent work on newer PCs
* **Disable Shake To Minimize** - Windows has a feature were you can shake a window to minimize all other windows, which most of the windows users dosent even know about.

## How To Install
**Step 1**
> Download the file from the link below and extract it. If you have trouble extarcting the File, Install [choco](/post/the-package-manager-for-windows-chocolatey/) and Run

>       > choco install winrar -y

> And extract it with winrar

![DownloadFile](/uploads/20200709_105201.png "Downloaded")
Downloaded File
![ExtractHere](/uploads/20200709_105202.png "Extracted")
Extract Here

**Step 2**
> Right-Click on Apply Tweaks File and select merge, give it a yes on the next window and you're pretty much Done with the process

![Rightclick](/uploads/20200709_105203.png "Merged")
Right-Click The File And Select Merge
![SayYes](/uploads/20200709_105204.png "Yes")
Click On Yes
![Done](/uploads/20200709_105205.png "Done")
You're Done!

**Step 3**
> Restart Your PC

## Download
You can download the tweak from [Here 2kb](https://www5.zippyshare.com/v/3zA7eFwV/file.html)

## Troubleshoot
If Something odd happends, or you just need to restore the changes, simply run the Restore Tweaks File and you're Good As new.