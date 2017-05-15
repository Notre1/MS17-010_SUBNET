
# MS17-010_SUBNET

This is a simple fork of the Python scanner for MS17-010 at https://github.com/RiskSense-Ops/MS17-010.

The only modification is that the script now takes one or more IPv4 CIDR networks as input, and checks through every host on each of them sequentially.  I just built it to speed some scanning I was doing.

Usage (for two example networks: 192.168.1.0/24 and 172.16.30.0/23):

    Unix:    python2.7 smb_ms17_010.py 192.168.1.0/24 172.16.30.0/23
    Windows: py -2 smb_ms17_010.py 192.168.1.0/24 172.16.30.0/2

It requires the 'ipaddress' library for Python 2, you can add it with pip as follows:

    Unix:    python2.7 -m pip install py2-ipaddress
    Windows: py -2 -m pip install py2-ipaddress


Original description from RiskSense below:

********************************************************************

# MS17-010
MS17-010 is the Microsoft security bulletin which fixes several remote code execution vulnerabilities in the SMB service on Windows systems.

There are numerous things about MS17-010 that make it esoteric, such as manipulating the Windows kernel pool heap allocations, running remote Windows ring 0 shellcode, and the intricacies of the different SMB protocol versions.

We previously improved the ExtraBacon exploit. https://github.com/RiskSense-Ops/CVE-2016-6366

## Scanners
The scanner uses uncredentialed information leakage to determine if the MS17-010 patch is installed on a host. If it is not installed, it will also check for a DoublePulsar infections.

## Resources 
- https://zerosum0x0.blogspot.com/2017/04/doublepulsar-initial-smb-backdoor-ring.html
- https://countercept.com/our-thinking/analyzing-the-doublepulsar-kernel-dll-injection-technique/
- https://www.rapid7.com/db/modules/auxiliary/scanner/smb/smb_ms17_010

## Disclaimer
This code serves an important business purpose for penetration testers and others to show impact to organizations, without having to run NSA malware binaries. We must ask that you use these tools for their intended, lawful purposes, and only with consent of targets.

### License
Apache 2.0 and MSF

### Credits
- @zerosum0x0
- @jennamagius
- @The_Naterz
- @Aleph___Naught
- @nixawk
- @JukeLennings (Countercept)

### Acknowledgements
- Shadow Brokers
- Equation Group
- skape
- Stephen Fewer
