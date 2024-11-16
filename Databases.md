## Difference between SQL and NoSQL

**SQL Databases**

SQL (Structured Query Language) databases are relational databases where data is stored in structured tables with predefined schemas. They rely on relationships between tables to organize and query data effectively.

- Examples: MySQL, PostgreSQL, Oracle Database, Microsoft SQL Server.

**NoSQL Databases**

NoSQL (Not Only SQL) databases are non-relational and store data in a variety of formats, including key-value pairs, documents, wide-columns, or graphs. They are designed for flexibility, scalability, and handling unstructured or semi-structured dat

- Examples: MongoDB, Cassandra, Redis, DynamoDB, Neo4j.

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

- For certain types of requests (e.g., those that modify data), the browser sends a "preflight" request using the HTTP OPTIONS method to check if the actual request is safe to send.
- The server must respond with appropriate CORS headers to allow the actual request.
- **CORS Headers:**

  - **Access-Control-Allow-Origin:** Specifies which origins are permitted to access the resource.
  - **Access-Control-Allow-Methods:** Lists the HTTP methods that are allowed when accessing the resource.
  - **Access-Control-Allow-Headers:** Indicates which headers can be used in the actual request.
  - **Access-Control-Allow-Credentials:** Indicates whether credentials (like cookies) can be included in the request.

- **Benefits of CORS:**
- **Enhanced Security:**

- CORS helps mitigate risks associated with cross-origin requests, ensuring that only authorized domains can access sensitive resources.
- **Flexibility for Developers:**

  - It allows developers to create applications that can interact with APIs hosted on different domains, enabling the use of third-party services.

- **Support for Modern Browsers:**

  - CORS is supported by all modern web browsers, making it a standard approach for handling cross-origin requests.

## ACID Transactions

In the context of databases, a transaction is a sequence of operations performed as a single logical unit of work. A transaction typically involves multiple operations such as reading, writing, or modifying data. The key characteristic of a transaction is that it must be executed completely or not at all; this ensures data integrity and consistency.

ACID (Atomicity, Consistency, Isolation, Durability) is a set of properties that ensure database transactions are processed reliably. The ACID properties are as follows:

1.  **Atomicity:** Ensures that a transaction is treated as a single, indivisible unit of work. If any part of the transaction fails, the entire transaction is rolled back to its previous state.
2.  **Consistency:** Guarantees that the database remains in a consistent state before and after the transaction. This means that the transaction must not violate any constraints or rules defined in the database.
3.  **Isolation:** Ensures that multiple transactions can be executed concurrently without interfering with each other. Each transaction sees a consistent view of the data, as if it were the only transaction executing.
4.  **Durability:** Ensures that once a transaction is committed, its effects are permanent and survive even in the event of a system failure.

ACID transactions are essential for maintaining data integrity and consistency in databases. They provide a robust and reliable way to manage concurrent access to shared data, ensuring that the database remains in a consistent state even in the presence of failures or concurrent transactions.

### Benefits of ACID Transactions

- **Data Integrity:** Ensures that data remains consistent and accurate, even in the presence of
  concurrent transactions or system failures.
- **Reliability:** Provides a robust and reliable way to manage concurrent access to shared data.
- **Scalability:** Enables multiple transactions to be executed concurrently without interfering with each other.
- **Flexibility:** Supports a wide range of database systems and applications, from simple to complex

### Use Cases for ACID Transactions

- **Banking and Finance:** ACID transactions are critical in banking and finance applications, where
  data integrity and consistency are paramount.
- **E-commerce:** ACID transactions are used in e-commerce applications to ensure that
  transactions are processed reliably and consistently.
- **Healthcare:** ACID transactions are used in healthcare applications to ensure that patient data is
  consistent and accurate.

### Conclusion

ACID transactions are a fundamental concept in database systems, ensuring data integrity and consistency in the presence of concurrent transactions or system failures. By understanding the benefits and use cases of ACID transactions, developers can design and implement robust and reliable database systems that meet the needs of their applications.

## MongoDB Aggregations

Aggregations in MongoDB are a powerful feature that allows you to perform complex data processing and analysis. By using the aggregation pipeline, you can efficiently manipulate and summarize your data to gain insights and generate meaningful reports.

### Example of an Aggregation Pipeline

