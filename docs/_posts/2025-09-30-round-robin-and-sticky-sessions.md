### What is Round-robin and what are sticky sessions?
Round-robin and sticky sessions are a way to load balance servers. Load balancers spread client requests across multiple servers.

### Why load balance and not just have a bigger server? 
Load balancing is good for improving performance and availability. Spreading requests across multiple servers allows for a fresh server to respond to a request and not one that is already tied up handling a request from a different client. Also, if a server becomes unhealthy or unresponsive it can be pulled manually or automatically from the load balancer and put back when it is healthy again.

### Round-robin

In round-robin load balancing, when a client makes a request the response will come from a server that is on a list of servers. The server that responds is chosen in sequential order. Even multiple requests from the same client could be routed to a different sever each time. This is great for evenly distributing traffic between a group of servers. However, an issue comes into play when you need state management.

### State

The web is inherently stateless. In it's simplest form the client makes a request to the server, the server handles the request and responds to the client. The server keeps no memory of this interaction. This is great for sites like blog.cammurphy.com, because no user history is required. However, it does not work well for sites like Facebook that you need to login for. 

A strategy to deal with this is, store information about the client on a servers memory *such as is the client authenticated?*. Subsequent requests will check the servers memory and see if it is an authenticated client and proceed in kind. However, memory is not shared among servers. If the next request is routed to a different server, the client who was logged in will show as logged out because they are not in this servers memory. Leading to frustration among users who have to constantly log back in. This is where Sticky Sessions come in.

### Sticky Sessions

One way to implement Sticky Sessions is on initial request from a client to a server. The server will respond with the regular response, but in addition it will set a cookie on the browser indicating what server responded. So now for subsequent requests the load balancer will check for a cookie and route to the same server that did the initial response. This will allow the client to utilize the on server memory set before. While also keeping load balancing for requests coming from different clients. There are better ways to maintain sessions for a client, but this is a way to do it on the networking level.
