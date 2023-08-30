# 1vpn 
1Password OpenVPN OTP Automation

### Get Started
Install `expect`
- mac `brew install expext`
- linux - look up for your package manger... sorry

Install OpenVPN

Install 1Password client <br>
https://support.1password.com/get-the-apps/

Enable 1Password CLI access <br> https://developer.1password.com/docs/cli/get-started/ <br>

Pull this repo

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