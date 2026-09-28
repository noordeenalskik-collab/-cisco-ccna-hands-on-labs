# 1. Create & Name VLANs

```pkt
Switch> enable  
Switch# configure terminal   
Switch(config)# vlan 10
Switch(config-vlan)# name Sales
Switch(config-vlan)# exit

Switch(config)# vlan 20
Switch(config-vlan)# name Stocks
Switch(config-vlan)# exit
```
### Note :-

- Shortcut of  ```enable``` is :- 
```pkt
Switch> ena
```

- Shortcut of  ```configure terminal```  is :- 
```pkt
Switch# conf t
```

---
# 2. Assign Interfaces to Access VLANs

```pkt

Switch(config)# interface range fa0/1 - 4
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 10
Switch(config-if-range)# exit

Switch(config)# interface range fa0/5 - 8
Switch(config-if-range)# switchport mode access
Switch(config-if-range)# switchport access vlan 20
Switch(config-if-range)# exit

```
### Note :-

- We use ```range``` to configure many ports together .
```pkt
Switch(config)# interface range fa0/5 - 8
```

-  Don't forget to **specify** the end port using the hyphen:   ```-num```

---
# 3. Verification & Testing

```pkt
Switch# show vlan brief
```

Shortcut :- 

```pkt
Switch# sh vlan br
```
### Note :-

- we use it to **check active** VLANs and assigned ports .

- we run it in ==privileged== EXEC mode ( after enable# ) .

- --
