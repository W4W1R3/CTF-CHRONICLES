# Description

Securing an important image requires good encryption. so we added extra security layer for your photo and now is unbreakable! 

# Solution
```
╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ····················································································································· ✔ │ 11:07:09 ─╮
╰─ steghide extract -sf cyber.jpg                                                                                                                                                                                         ─╯
Enter passphrase: 
steghide: could not extract any data with that passphrase!

```

Seems Encrypted 

Lets use Stegseek

```
╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ··················································································································· 1 ✘ │ 11:07:48 ─╮
╰─  time stegseek -sf cyber.jpg /usr/share/wordlists/rockyou.txt                                                                                                                                                          ─╯
StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found passphrase: "1234"
[i] Original filename: "flag.txt".
[i] Extracting to "cyber.jpg.out".

stegseek -sf cyber.jpg /usr/share/wordlists/rockyou.txt  0.02s user 0.00s system 21% cpu 0.101 total

╭─ ~/Rootank/CYBERTALENTS/CyberTalents-Introduction-to-Cybersecurity-Bootcamp-2023 ····················································································································· ✔ │ 11:09:32 ─╮
╰─ cat cyber.jpg.out                                                                                                                                                                                                      ─╯
flag{cyb3rs3cisaw3s0me}

```

# Flag

`flag{cyb3rs3cisaw3s0me}`

