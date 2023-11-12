# Setting up VPN 

We are using a VPN to ensure every member of the team has private, secure access to shared hardware, regardless of where you are in the world. While a conventional VPN service reroutes all outbound traffic we are only rerouting traffics that goes to other nodes in the VPN. The typical use case is to enable network access to our drones without exposing them to the entire internet. Beyond that, by enabling secure, direct network communication between member of our teaem, there are many more possibilities.

To power this, we are using the frontend of [Tailscale](http://tailscale.com), a freemium, open-source VPN software. To save cost, we are hosting our own backend [Headscale](https://headscale.net) server, running on a small Google Cloud VM. 

You are welcomed to use this VPN service for your personal use. However, please be mindful that everyone shares the same network bandwidth, so do not overload it.

## Login

Each of you should have receieved an `auth-key` for the server. If you have not received one, please check your spam folder then contact Linus.
You can use your `auth-key` to register multiple machines with the server. 

Your user name is your CRSid. Each machine you add will be assigned the domain `<machine_hostname>.<username>.vpn.wise-angel.com`. Once Tailscale is running on your system, you can use this domain to access ports on your machine.

## Quick Install

### Linux
1. [Download and install Tailscale](https://tailscale.com/download/linux), stop before running `sudo tailscale up`
2. Instead run the following:
```
tailscale up --login-server https://vpn.wise-angel.com:8080 --auth-key <YOUR-AUTH-KEY>
```
3. A browser window should appear informing you that you have successfully signed in.
4. Try restarting tailscale and see if your login persists.


### Windows
1. [Download and install Tailscale](https://tailscale.com/download/windows)
2. Close and exit Tailscale
3. on CMD or Powershell, run the following command:
```bash
tailscale login --login-server https://vpn.wise-angel.com:8080 --auth-key <YOUR-AUTH-KEY>
```
4. A browser window should appear informing you that you have successfully signed in.
5. Try restarting tailscale and see if your login persists.


### Mac
1. [Download Tailscale from the App Store](https://apps.apple.com/ca/app/tailscale/id1475387142?mt=12)
2. Open terminal and run the following:
```
tailscale login --login-server https://vpn.wise-angel.com:8080 --auth-key <YOUR-AUTH-KEY>
```

## Advanced Guide
If you encountered any problems with the steps above, please refer to these guides:
- [Windows](https://vpn.wise-angel.com:8080/windows)
- [Apple](https://vpn.wise-angel.com:8080/apple)

 If you still cannot resolve the problem, contact Linus.

 ## First Test
 To test that your set-up is working, please try pinging the Mark 2 drone hardware:

 ```
 ping drone.mk2
 ```



## Security
By default, only traffic to and from shared hardware (like the drone) is allowed. This way, you don't have to worry about your network ports being exposed.

You may want to enable traffic between your own machines. I personally use this to SSH into my room computer when I am out. If you want this enabled, please ask Linus to add you to group `tag:meta`. (I may enable this by default, once everyone has joined the server)

You may also want to expose certain ports on your machine. This could be useful if you self-host services for the rest of the group. You can be added to group `tag:hosting`, which exposes port `7730` to `7739` by default. You can also specify which exact port you want to expose.