Suppose you have a collection named sales that contains documents representing sales transactions, with fields like item, quantity, and price. You want to calculate the total sales for each item.

```javascript
db.sales.aggregate([
  {
    $group: {
      _id: "$item", // Group by the 'item' field
      totalQuantity: { $sum: "$quantity" }, // Sum the quantities
      totalSales: { $sum: { $multiply: ["$quantity", "$price"] } }, // Calculate total sales
    },
  },
  {
    $sort: { totalSales: -1 }, // Sort by total sales in descending order
  },
]);
```

### Key Features of Aggregations in MongoDB

1.  **Pipeline Approach:**

    - MongoDB uses an aggregation pipeline, which is a framework that processes data in stages. Each stage transforms the data as it passes through the pipeline. The output of one stage becomes the input for the next stage.

2.  **Stages:**

    - Each stage in the aggregation pipeline performs a specific operation, such as filtering documents, grouping them, or projecting fields. Common stages include:

      - **$match**: Filters documents based on specified criteria.
      - **$group**: Groups documents by a specified key and allows for the computation of aggregate values (e.g., sums, averages).
      - **$sort**: Sorts the documents based on specified fields.
      - **$project**: Reshapes documents by including or excluding fields and adding new computed fields.
      - **$limit**: Limits the number of documents passed to the next stage.
      - **$skip**: Skips a specified number of documents.

3.  **Operators:**

    - MongoDB provides a variety of aggregation operators that can be used within stages to perform calculations, manipulate strings, work with dates, and more. For example, **$sum**, **$avg**, **$max**, **$min**, and **$push** are commonly used operators.

### Benefits of MongoDB Aggregations

- **Efficient Data Processing:** Aggregations enable you to process large datasets efficiently, reducing the
  need for manual data manipulation and analysis.
- **Flexible Data Analysis:** Aggregations provide a flexible framework for data analysis, allowing you to
  perform a wide range of operations, from simple filtering to complex data transformations.
- **Improved Data Insights:** Aggregations enable you to generate meaningful reports and insights from your data
- **Scalability:** Aggregations can handle large datasets and scale with your data, making
  them an ideal choice for big data analytics.

## REST APIs

### Overview of REST APIs

REST (Representational State of Resource) APIs are an architectural style for designing networked applications. They
are based on resources identified by URIs, manipulated using a fixed set of operations. REST APIs are
stateless, cacheable, and use standard HTTP methods (GET, POST, PUT, DELETE)

### Key Features of REST APIs

1.  **Resource-Based:**

- REST APIs are based on resources, which are identified by URIs.
- Each resource has a unique identifier, and the API provides operations to manipulate these resources.

2.  **Stateless:**

- REST APIs do not maintain any information about the state of the client between requests.
- Each request contains all the information necessary to complete the request.

3.  **Cacheable:**

- REST APIs are designed to be cacheable, which means that responses can be cached by the client
  to reduce the number of requests made to the server.

4.  **Standard HTTP Methods:**

- REST APIs use standard HTTP methods to manipulate resources, such as GET, POST, PUT, and
  DELETE.

### Benefits of REST APIs

1.  **Platform Independence:** REST APIs are platform-independent, meaning they can be consumed by any
    client, regardless of the platform or technology used.
2.  **Scalability:** REST APIs are designed to scale, making them suitable for large
    applications.
3.  **Flexibility:** REST APIs provide a flexible framework for designing APIs, allowing developers to
    create APIs that meet specific business needs.
4.  **Easy to Implement:** REST APIs are relatively easy to implement, as they use standard
    HTTP methods and are based on resources identified by URIs.

### Common Use Cases for REST APIs

1.  **Web Services:** REST APIs are commonly used to expose web services, allowing clients to
    interact with the server and retrieve or update data.
2.  **Mobile Apps:** REST APIs are used in mobile apps to provide a backend interface for
    data retrieval and manipulation.
3.  **Microservices Architecture:** REST APIs are used in microservices architecture to enable
    communication between services.
4.  **API Gateways:** REST APIs are used in API gateways to provide a single
    entry point for clients to access multiple services.

## Difference between **PUT** and **PATCH**

PUT and PATCH are both used to update resources, but they differ in their approach.

- **PUT** is used to replace the entire resource with the new data provided in the request body
- **PATCH** is used to update only the specific parts of the resource that are provided in the
  request body.
