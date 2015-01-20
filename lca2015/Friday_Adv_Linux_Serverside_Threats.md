@obilodeau ESET

serverside malware is a thing

Windigo

Devop malware operators

adv.edu.vn

crimeware

server good to pop - good hardware, network, trusted IP

spanhaus XBL (spam block)
 - google safe browsing
 - AV blacklists

.htaccess redirect
 - redir fro mgoogle, wiki
 - testing via raw URL = not detected

--> darkleech - $1000 blackmarket - Malware as a Service
 - aka apmod chapro

Phalanx 1/2
 - kernal root kit
 - unstable to kernel changes/updates

Operation Windigo
 - ebury, cdorked, calfbot
 - run on compromised servers

 > certbund, cern, eset, snic
 - ongoing law enforcement case

- ebury - OpenSSH backdoor
 - replace libkeyutils.so 
 - encrypt/unencrypt keys stolen to/from server
 - was replacing ssh/d/-add
 - adding 23k LOC on .so (libns2.so)

assembly hooks - replacement constructor code

password sent via DNS and shared memory - Xcat command - future fetch

mitigation - permiscuous mode on DNS

ssh backdoor - key identifier

xver, xcat, xbnd, xpsw - extended command for backdoor intercepton
 - w/out command - root shell

cdorked - httpd nginx backdoor
 - malware patched to cross support, redirect to affilicate ads
 - static XOR key - binary replacement

targets = porn sites 
 - host is not redirected on: jp, ru user agents, admin uri, repeat visitor
  -> hard to reproduce findings if limitations in place

correlated via IP, encryption functionality between ebury and cdorked

7000+ witnessed infections 

domain generation algorithm (DGA)

via credentials, probably not exploits

perl/calfbot
 - self deleting (memory only)
 - hides as crond
 - perl spam daemon
 - tests to gmail, yahoo, hotmail - op address -> good to work 
  -> ability to detect if on a blacklist

Victims: 1888 linux, 61 BSD, 2 windows (via cygwin), 19 OSX, 241 other (ARM)

pcap dump -> user agent via wget

"operation" backed by law enforcement
 - targets only windows clients - testing on unix shows no results
 - unable to reach core machines

~40% root credentials stolen

Money = spam

500,000 redirects/day -> 20% exploit backs

kernel.org infected 2011

reconn script
 - MITM ssh to capture data -> perl stdout, still weird
 - inline backticks :<
 - self-cleaning

LD_preload checks - will avoid infecting machine if enabled. 

more fail conditions if server is possibly monitored (nagios)
 - assumes server is monitored by someone, might not be the easiest target

Perl DATA 
 - pass via ssh
 - will replace hash of self with real
 - can rewrite rpm history
 - gpg signed malware
 - can change SELinux policy
 - will place other rootkits w/self

if inspecting use out of band forensics
 - auditd
 - gcore <pid> - see reverse engineering tute

`proc` can extract deleted execs
procfs crond - check location

/proc/id copy before killing - ENV var for password in process

tools for investigation - lsof, strace, lpcs, shmcat (warning, these might be compromised on a system)

perl tidy, then grok nicer code - B::Deparse

3proxy - vector

upstream LB in malware

iptables - port redirect - vector

Lime - 504 labs - volitility

Once published, malware changes 
 - one app thanks ESET in malware

On reinstallation, do NOT reuse the same credentials

Use FreeIPA or google auth 2-factor

