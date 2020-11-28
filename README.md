# LoadBalancer-Guide
This projects takes you through what a loadbalancer is

<h2>Information</h2>

What is a load balancer: 
- A loadbalancer receives requests from the UI / user and distributes the request to a netowrk of internal servers to provide the system with high reliability and high availability.
- It's also provides you with the opertunity to be able to add and remove servers in the network as per demand. 


Load balancing algorithms:
1. Rount Robin
- Squential request distributed
- First request goes to the first server, second to second, third do third and so on. 

2. Least Connections
- Request sent to the least used server in the network. 
- This will need a little additional resources form the loadbalancers in terms of metadata files due to the fact that the loadbalancers need to know which server is least used on the network. 

3. IP Hash
- Request sent to the server based on Client IP. 
- Request is distributed to a server based on the Client's IP address.

Sticky Sessions: 
- First of all, the session and all it's information is from a general point of view created and stored in the browser in the first place. The browser caches all the session information and specially the session ID. The session ID is sent to the loadbalancer and the loadbalancer takes care of the distribution.
- The loadbalancer has a cache which is uses to keep track of the session ID of the user.
- Common catch such as redis cachch can be used. 
- We need to allow the loadbalancer to go to the same instance (server) every time for the individual session ID.
