# Cisco `Router` Commands
## Basic Commands
1. `Router> ?`: Help
2. `Router> enable`: Equivalent to `sudo` in Ubuntu
3. `Router# ?`: Help for Admin (If you see `--More--`, press `Enter` to add one line at a time and press `Space` to add one page at a time)
4. `Router# exit`: Exit from current EXEC (back to previous step, like `cd..` in cmd). Use `Ctrl` + `Z` to force exit from any mode to `Router#`.
5. `Tab`: Auto-complete command from a unique segment. For example, typing `en` and pressing `Tab` will complete the command to `enable`. You can also type a unique segment and then press `Enter`.
6. To see a list of full commands in the current EXEC mode, use the `?` command. To see possible continuation commands after the current typed command, use the following format: `Router(config)# interface ?` (note the space between the current command and `?`).
7. `<cr>`: "Carriage Return" means the command is completed.


## Set Static IP
1. `Router# configure terminal` or `conf t`: Go to `Router(config)#` to configure the router.
2. `Router(config)# interface FastEthernet x/x`: (`x/x` is the name of the interface, like `0/0`). Go to `Router(config-if)#`.
3. `Router(config-if)# ip address 192.168.10.1 255.255.255.0`: Set the IP address.
4. `Router(config-if)# no shutdown`: Turn on the interface.

## Set password and secret for `enable` mode of Router
1. `Router# show running-config`: Show the current configuration.
* `Router# show ip interface brief`: Show the IP address of all interfaces.
2. `Router(config)# enable password 1234`: Set the password for `enable` mode.
3. `Router(config)# enable secret 5678`: Set the password for `enable` mode (encrypted).
* When both `enable password` and `enable secret` are set, the `enable secret` will be used.
1. `Router(config)# no enable password`: For delete password use `no` before the command.
2. `Router(config)# no enable secret`: For secret password use `no` before the command.

## Telnet
1. `Router(config)# line vty 0 4`: Go to `Router(config-line)#`.
2. `Router(config-line)# password 9090`: Set the password for `telnet`.
3. `PC> telnet 192.168.10.1`: Connect to the router from PC (`192.168.10.1` is default gateway for PC).
4. `Router> exit`: Exit from `Router>` to `PC>`.

## Create Connection between 2 Routers
1. `Router(config)# hostname 1`: Set the name of the router to `R1`.
2. `Router(config)# interface Serial 0/0/0`: Go to `Router(config-if)#`.
3. `Router(config-if)# ip address 192.168.x.x 255.255.255.0`: Set the IP address for the interface.
4. `Router(config-if)# no shutdown`: Turn on the interface.
5. Do 1 to 4 Setps in another `Router`.
   
## Static Routing
1. `R1(config)# ip route + destination Net-ID + destination SubnetMask + next Hop`: For set IP Routing for unknown destinations
2. `R1# show ip route`: For check the routing table in the router.
3. `R1(config)# no ip route + destination Net-ID + destination SubnetMask + next Hop`: For **DELTE** IP Routing for unknown destinations

## Default Routing
`R2(config)# ip route 0.0.0.0 0.0.0.0 + next Hop`: For set IP Routing for forward all requests to 1 next hop.

## RIP
1. `R1(config)# router rip`: For select the protocol RIP.
2. `R1(config-router)# network {Net ID}`: For set all known Net IDs for each router.

## EIGRP
1. `R1(config)# router eigrp 100`: For select `EIGRP` protocol with `as = 100`.
2. `R1(config-router)# network 192.168.10.0 0.0.0.3`

## Redistribution between Protocols
`R1(config-router)# redisribute ${protocol}`: For set redistribution for another protocol.

## OSPF
1. `R1(config)# router ospf 100`: For select `OSPF` protocol with `as = 100`.
2. `R1(config-router)# network ${net-id} ${wildcard-mask} area ${area-id}`: For set known Net ID for each Router's interface.