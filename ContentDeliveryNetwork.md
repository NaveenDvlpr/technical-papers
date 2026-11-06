# CDN

CDN: Content Delivery Network or also called Content Distribution Network is geographically distributed network of proxy servers and corresponding data centers. It eliminates the problem of long loading time of application due to distance of servers by bringing proxy servers near to the user. A request used to handle by a server in a different continent can be done by a proxy server nearest to the user.

A proxy server is an intermediary server between a client requesting a resource and the server then providing that resource.

### Helping busineses
CDNs are a layer in the internet ecosystem. CDN does not do a business with the end users. They make businesses to quickly accessible to users. Content owners and E-commerce companies pay CDN providing companies to reduce their bandwidth on servers and quick access of the content to the end user. Content delivery service providers include Akamai Technologies, Cloudflare, Amazon CloudFront, Qwilt (Cisco), Fastly, CDN77, BunnyCDN, EdgeNext, and Google Cloud CDN.

### Benefits:
* Reduced bandwidth costs
* Improved page loading
* Increased global availability
* Increased security

### Working 
CDN comaponies setup POPs(point of presence) across the globe or selected regions. These POPs act as network interface points. Requests from end users are algorithmically directed to nodes which provide faster acces to the content. They serve the user with the request. The POPs where the users interact with are called Edge Servers. We only store static data in CDN servers. Any dynamic data like user configuration data is stored in the origin server. Files in the edge servers have a TTL(Time to leave). Once the TTL finishes the CDN servers will request for the data from the origin server.


### CDN concepts:
Content Provider Origin Server: the web server providing the source content
CDN entry point(s): the servers within the CDN that fetch the content from the origin
CDN Origin Shield: the CDN service helping to protect the origin server in case of heavy traffic
CDN Edge Servers: the CDN servers serving the content request from the clients
CDN footprint: the geographic areas where the CDN Edge Servers can effectively serve clients' requests
CDN selector: in the context of multi-CDN, a decision-making service to choose among multiple CDNs
CDN offloading: in the context of Peer-to-Peer CDN, a mechanism to help deliver the content between clients who are consuming it, in addition to CDN Edge Server delivery


### Case study(Giphy)

Giphy servies 10 billion media content every day to its users. This is done using a CDN. Serving images and videos is a big challenge when we consider their size compared to text based data. CDN caches images, videos and other static data. CDN will also store thie responses. They will not store API responses like authentication. API responses which are very static in nature are store in CDN servers. Since CDN servers are distributed across the globe. This makes the end user experience seamless. Every edge server has its own cache. Whenever there is a cache miss the edge servers will contact the origin server for the information. This can increase the load on the origin server. To reduce it, CDNs use origin shield servers. Orgin shield servers interactly directly with origin and they cache their data. Now, edge servers can interact with origin shield servers. This reduces the load on the origin server. Shields are only few in number. Giphy maintains route specific TTL. It maintains response oriented caching.
