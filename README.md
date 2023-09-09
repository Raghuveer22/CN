# CN
When a DNS query is made to resolve the IP address of a server, the DNS resolver checks its cache to see if it already has the IP address information for the requested domain name. This cache is a temporary storage that DNS resolvers use to store recently resolved domain names and their corresponding IP addresses. If the IP address is present in the cache, it means that the resolver has previously looked up this domain name, and the IP address is still valid according to the time-to-live (TTL) value associated with the cached record.

Here's what happens when the IP address is present in the cache:

1. **Cache Lookup**: The DNS resolver first checks its cache for the domain name (e.g., github.com) that it needs to resolve. It looks for a matching entry that contains the IP address and TTL information.

2. **TTL Check**: If the cache entry is found, the resolver checks the TTL associated with that entry. The TTL is a value expressed in seconds and indicates how long the DNS information is considered valid. If the TTL has not expired, and the cached IP address is still within its validity period, the resolver can use this IP address without making a new DNS query.

3. **Using Cached IP**: If the TTL has not expired, the resolver can use the cached IP address to establish a connection to the GitHub server. This saves time and reduces DNS query traffic on the network.

4. **Background Refresh**: While using the cached IP address, the DNS resolver may also initiate a background process to refresh the cache entry. It does this by sending periodic queries to the authoritative DNS servers for the domain to check for any changes in the IP address or TTL. If there are updates, the cache will be updated accordingly.

5. **Response to Requestor**: The resolver returns the cached IP address to the application or device that made the DNS query. The application can then use this IP address to connect to the GitHub server.

Using a cached IP address from a previous DNS query can significantly improve the efficiency and speed of network operations, as it eliminates the need to repeatedly perform DNS resolution for frequently accessed domains. However, it's essential for DNS resolvers to manage the cache properly and respect TTL values to ensure that they always provide accurate and up-to-date DNS information.
