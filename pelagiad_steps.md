# Pelagiad 192.168.2.7
## Andrea Zonnekus 18758119

sudo nmap -p- -O -sV 192.168.2.7 -oN host -Pn

![](pelagiad_steps/Aspose.Words.58904709-0453-4e87-aae1-3641960713a7.001.png)

gobuster dir -u 192.168.2.7 -w /usr/share/dirb/wordlists/big.txt -o http\_80

