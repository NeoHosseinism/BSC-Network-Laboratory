# CPT Lessons Summary
## 1. Configuring an IP address for an interface on a router and turn on that interface.

> **Long way**
```
Router> enable
Router# configure terminal
Router(config)# interface FastEthernet 0/0
Router(config-if)# ip address 192.168.10.1 255.255.255.0
Router(config-if)# no shutdown
```

> **Short way**
```
Router> en
Router# conf t
Router(config)# in f 0/0
Router(config-if)# ip ad 192.168.10.1 255.255.255.0
Router(config-if)# n sh
```
## 2. Configure password for `enable` mode And `telnet`

### 2-1 `enable` mode
> **Long way**
```
Router> enable
Router# configure terminal
Router(config)# enable password 1234
Router# exit
Router# show running-config
Router# configure terminal
Router(config)# no enable password
Router(config)# enable secret 5678
Router# show running-config
```
> **Short way**
```
Router> en
Router# conf t
Router(config)# ena p 1234
Router# ex
Router# sh r
Router# conf t
Router(config)# no ena p
Router(config)# ena s 5678
Router# sh r
```

### 2-2 `Telnet`
#### 2-2-1 Set password for `Telnet` in Router
> **Long way**
```
Router> enable
Router# configure terminal
Router(config)# line vty 0 4
Router(config-line)# password 9090
```
> **Short way**
```
Router> en
Router# conf t
Router(config)# li vty 0 4
Router(config-line)# pas 9090
```
#### 2-2-2 Connect with `Telnet` from PC to Router
> **Long way**
```
PC> telnet 192.168.10.1
Password: 9090
Router> enable
Password: 5678
Router> exit
```
> **Short way**
```
PC> telnet 192.168.10.1
Password: 9090
Router> en
Password: 5678
Router> ex
```
## 3. Static Routing
3-1 Set Hostname for Router
> **Long way**
```
Router> enable
Router# configure terminal
Router# hostname 1
R1(config)#
```
> **Short way**
```
Router> en
Router# conf t
Router(config)# h 1
R1(config)#
```
### 3-2 Create Connection between 2 Routers
> **Long way**
```
Router# configure terminal
Router(config)# hostname 1
R1(config)# interface serial 0/0/0
R1(config-if)# ip address 192.168.x.x 255.255.255.0
R1(config-if)# no shutdown
```
> **Short way**
```
Router> en
Router# conf t
Router(config)# h 1
R1(config)# in s 0/0/0
R1(config-if)# ip ad 192.168.x.x 255.255.255.0
R1(config-if)# n sh
```
### 3-3 Set IP route for Router
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# ip route + destination Net-ID + destination SubnetMask + next Hop
R1# show ip route
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ip route + destination Net-ID + destination SubnetMask + next Hop
R1# sh ip route
```
## 4. Default Routing
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# ip route 0.0.0.0 0.0.0.0 + next Hop
R1# show ip route
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ip route 0.0.0.0 0.0.0.0 + next Hop
R1# sh ip route
```
## 5. RIP
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# router rip
R1(config-router)# network {all known Net IDs} 
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ro r
R1(config-router)# ne {all known Net IDs}
```
## 6. EIGRP
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# router eigrp {as}
R1(config-router)# network {all known Net IDs} {subnet masks}
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ro e {as}
R1(config-router)# ne {all known Net IDs} {subnet masks}
```

## 7. OSPF
### 7-1 Redistribution between protocols
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# router {protocol}
R1(config-router)# redistribute {protocol}
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ro {protocol}
R1(config-router)# r {protocol}
```

### 7-2 OSPF
> **Long way**
```
R1> enable
R1# configure terminal
R1(config)# router ospf {as}
R1(config-router)# network {all known Net IDs} {wildcard masks} area {area}
```
> **Short way**
```
R1> en
R1# conf t
R1(config)# ro o {as}
R1(config-router)# ne {all known Net IDs} {wildcard masks} area {area}
```
