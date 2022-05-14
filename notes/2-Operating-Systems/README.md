# 2 - Operating Systems 

TODO: this description

## IOS Basics

CLI - Command Line Interface

GUI - Graphical User Interface

Cisco IOS - Cisco Internetwork Operating System

### Confic Command Modes

- switch>			- User EXEC mode, very few available commands
- switch#			- Privledged EXEC mode, all available commands
- switch(config)#	- Global config mode, configuration commands that affect the entire system
- switch(config-if)# - Interface config mode, configure a specific interface
- switch(config-line)#		- Line config mode, configure console/SSH/telnet/etc access

- `exit` go down 1 level of configuration
- `end` exit config mode completely
- `enable` user EXEC -> privledged EXEC
- `configure terminal` privledged EXEC -> global config

### IOS Command Structure

Everything before the > or # is the "prompt"
- `MyCoolSwitch(config)#`

First word after the prompt is the command itself
- MyCoolSwitch# `ping`

Commands are followed by either _keywords_ or _arguments_
- MyCoolSwitch# ping `127.0.0.1`
- MyCoolSwitch# show `ip protocols`

Certain syntax shows what parts of commands are required or not:
- boldface:		enter literally
- italics:		supply values
- [x]:			optional element
- {x}:			required element
- [x{y|z}]:		required choice


## Basic Device Configuration

! represents a 'remark' in Cisco IOS, consider
! them to be comments. anything following one
! will not be interpretted by the device

- switch(config)#hostname MyCoolSwitch ! change hostname of the device
- switch(config)#enable secret Passw0rd123 ! change privledged exec mode password
- switch(config)#line vty 0 15 ! change to line config mode for the first 16 virtual connections
- switch(config-line)#password coolnewpassword ! set password required to SSH/telnet into the box
- switch(config-line)#login ! needed to tell the router to _use_ the above password
- switch(config-line)#exit ! return to global config mode
- switch(config)#service password-encryption ! run encryption on weak passwords like the above `password` command
- switch(config)#clock set xxxx ! set device time, useful for when you need to look at historic logs to troubleshoot
- switch(config)#banner motd #bannergoeshere# ! set MOTD banner, shown when logging in to a device

Alternatively, configure logins to use a username/secret-based system. This allows for multiple valid user accounts and is preferrable to the old `password x` command

- switch(config)#username Joe secret Joe2
- switch(config-line)#login local


## Basic Config Management

All configurations are put in the _running_ config file. This is what's currently being run by the switch. It is stored in RAM, thus not persistent and will be reset upon a device reboot.

When a device boots it looks at the _startup_ config file. This is stored in NVRAM, non-volatile storage that persists between reboots.

### Show a config

- switch#show running-config
- switch#show startup-config

### Save a running config

All of the following commands do the exact same thing:

- switch#copy running-config startup-config
- switch#cop ru st
- switch#write memory
- switch#wr

### Wipe a device's config

- switch#erase startup-config ! remove the startup config file
- switch#delete vlan.dat ! not all information is stored in the running config!
- switch#reload ! reboot the device to knock out the running config

