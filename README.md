# az-deploy-lab
Deploy HA CGF and HA WAF

Re-hydration script. Deploys a fresh install of a lab:
* New resource group
* New storage account
* New VNet with subnets:
** FW Subnet
** Web Subnet
** Green and Blue Subnets (internet access)
** Red Subnet (no internet access)
* New VMs:
** 2 X CGF BYOL
** Windows jump host
** 2 X WAF BYOL
** Debian host
* STD ELB + STD PIP in front of HA pair CGFs
* STD ILB w/ HA ports
* STD ILB in front of HA pair WAFs
* RouteTable for each subnet
* NSG for FW subnet
