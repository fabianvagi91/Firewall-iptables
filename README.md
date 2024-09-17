My name is Fabian Vagi and I am an aspiring cybersecurity professional.
I have a deep interest in raising technology and data security.
This portfolio showcases my journey, projects, and skills as I work towards becoming a cybersecurity expert.

About me

I have completed a 600-hour course in cybersecurity which gave me a solid foundation.
I completed several courses in Coursera and Cisco.
Also in tryhackme.com im in the top %5.
I am particularly interested in network security, SOC, IDS, and malware analysis.


# projects
Linux Firewall using iptables

During the course of my studies i learn about network security and how important is to take mesurements in securing our network.
So for my fist project i choose to build a simple but efective firewall in my kali linux virtual machine.
A firewall is a subsystem on a computer that blocks or allow certain network traffic from going into or out of our computer.

Sources : Network Basics for Hackers by Occupytheweb ,  https://www.netfilter.org/projects/iptables/index.html 


![image alt](https://github.com/fabianvagi91/projects/blob/c377fd6b80d301dfa0a679340e0c70552dfa3dfd/iptablesinstall.png)
I choose iptables due to its user frendliness and because its a long standing framework which is secure and flexible. 

![image alt](https://github.com/fabianvagi91/projects/blob/d3c14782a55a493677f2f5d8b0014b5e2f79f168/iptables%20help.jpg)
In this picture we can see the useful commands.
-A is append rule to the chain -D delete rule  -L list -F erase list -j target -s source -d destination

![image alt](https://github.com/fabianvagi91/projects/blob/72d91838330502b7a7e96f8cd8241c9721629cdd/iptablespolicy.png)
This is the default configuration and all the chains are in ACCEPT. 
Means that we accept connections without restrictions.
![image alt](https://github.com/fabianvagi91/projects/blob/f2a31b3737ea420a74f6b209cd7e7361dece0551/Iptablesblockfacebook.jpg)
As first try i pinged facebook.com and with the outcome of the ping i applyed the first rule.
To block any connection coming and going to our computer coming from facebook.com
Its important to note iptables is going to make a DNS lookup only after the rule has been made.
For its reason i pinged facebook.com so i can use the IP address of the domain.
![image alt](https://github.com/fabianvagi91/projects/blob/d3c14782a55a493677f2f5d8b0014b5e2f79f168/iptables%20outcome.png)
The rules have been aplyed and we can see that we drop the packages coming from facebook.com and we accept the packages from cnn.com
![image alt]( iptablesblock)
