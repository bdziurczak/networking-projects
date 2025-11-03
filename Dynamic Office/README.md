DHCP server on Cisco 4331. There's two VLANs (10/20), respectively for networks 192.168.10.128/25 and 192.168.10.0/25.
There's also VLAN 1000(10.0.0.0/30) for link between switch and router

VLANS:
10, 20 - for users
1000 - vlan for link between router and switch
99 - for management. From devices in VLAN 99 ssh into switch by command ssh -l admin 192.168.99.1 (password is cisco123)

FEATURES:

* DHCP don't break because I use DHCP helper address. This converts DHCP broadcasts to unicasts and forwards them to router.
* I set up rate limiting for DHCP requests

CREDENTIALS:
user: admin, password: cisco123



---

\[Users VLANs] → \[L3 Switch - Routing] → (10.0.0.2/)\[Router - Gateway to Internet]

↓               ↓                       ↓

Local traffic   Inter-VLAN routing      External traffic

---

TODO:

* DMZ
* Internet connection

TODO Next:
Add a second internal l3 switch and use PAT (Port Address Translation).
Try blocking outbound traffic with ACLs.

