# Introduction

`nodemcu-bootstrap` contains various common precedures for nodemcu apps. Those precedures are

 - initialize WiFi connection
 - setup a network console
 - synchronize time with NTP server
 - provides hardware information on the console

 After everything has been settle down, `nodemcu-bootstrap` will invoke `app.lua` where you put your own application logics.

# Basic Settings

To use `nodemcu-bootstrap`, one have to modify 'settings.lua' according to ones' need.

```
local M = {
   name = ...,
   pin = {led = 0, device_p1 = 6, device_p2 =7},
   wifi = {ssid = 'home', secret='123456789'},
   ntp = {server = '192.168.1.1'},
   telnetd = {port = 23},
}

_G[M.name] = M

return M
```

# Download to NodeMCU

```
make PORT=/dev/ttyUSB0 BAUDRATE=115200
```
