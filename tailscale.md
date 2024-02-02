# VPN Guide

## Motivation
Our primary goal is to provide stable and secure access to shared hardware (RPIs, Servers, Flight controllers etc) regardless of where our members are in the world. In addition, we hope to unlock new opportunities by allowing private, secure communication between team members.

### Notes
1. This is *NOT* a VPN service: the VPN will only reroute traffic directed to other nodes in the private network; your normal traffic is still directed to the internet.
2. You are welcomed to use this VPN service for personal use, but note that server bandwidth is limited and shared between members.
3. By agreeing to use the network, you accept full responsibility for your own network activities.


## Security
By default, you can only access shared machines and your own machines. Your machines are only acccessible by yourself.

You may also want to forward certain ports on your machine. This could be useful if you self-host services for the rest of the group. Please contact the server admin.

## Login

Access to the server requires an non-expired `auth-key`. You can register multiple machines with the server with one `auth-key`.

Your user name is your CRSid. Each machine you add will be assigned the domain `<machine>.<user>.headscale.wise-angel.com`. Once Tailscale is running on your system, you can use this domain to access ports on your machine.

## Quick Install

### Linux
1. Follow the manual install instruction on the [Tailscale website](https://tailscale.com/download/linux), stop before running `sudo tailscale up`
2. Instead run the following:
```
tailscale up --login-server https://vpn.wise-angel.com --auth-key <YOUR-AUTH-KEY>
```
3. A browser window should appear informing you that you have successfully signed in.
4. Try restarting tailscale and see if your login persists.


### Windows
1. [Download and install Tailscale](https://tailscale.com/download/windows)
2. on CMD or Powershell, run the following command:
```bash
tailscale login --login-server https://vpn.wise-angel.com --auth-key <YOUR-AUTH-KEY>
```
3. If you have previous logged into Tailscale, try adding the following argument to the previous command: `--force-reauth --reset`
4. A browser window should appear informing you that you have successfully signed in.
5. Try restarting tailscale and see if your login persists.


### Mac
1. [Download Tailscale from the App Store](https://apps.apple.com/ca/app/tailscale/id1475387142?mt=12)
2. Open terminal and run the following:
```
/Applications/Tailscale.app/Contents/MacOS/Tailscale login --login-server https://vpn.wise-angel.com --auth-key <YOUR-AUTH-KEY>
```
3. If you have previous logged into Tailscale, try adding the following argument to the previous command: `--force-reauth --reset`

4. A browser window should appear informing you that you have successfully signed in.
5. Try restarting tailscale and see if your login persists.

## Advanced Guide
If you encountered any problems with the steps above, please refer to these guides:
- [Windows](https://vpn.wise-angel.com/windows)
- [Apple](https://vpn.wise-angel.com/apple)

 If you still cannot resolve the problem, contact the sserver admin.
