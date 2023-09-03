# 1vpn 
1Password OpenVPN 2FA OTP Automation

### Get Started
**Install** `expect`
- mac - `brew install expext`
- linux - look up for your package manger... sorry

**Install OpenVPN** - 2.4 prefered, not tested on others.

**Install 1Password client** <br>
You must have a valid item entry in your vault that has OTP for the VPN you want to connect to <br>
https://support.1password.com/get-the-apps/

**Enable 1Password CLI access** <br> https://developer.1password.com/docs/cli/get-started/ <br>

**Create auth file** <br>
Used for the `-a` option <br>
From [OpenVPN Docs](https://openvpn.net/community-resources/reference-manual-for-openvpn-2-4/)
```
--auth-user-pass [up]
Authenticate with server using username/password. up is a file containing username/password on 2 lines. If the password line is missing, OpenVPN will prompt for one.If up is omitted, username/password will be prompted from the console.
The server configuration must specify an --auth-user-pass-verify script to verify the username/password provided by the client.
```
e.g.
```
john.smith
P@$$W0RD123
```

### Usage
`-c` ovpn config path<br>
`-a` auth (username password) file path to ovpn <br>
`-i` Item name onepassword <br>
`-k` kill 

To connect - `1vpn -a ~/some-path/auth.txt -i "OpenVPN Connect" -c ~/some-path/profile.ovpn` <br>
To disconnect - `1vpn -k`

### How it works
In the `getotp` script 1passowrd cli grabs the OTP assigned to your vault item entry given in the `-i` command. <br>
Then in the `automate` script expect is used to connect to OVPN via cli and will interact with your console on "CHALLENGE: Enter 2FA Authentication" pattern match and enter the OTP generated.