+++
author = "Nushan Kodikara"
date = 2020-07-08T17:30:00Z
description = "Automate installations and updates on windows 3rd party softwares"
draft = true
tags = ["Windows", "Package Manager", "Introduction", "Review"]
title = "The Package Manager for Windows ( Chocolatey )"

+++
# Introduction

Do you ever thought about a single command to install, uninstall or update softwares in Windows? How about a script automatically do everything for you? Guess what, you're in the perfect place!

Chocolatey is a package manager for Windows, which you can install by a single command and do everything with a single command!

### Showcase

Install softwares

    > choco install vlc

Updated softwares

    > choco upgrade vlc

Uninstall softwares

    > choco uninstall winrar

And explore more in the [docs](https://chocolatey.org/docs "Chocolatey Docs")

## Installation

Step 1

Installation is not much difficulty however, you just need a powershell window with administration Access. Right-click windows icon at bottom right and select powershell with administration Access.

Step 2

Copy the code bellow and paste it in the powershell

    Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))

And press enter, wait and you're ready to go.

## Usage

Always start a powershell window with administration Access. Use the code below to get the help documents

    > choco -?

End