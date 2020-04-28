# az-deploy-lab
Deploy HA CGF and HA WAF

Re-hydration script. Deploys a fresh install of a lab:
* New resource group
* New storage account
* New VNet with subnets:
  * FW Subnet
  * Web Subnet
  * Green and Blue Subnets (internet access)
  * Red Subnet (no internet access)
* New VMs:
  * 2 X CGF BYOL
  * Windows jump host
  * 2 X WAF BYOL
  * Debian host
* STD ELB + STD PIP in front of HA pair CGFs
* STD ILB w/ HA ports
* STD ILB in front of HA pair WAFs
* RouteTable for each subnet
* NSG for FW subnet

=== WAF BYOL Licensing via script ===
`curl -X POST -H 'Content-Type: application/json' -d '{"token":"XXXXX-XXXXX-XXXXX","domain":"domain.com"}'  http://1.2.3.4:8000`
`curl http://1.2.3.4:8000 | grep hidden`
`curl -X POST -H 'Content-Type: application/json' -d '{"name":"Michael S Collins","company":"Barracuda","email":"mcollins@barracuda.com","eula_hash_value":"ed4480205f84cde3e6bdce0c987348d1d90de9db","action":"save_signed_eula"}'  http://1.2.3.4:8000`
