## CPT Lessons Summary
1. Configuring an IP address for an interface on a router and turn on that interface.

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