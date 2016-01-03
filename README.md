# Vagrant CTF Box
This project has been forked and it was a great idea watched in the [liveoverflow's youtube channel](https://www.youtube.com/watch?v=wLsckMfScOg) meanwhile he was solving the readme challenge. This Vagrant Enviroment 
would be helpful during the ctf and wargames competitions/challenges for the PereiraSecurityTeam. We'll use the options shared by @thebarbershopper, In addition to that some tools from categories not covered in the original repo has been added, please see below.

### Requirements 
* [VirtualBox](https://www.virtualbox.org)
* [Vagrant](https://www.vagrantup.com/)

## Categories Included:
* Reversing : Is done by @barbershopper
* Networking 
* Scripting
* Forensics
* Cryptography 
* Websec (Pending)

## Reversing
* [Binjitsu](https://github.com/binjitsu/binjitsu)
* [Pwndbg](https://github.com/zachriggle/pwndbg)
* [Radare2](https://github.com/radare/radare2)
* [Firmware tools (fmk / qemu)](http://reverseengineering.stackexchange.com/questions/8829/cross-debugging-for-mips-elf-with-qemu-toolchain)
* [Angr](https://github.com/angr/angr)

## Check correct installation of Reversing Tools:
### Pwndbg
Run the following command in the VM:
```
gdb /bin/ls
```
Expected output:
```
Loaded 53 commands.  Type pwndbg for a list.
Reading symbols from host-share/crackme...(no debugging symbols found)...done.
Only available when running
pwn>
```

### Radare
Run the following command in the VM:
```
r2 /bin/ls
```

Expected output:
```
[0x00404890]> aaa
```

### Binjitsu

Run the following command in the VM:
```
python
>>> from pwn import *
>>> elf = ELF('/bin/ls')
[*] '/bin/ls'
    Arch:     amd64-64-little
    RELRO:    Partial RELRO
    Stack:    Canary found
    NX:       NX enabled
    PIE:      No PIE
    FORTIFY:  Enabled
>>> rop = ROP(elf)
[*] Loading gadgets for '/bin/ls'
```

### Angr

Run the following commands in the VM:
```
source ~/angr/bin/activate
python
>>> import angr
>>>
```

## Networking 
* tshark,wireshark
* pixiewps
* nc	
* tcpdump
* openssl
* tcpdump
* openvpn

## Scripting
* python 
* ruby 
* bash 


## Forensics
* pngcheck 
* steghide
* dd
* foremost 
* scalpel


## Cryptography
* John the Ripper 
* hashdump 
* sage python modules(not yet!)
* gpg


## Websec
* Pending.

##ToDo
We need to choose properly the tools needed for the ctfs, and if its convenient install all this software in a single vm or in multiple vms.


### Shared folder
Drop files in the `host-share` folder on your host to find them on your VM at `/home/vagrant/host-share`
