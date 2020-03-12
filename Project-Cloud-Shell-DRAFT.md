# Project Audition by David Cobb

## Summary

I propose a series of projects using Azure Cloud Shell, where the student builds and tests their cloud infrastructure from the Azure Cloud Shell and Visual Studio Code.

Skills and to include:
* PowerShell 7
  * [AZ Module](https://docs.microsoft.com/en-us/powershell/azure/new-azureps-module-az?view=azps-3.5.0)
  * [Pester Module](https://github.com/pester/Pester)
* [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/get-started-with-azure-cli?view=azure-cli-latest)
* git
* ARM Templates
* Azure Policy
* .NET Core, `dotnet new`, etc.

Each project focuses on a set of cloud infrastructure functionality. The starting point of each project is either from scratch, or the deployment of an ARM Template shared on github.

Here is an outline, to be discussed, of how the first few projects and their tasks might look from a high level.

* Cloud Shell Setup
  * [Initial Login and cloud drive setup](./lab-1-cloud-shell-login.md)
  * Use Code Editor to edit projectSettings.ps1
    * Explore clouddrive
    * Create working folder
    * Edit projectSettings.ps1
    * (Create and mount additional drive from Azure)
* Using git from Cloud Shell
  * Clone project repo to local folder
  * Review ARM Template
  * Deploy ARM Template
  * VERIFY: Download and run pester test?
* Create VNet
  * Examine syntax
  * Explore VNet options
  * Create VNet
  * Create Subnet
  * Configure
  * Save script
  * Export template
  * ( Recreate VNet from template)
  * VERIFY: Download and run pester test?
* Create VM
  * Examine syntax
  * Explore VM options
  * Create VM
  * VERIFY: Download and run pester test?
* Create Network Security Group (NSG)
  * Examine syntax
  * Create NSG
  * Apply NSG to Subnet & VM
  * VERIFY: Test access to VM
  * VERIFY: Download and run pester test?
* Explore Azure:\ SHiPS provider
....

Future project outline may look like:

* Troubleshooting network security groups
  * Deploy problem ARM template that provisions VNnet, subnets, VMs, NSG
  * Deploy & run pester tests that fail due to blocked port(s) or exposed services
  * Investigate logs, network watcher, etc
  * Investigate NSG
  * Modify NSG
  * Test manually, then re-run pester tests
