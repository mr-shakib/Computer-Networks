OSPF commands :

For router 1:

enable
configure terminal
router ospf 1
network 192.168.1.0 0.0.0.255 area 0
network 192.168.3.0 0.0.0.255 area 0

For router 2: 

enable
configure terminal
router ospf 1
network 192.168.2.0 0.0.0.255 area 0
network 192.168.3.0 0.0.0.255 area 0



NAT:
Router 1:
ip nat inside source static 10.10.10.2 50.50.50.2
int f0/0
ip nat inside
int s2/0
ip nat outside

Router 2:
ip nat inside source static 20.20.20.2 60.60.60.2
int f0/0
ip nat inside
int s2/0
ip nat outside

then static connection


VLAN:

vlan 2
name office
exit
vlan 3
name home
exit

interface fastEthernet 0/1
switchport access vlan 2
exit
interface fastEthernet 0/2
switchport access vlan 2
exit
interface fastEthernet 0/3
switchport access vlan 3
exit
interface fastEthernet 0/4
switchport access vlan 3
exit
