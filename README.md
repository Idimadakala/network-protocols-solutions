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
Network Load Balancer (NLB): Operates at Layer 4 for TCP/UDP traffic distribution.
							 Reassembles TCP segments (NLB) or makes routing decisions based on TCP/UDP headers (NLB).
Elastic Load Balancer (ELB): 

AWS Service Example: AWS CloudFront, which serves as a content delivery network (CDN) and caches content at edge locations.

NLB operates at Layer 4 (Transport Layer), 
while ALB operates at Layer 7 (Application Layer). 
Other services like Route 53, API Gateway, and CloudFront also primarily work at Layer 7, 
although the actual data transmission happens over the physical layer of the network.