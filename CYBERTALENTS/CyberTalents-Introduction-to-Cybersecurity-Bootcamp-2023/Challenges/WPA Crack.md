# Description

You are conducting a WIFI pentest, Handshake has been captured and your task is to crack it

Flag format is just the password 

 Link:https://hubchallenges.s3-eu-west-1.amazonaws.com/Machines/wpa943050264305852656243865.cap


# Solution

first we have a pcap file.
```
╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ································································ ✔ │ 14:58:32 ─╮
╰─ file wpa943050264305852656243865.cap                                                                                                                                                                                   ─╯
wpa943050264305852656243865.cap: pcap capture file, microsecond ts (little-endian) - version 2.4 (802.11 with Prism header, capture length 65535)


```
**Cracking it using Hashcat**
First we will Transform it into a Crackable file
```
╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ··················································································· 127 ✘ │ 15:00:07 ─╮
╰─  hcxpcapngtool -o hashwifi.txt -E essidlist wpa943050264305852656243865.cap                                                                                                                                            ─╯

hcxpcapngtool 6.2.7 reading from wpa943050264305852656243865.cap...

summary capture file
--------------------
file name................................: wpa943050264305852656243865.cap
version (pcap/cap).......................: 2.4 (very basic format without any additional information)
timestamp minimum (GMT)..................: 10.05.2005 13:01:06
timestamp maximum (GMT)..................: 10.05.2005 13:01:06
used capture interfaces..................: 1
link layer header type...................: DLT_PRISM_HEADER (119)
endianness (capture system)...............: little endian
packets inside...........................: 13
frames with correct FCS..................: 13
ESSID (total unique).....................: 1
BEACON (total)...........................: 1
BEACON on 2.4 GHz channel (from IE_TAG)..: 7 
WPA encrypted............................: 2
EAPOL messages (total)...................: 4
EAPOL WPA messages.......................: 4
EAPOLTIME gap (measured maximum usec)....: 6788
EAPOL ANONCE error corrections (NC)......: not detected
EAPOL M1 messages (total)................: 1
EAPOL M2 messages (total)................: 1
EAPOL M3 messages (total)................: 1
EAPOL M4 messages (total)................: 1
EAPOL pairs (total)......................: 4
EAPOL pairs (best).......................: 1
EAPOL pairs written to 22000 hash file...: 1 (RC checked)
EAPOL M34E4 (authorized).................: 1

frequency statistics from radiotap header (frequency: received packets)


╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ······································ ✔ │ 15:02:18 ─╮
╰─ cat essidlist                                                                                                                                                                                                           ─╯
test

```

**Cracked**
```
╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ··········································· ✔ │ 15:02:18 ─╮

└─ hashcat -m 22000 hashwifi.txt -a 0 /usr/share/wordlists/rockyou.txt       
hashcat (v6.2.6) starting

OpenCL API (OpenCL 3.0 PoCL 3.0+debian  Linux, None+Asserts, RELOC, LLVM 13.0.1, SLEEF, DISTRO, POCL_DEBUG) - Platform #1 [The pocl project]
============================================================================================================================================
* Device #1: pthread-Intel(R) Core(TM) i5-3427U CPU @ 1.80GHz, 1389/2843 MB (512 MB allocatable), 4MCU

Minimum password length supported by kernel: 8
Maximum password length supported by kernel: 63

cc303dcc8fb0b285257353480a52c563:000d93ebb08c:00095b91535d:test:XXXXXX
                                                          
Session..........: hashcat
Status...........: Cracked
Hash.Mode........: 22000 (WPA-PBKDF2-PMKID+EAPOL)
Hash.Target......: hashwifi.txt
Time.Started.....: Sat Nov 25 15:05:32 2023 (25 secs)
Time.Estimated...: Sat Nov 25 15:05:57 2023 (0 secs)
Kernel.Feature...: Pure Kernel
Guess.Base.......: File (/usr/share/wordlists/rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:     2362 H/s (6.41ms) @ Accel:32 Loops:512 Thr:1 Vec:8
Recovered........: 1/1 (100.00%) Digests (total), 1/1 (100.00%) Digests (new)
Progress.........: 151377/14344385 (1.06%)
Rejected.........: 93777/151377 (61.95%)
Restore.Point....: 151064/14344385 (1.05%)
Restore.Sub.#1...: Salt:0 Amplifier:0-1 Iteration:0-1
Candidate.Engine.: Device Generator
Candidates.#1....: born1992 -> bangonthedoor
Hardware.Mon.#1..: Temp: 71c Util: 94%

Started: Sat Nov 25 15:04:41 2023
Stopped: Sat Nov 25 15:05:58 2023



```
# Flag

`born1992`
