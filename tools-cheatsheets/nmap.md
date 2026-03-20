# Nmap Cheatsheet

## Basic Scans
```bash
nmap -sV -sC -oN scan.txt <target>       # default scripts + version
nmap -p- --min-rate 5000 <target>        # all ports fast
nmap -A -T4 <target>                     # aggressive
nmap -sU -top-ports 20 <target>          # UDP top 20
```

## Useful Flags
```bash
-sV     # version detection
-sC     # default scripts
-O      # OS detection
-oN     # normal output
-oA     # all formats
--script vuln  # vuln scan
```
