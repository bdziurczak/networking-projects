My Network Description
+--------------------------------------------+------------+
| Network         | VLAN |  Devices          |Interfaces  |
------------------+------+-------------------+------------+
192.168.10.128/25 |   10 | PC0,PC1,PC2       | All        |
---------------------------------------------+------------+
192.168.10.0/25   |   20 | PC3,PC4,PC5       | All        |
------------------+------+-------------------+------------+
192.168.99.0/26   |   99 | Laptop-PT         | All        |
------------------+------+-------------------+------------+
10.0.0.0/30       | 1000 |Multilayer Switch0,|Gig1/0/1    |
	          |      |Router1            |Gig0/0/0    |
------------------+--------------------------+------------+
203.0.0.0/24      | ---  |Router1            | Gig0/0/1   |
------------------+------+-------------------+------------+
VLANS intended use:
10, 20 - for users
1000 - vlan for link between router and switch
99 - for management. From devices in VLAN 99 ssh into switch by command ssh -l admin 192.168.99.1 (password is cisco123)

FEATURES:

* I use DHCP helper address. This converts DHCP broadcasts to unicasts and forwards them to router.
* I set up rate limiting for DHCP requests
* Inter-VLAN routing is set up on a L3 Switch 
* On Router1 I've set up NAT-PAT that translates addresses of devices that want to connect to Cluster0

CREDENTIALS:
user: admin, password: cisco123

TODO:
* NAT