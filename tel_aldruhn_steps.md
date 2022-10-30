# Telaldruhn 192.168.2.9
## Andrea Zonnekus 18758119

nbtscan -r 192.168.2.0/24 > hosts

cat hosts

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.001.png)

sudo cat hosts | grep -oE '192.168.2.[0-9]{1,3}' > ips

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.002.png)

map -F -Pn -n --excludefile ips -oA other\_hosts --open 192.168.2.0/24

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.003.png)



sudo nmap -sV -F -O 192.168.2.9 -oN host -Pn

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.004.png)

sudo gobuster dir -u 192.168.2.9 -w /usr/share/dirb/wordlists/big.txt -o http\_enum -x php,html,js,txt,aspx

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.005.png)

python3 rpcdump.py 192.168.2.9 -port 135

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.006.png)

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.007.png)

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.008.png)

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.009.png)

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.010.png)

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.011.png)

<https://book.hacktricks.xyz/network-services-pentesting/135-pentesting-msrpc>

![](tel_aldruhn_steps/Aspose.Words.88c0842f-93c7-4b87-b090-e64fed2155f5.012.png)
