# Network protocol communication

AWS Route53 resolves the DNS name to IP Adddress

L7 - Application Layer - interact with end-user with http or https or http/3 protocols 
L6 - presentation layer - connect l3 and l7
L5 - session layer - manages sessions and connections between the applications
L4 - Transport Layer - Ensure reliable transmission of data - UDP and TCP 
L3 - Network Layer - manages communication between different networks
L2 - Data link layer - communication between the adjacent network nodes
L1 - Physical layer - deals with physcial connection between the nodes - AWS Direct Connect 


Application Load Balancer (ALB): Operates at Layer 7 for content-based routing, handling HTTP/HTTPS requests.
								 Makes routing decisions based on HTTP/HTTPS headers and content (ALB) 
								 or forwards traffic based on TCP/UDP information (NLB).
								 supports path-based routing, host-based routing, query string parameter based routing, source IP address based routing
Network Load Balancer (NLB): Operates at Layer 4 for TCP/UDP traffic distribution.
							 Reassembles TCP segments (NLB) or makes routing decisions based on TCP/UDP headers (NLB).
							 offers ultra high perfor, low latency, TLS offloading at scale
							 
Elastic Load Balancer (ELB): 

AWS Service Example: AWS CloudFront, which serves as a content delivery network (CDN) and caches content at edge locations.

NLB operates at Layer 4 (Transport Layer), 
while ALB operates at Layer 7 (Application Layer). 
Other services like Route 53, API Gateway, and CloudFront also primarily work at Layer 7, 
although the actual data transmission happens over the physical layer of the network.

-> SSH (Secure Shell) communication takes place using the SSH protocol, which is specifically designed to secure network communication. 
-> SSH operates over the Transport Layer Protocol (TCP), typically using port 22 as its default
-> All the communication between client and server are encrypter using RSA to secure the communication channel.
-> 
ssh -i <pem-file> ec2-user@<public-ipaddr>

HTTP:
-> Operates over TCP (typically on port 80).
-> Transfers unencrypted data, making it less secure.

HTTPS:

-> Adds encryption using TLS/SSL for secure data exchange.
-> Operates over TCP (typically on port 443).
-> Protects against data interception and tampering.

File transfer -> protocol: TCP -> on port: 20 and 21
Send/Receive Email -> protocal: TCP -> on port: port 25, or port 587 for encrypted connection
Syncs emails across devices. -> IMAP (Internet Message Access Protocol) -> Operates over TCP (port 143 or port 993 for encrypted connections).
Downloads emails from the server to a single device. -> POP3 (Post Office Protocol) -> Uses TCP (port 110 or port 995 for encrypted connections).
Address translation to IPAddr -> DNS -> Operates over UDP or TCP -> on port 53

netstat
netstat -l
netstat -lt (-t: TCP)
netstat -ltn -- ports (Identify the process using the port: 80 and kill it : sudo netstat -ltnp | grep '80' and kill the process with pid)
netstat -ltp -- pid 
netstat -lu (-u: UDP)
netstat -lun -- ports
netstat -lup -- pid

telnet - 
netcat - 

Your identification has been saved in /home/saisrinivasi/.ssh/id_rsa.
Your public key has been saved in /home/saisrinivasi/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:n38qk0QEZjZN173dK4eiPpf0KlMF99Hi5y3nHGSVLwU saisrinivasi@ip-172-31-13-71.ap-south-1.compute.internal


May 02 04:07:27 ip-172-31-13-71.ap-south-1.compute.internal systemd[1]: Starting The nginx HTTP and reverse proxy server...
May 02 04:07:27 ip-172-31-13-71.ap-south-1.compute.internal nginx[26907]: nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
May 02 04:07:27 ip-172-31-13-71.ap-south-1.compute.internal nginx[26907]: nginx: configuration file /etc/nginx/nginx.conf test is successful
May 02 04:07:27 ip-172-31-13-71.ap-south-1.compute.internal systemd[1]: Started The nginx HTTP and reverse proxy server.

# to display the running process 
ps
ps -a (tty - Teletype terminal and pts -pseudo terminal slave)
sed - stream editor (we can edit on the fly)
for ex: FILENAME=apache-tomcat.tar.gz
echo $FILENAME | sed 's/.tar.gz//' (here s is a substitution command: s/old/new)
ps -u (with usernames)
ps -ef (list all the process)

# create a user
sudo useradd saisrinivasi
sudo passwd saisrinivasi
usermod -aG wheel saisrinivasi (-a: append -G: group)
# to get the groups
use command - groups and it returns - ec2-user adm wheel systemd-journal
getent group wheel 
	wheel:x:10:ec2-user,saisrinivasi
getent group ec2-user

#switch the user
su - saisrinivasi

# lean os and add extras to it 
sudo amazon-linux-extras install nginx1
yum repolist
yum install nginx
systemctl status nginx
systemctl start nginx
systemctl status nginx

# check the os, system release
cat /etc/os-release
cat /etc/system-release

# list of installed packages
yum list installed
yum repolist






