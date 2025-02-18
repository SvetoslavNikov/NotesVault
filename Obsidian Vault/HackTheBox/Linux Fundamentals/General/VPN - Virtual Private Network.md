[[Networking]]
![[Pasted image 20250201131214.png]]

## VPN Client
Encrypts data before sending it

## ISP - Internet Service Provider
Encrypted data can not be accessed by the internet provider. 

## VPN Server
It receives the data and decrypts it and send to the destination

## Example
Hack the Box OpenVPN

HTB gives us a VPN file which we use through our OpenVPN client to connect to OpenVPN server configured by them. 

- The **OpenVPN client** encrypts your traffic and sends it to the **OpenVPN server**. The **OpenVPN server** decrypts the traffic and routes it to the **HTB network** (which is a private network).

- The **HTB network** allows your device (now using the VPN-assigned IP) to access its machines and challenges securely. The **ISP** is only involved in the initial connection to the VPN server; after that, your traffic is isolated and encrypted via the VPN.
