# Initial setup of Debian 10 server


## Description

Initial setup of Debian 10 server.

**First role (sudo_user)**

* System update
* Check if reboot is required
* Create sudo admin, add ssh public key and set no password

**Second role (bootstrap)**

* Set timezone
* Install, setup chrony utility and synchronize time and date against remote ntp server


## Tested on

Debian 10 server (ver. 10)


## Requisites

a) Cloud Platform account<br />
b) A VPS server with Debian 10 already installed<br />
c) An SSH key pair<br />



## Instructions

a) On your laptop create a working directory


b) In your working directory open a console window


c) Clone github repository

```
git clone https://github.com/jobetinfosec/ansible-debian10-bootstrap.git
```


d) Switch to first role directory

```
cd ansible-debian10-bootstrap/sudo_user
```


e) Open the hosts file

```
nano hosts
```

f) Replace <TEMPORARY_ITEMS> with your own data:

`<SERVER_IP>`		replace <SERVER_IP> with the actual IP address of your remote server<br />
`<PRIVATE_KEY_NAME>`	replace it with your private key's name<br />

then save and close the file


g) Check if you are able to ping remote server

```
ansible -m ping all
```

You should receive a SUCCESS message


h) Check if any error shows up

```
ansible-playbook sudo_user.yml --check
```


g) Launch installation

```
ansible-playbook sudo_user.yml
```


## Licence

MIT licence
