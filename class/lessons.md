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

### 2.1 `enable` mode
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

### 2.2 `Telnet`
#### 2.2.1 Set password for `Telnet` in Router
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
#### 2.2.2 Connect with `Telnet` from PC to Router
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