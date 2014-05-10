# boot2docker-powershell

This is an experimental PowerShell port of the boot2docker management script. This is based on the original boot2docker shell script with some extra features like automatic formating of the virtual hard disk on initialization. USE AT YOUR OWN RISK.

## What it does

This tool downloads the boot2docker ISO image, creates a VirtualBox virtual machine, sets up one network for that virtual machine (one NAT to allow the VM and containers to access the internet), and then provides the user a simple way to login via SSH.

The tool uses putty and plink and downloads them automatically.

The files for the VM, putty, plink and boot2docker ISO can be found in your `$HOME\.dockervm` directory (e.g. C:\Users\<YourName>\.dockervm).

## Installation

Copy directory `Docker` to your `$HOME\Documents\WindowsPowerShell\Modules` directory (e.g. `C:\Users\<YourName>\Documents\WindowsPowershell\Modules`).

You may also need to set the script execution policy to RemoteSigned (see http://technet.microsoft.com/en-us/library/ee176961.aspx). This can be done by running PowerShell as Administrator and executing "Set-ExecutionPolicy RemoteSigned".

## Usage

Following commands are provided (some of them might be renamed later):

  `Connect-Docker` - Connects to VM using putty
  `Format-Docker` - Connects to VM and runs mkfs-script and reboots using plink
  `Get-Docker` - Shows status of VM
  `Install-Docker` - Initializes, formats and starts VM
  `Measure-Docker` - Shows information about VM
  `Restart-Docker` - Restarts VM
  `Start-Docker` - Starts VM
  `Stop-Docker` - Stops VM
  `Suspend-Docker` - Suspends VM
  `Uninstall-Docker` - Destroys VM
  `Update-Docker` - Downloads the latest boot2docker ISO image

The config variables are in the `Docker\Docker.psm1` file. VM ports, disk size and memory size can be configured.
