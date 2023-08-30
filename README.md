# 1vpn 
1Password OpenVPN OTP Automation

### Get Started
install `expect`
- mac `brew install expext`
- linux - look up for your package manger... sorry

Populate `auth.txt` with your username and password e.g. 
```
john.smith
Very$ecurePa$$
```
Populate config file with path to ovpn config file and name of your 1password item in your vault
e.g.
```
vpnLocation=~/somewhere/profile.ovpn
onePassItem="OpenVPN Connect"
```

Your `onePassItem` entry for the VPN must have OTP code assigned to it.

### Usage
To connect `./1vpn`