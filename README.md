
# Linux Firewall using iptables

During my studies, I learned about network security and how important is to take measurements in securing our network.
So for my first project, I choose to build a simple but effective firewall in my Kali Linux virtual machine.
A firewall is a subsystem on a computer that blocks or allows certain network traffic from going into or out of our computer.

Sources : Network Basics for Hackers by Occupytheweb ,  https://www.netfilter.org/projects/iptables/index.html 


![image alt](https://github.com/fabianvagi91/projects/blob/c377fd6b80d301dfa0a679340e0c70552dfa3dfd/iptablesinstall.png)
I choose iptables due to their user-friendliness and because it's a long-standing framework that is secure and flexible. 

![image alt](https://github.com/fabianvagi91/projects/blob/d3c14782a55a493677f2f5d8b0014b5e2f79f168/iptables%20help.jpg)
In this picture we can see the useful commands.
-A is append rule to the chain -D delete rule  -L list -F erase list -j target -s source -d destination 

![image alt](https://github.com/fabianvagi91/projects/blob/72d91838330502b7a7e96f8cd8241c9721629cdd/iptablespolicy.png)
This is the default configuration and all the chains are in ACCEPT. 
This means that we accept connections without restrictions.

![image alt](https://github.com/fabianvagi91/projects/blob/6950366e5c8cfa3a78b012dac15e9eeaee5d1cd2/Iptablesblockfacebook.jpg) 
On the first rule, I pinged facebook.com, and based on the outcome of the ping request, I applied the first rule.
To block any connection coming and going to our computer from facebook.com
It's important to note that iptables will make a DNS lookup only at the time of the creation of the rule.
For this reason, It is preferable to use the IP address of the domain.
![image alt](https://github.com/fabianvagi91/projects/blob/c586794015d09f7287cf1434e439ad19697d0210/iptablescnnblock.jpg)
In the second rule that I applied, I created a rule that accepts any package coming from CNN.
Therefore I pinged the IP address of the domain.

![image alt](https://github.com/fabianvagi91/projects/blob/a704e92ec51dc45474e94a277f317eb9540f2f52/iptablesoutcome.png)
The rules have been applied and we can see that we dropped the packages coming from facebook.com and we accepted the packages from cnn.com
With facebook.com we don't have a response because it is blocked and cnn.com we allowed to receive traffic.

![image alt](https://github.com/fabianvagi91/projects/blob/79cdb355161dcdd526e7da12da109fbfef845b8b/iptables-blockport-list.jpg)
In the third rule, I applied two rules that block outgoing traffic to ports 80 and 443 which are HTTP and HTTPS traffic respectively.
Any attempt to access websites from my Kali machine will be blocked.
Shows also the outcome of the rules that we applied.

![image alt](https://github.com/fabianvagi91/projects/blob/fc73b72a8f3782f8ce394e92d61a3d5ae5f6b78c/iptables-noconneciton.jpg)
As the result of blocking the port 80 and 443 we dont recieve any package from any website


![image alt](https://github.com/fabianvagi91/projects/blob/a704e92ec51dc45474e94a277f317eb9540f2f52/ipttables%20end.png)
I was experimenting and learning with this framework so erased all the rules that I made using the command sudo iptables -F.

# conclusion

I acquired a deeper understanding of how firewalls work and explored different open-source frameworks in Kali Linux. I learned about the iptables framework and the new version, nftables. Nftables is better suited for larger networks, and although migrating from the old version (iptables) to the new version is challenging, I chose to experiment with nftables in a home network.
The order of the rules is critical. This means that iptables will search through the rules until it finds a match. For example, if the last two rules drop ports 80 and 443 and are placed before the domain rule, the user would never be able to reach cnn.com, as the drop rules would match before reaching the domain rule.

