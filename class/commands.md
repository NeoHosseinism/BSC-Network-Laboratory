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

show: با استفاده از این دستور، می‌توانید اطلاعات مختلفی از دستگاه خود مانند تنظیمات فعلی، جداول مسیریابی و... را مشاهده کنید.

ping: با استفاده از این دستور، می‌توانید از میزان دسترسی به یک دستگاه دیگر در شبکه مطمئن شوید.

traceroute: با استفاده از این دستور، می‌توانید مسیریابی بسته‌های داده را از دستگاه فعلی تا مقصد مورد نظر پیگیری کنید.

shutdown: با استفاده از این دستور، می‌توانید یک رابط شبکه را غیرفعال کنید.

copy: با استفاده از این دستور، می‌توانید فایل‌ها و تنظیمات را بین دستگاه و سایر دستگاه‌ها یا سرورها کپی کنید.