---
nav_order: 3
layout: default
title: OS Cfg
nav_enabled: true
---

`sudo auditd -s enable`  
`sudo systemctl enable auditd.service`  

`sudo nano /etc/audit/rules.d/stig.rules`  
create/copy/paste audit rules.txt
`sudo augenrules --load`
`sudo chmod -R 0640 /etc/audit/rules.d`
`sudo cp /usr/share/doc/libpam-pkcs11/examples/pam_pkcs11.conf.example /etc/pam_pkcs11/pam_pkcs11.conf`

`sudo useradd -D -f 35`
`sudo nano /etc/sysctl.conf`
uncomment net.ipv4.tcp_syncookies = 1 then save file
`sudo nano /etc/login.defs`
Make the following edits  
UMASK 077  
PASS_MIN_DAYS 1  
PASS_MAX_DAYS 60  
`sudo nano /etc/pam.d/login`
Make the following edits  
session required pam_lastlog.so showfailed
+++++Remove any occurrence of "NOPASSWD" or "!authenticate" found in "/etc/sudoers" file or files in the "/etc/sudoers.d" directory.
##sudo rm /etc/sudoers.d/010_pi-nopasswd
##sudo nano /etc/ssh/sshd_config
Make the following edits  
PermitEmptyPasswords no  
PermitUserEnvironment no  
ClientAliveCountMax 1  
ClientAliveInterval 600  
X11UseLocalhost yes  
X11Forwarding no  
PubkeyAuthentication yes  
AuthorizedKeysFile      .ssh/authorized_keys .ssh/authorized_keys2  
`mkdir ~/.ssh`
`sudo nano ~/.ssh/authorized_keys`
copy key into file
`sudo systemctl restart sshd.service`
`sudo aideinit`

##sudo nano /etc/pam.d/login
session required pam_lastlog.so showfailed
##sudo nano /etc/apt/apt.conf.d/50unattended-upgrades
Unattended-Upgrade::Remove-Unused-Dependencies "true";
Unattended-Upgrade::Remove-Unused-Kernel-Packages "true";
##sudo nano /etc/security/limits.conf
* hard maxlogins 10
++##sudo nano /etc/chrony/chrony.conf
makestep 1 -1
##sudo find /var/log -perm /137 ! -name '*[bw]tmp' ! -name '*lastlog' -type f -exec chmod 640 '{}' \;
