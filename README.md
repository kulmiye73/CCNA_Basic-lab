# CCNA_Basic-lab
configuration router and switch

##Network Topology for one Router one Switch and two Work stations.##
##Switch configuration##

enable
configure terminal
## Turnoff Domain name##
no ip domain-lookup
## set Hostname SW1 ##
hostname SW1
## Create password encrypted##

enable secret cisco
## create line console password#
line console 0
logging synchronous
login
password switch
exec-timeout 0 0
exit
## create line aux password##
line aux 0
login
password cisco
exit
Create Line vty and password##
line vty 0 15
login
password cisco
exit
## Sets ip address and netmask for Switch##
interface vlan 1
ip address 192.168.1.2 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.1.1
## set description for interface fa0/4##
interface fa0/1
description Link to Seattle Router
interface fa0/4
description Link to Workstation A
## set switchport security##
switchport port-security 
switchport port-security maximum 1
switchport port-security violation shutdown
 

## set description interface fa0/8##

interface fa0/8
description Link to Workstation B
## set port-security##

switchport  port-security mac-address 1234.5678.90ab

switchport port-security 
switchport port-security maximum 1
switchport port-security violation shutdown
exit
exit
## save file to config-running##
copy run start















 

