# 802.1Q Trunk Configuration

```pkt
! Configure Inter-Switch Interface as Trunk

Switch# configure terminal

Switch(config)# interface gigabitethernet 0/1

Switch(config-if)# switchport mode trunk

! Security Best Practice: Restrict Allowed VLANs

Switch(config-if)# switchport trunk allowed vlan 10,20,30

Switch(config-if)# exit
```
### Note :- 

- Ensure the Native VLAN matches on both ends of the trunk link (Default is VLAN 1).

- ​A mismatch can lead to traffic leakage and CDP error warnings.

- Explicitly defining ```allowed vlan``` limits unnecessary broadcast traffic and improves network security.

---
# Verification & Connectivity Testing

```pkt
Switch# show interface trunk 
```

Shortcut :-

```pkt
Switch# sh int tr
```

### Note :- 

- ```sh int tr``` (Displays trunking operational status & allowed VLANs).

- Ping PC5 (VLAN 30) to PC7 (VLAN 30) Success (Reply Received).

---

