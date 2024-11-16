## Difference between SQL and NoSQL

**SQL Databases**

SQL (Structured Query Language) databases are relational databases where data is stored in structured tables with predefined schemas. They rely on relationships between tables to organize and query data effectively.

*   Examples: MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server.


**NoSQL Databases**

NoSQL (Not Only SQL) databases are non-relational and store data in a variety of formats, including key-value pairs, documents, wide-columns, or graphs. They are designed for flexibility, scalability, and handling unstructured or semi-structured dat


*   Examples: MongoDB, Cassandra, Redis, DynamoDB, Neo4j.

## CORS Policy

## what is cors
Cross-Origin Resource Sharing (CORS) is a security feature implemented in web browsers that allows or restricts web pages from making requests to a different domain than the one that served the web page. 

**Key Features**

**Same-Origin Policy**
This policy restricts web pages from making requests to a different domain, protocol, or port.It is designed to protect user data from cross-site request forgery (CSRF) attacks.By default, browsers enforce the same-origin policy

**CORS Policy**
This policy allows web pages to make requests to a different domain, protocol, or port.It is designed to enable web applications to share resources across different domains.


CORS allows servers to specify who can access their resources by using HTTP headers.
When a web application makes a cross-origin request, the browser sends an Origin header to the server.
The server can respond with headers like Access-Control-Allow-Origin to indicate whether the request is allowed.

*   For certain types of requests (e.g., those that modify data), the browser sends a "preflight" request using the HTTP OPTIONS method to check if the actual request is safe to send.
    
*   The server must respond with appropriate CORS headers to allow the actual request.
    
*   **CORS Headers:**
    
    *   **Access-Control-Allow-Origin:** Specifies which origins are permitted to access the resource.
        
    *   **Access-Control-Allow-Methods:** Lists the HTTP methods that are allowed when accessing the resource.
        
    *   **Access-Control-Allow-Headers:** Indicates which headers can be used in the actual request.
        
    *   **Access-Control-Allow-Credentials:** Indicates whether credentials (like cookies) can be included in the request.
        
*   **Benefits of CORS:**
    
*   **Enhanced Security:**
    

*   CORS helps mitigate risks associated with cross-origin requests, ensuring that only authorized domains can access sensitive resources.
    
*   **Flexibility for Developers:**
    
    *   It allows developers to create applications that can interact with APIs hosted on different domains, enabling the use of third-party services.
        
*   **Support for Modern Browsers:**
    
    *   CORS is supported by all modern web browsers, making it a standard approach for handling cross-origin requests.
