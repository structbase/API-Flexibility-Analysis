### Task 2: Written Reflection – API Flexibility Analysis

**The Over-fetching and Under-fetching Problem**
In the context of REST APIs, **_over-fetching_** occurs when an API endpoint returns more data than the client actually needs. This happens because REST endpoints are typically designed with a fixed response structure that must serve many different use cases. As a result, clients often receive unnecessary fields, which increases payload size and wastes bandwidth.

**_Under-fetching_**, on the other hand, occurs when a single endpoint does not return enough data to satisfy the client’s needs. In this case, the client must make multiple requests to different endpoints to gather all the required information. This leads to additional network requests, increased latency, and tighter coupling to API documentation.

GraphQL’s query language inherently solves both problems by allowing the **_client to define the exact shape of the data it needs_**. Instead of receiving a predefined response, the client specifies which fields to retrieve in a query. This eliminates over-fetching by excluding unnecessary data and prevents under-fetching by enabling the client to retrieve all required related data in a **_single request_**. As a result, GraphQL provides more efficient data fetching and gives greater control to the client.

---

**Endpoint and Schema Philosophy**
In a typical REST API, there are many endpoints, and each endpoint is specified for specific resources, getting pre-defined resources, and the endpoint reflects that specified resource; the name of the endpoint should reflect the resource.
A **_GraphQL API_**, on the other hand, uses a single endpoint. Instead of many multiple endpoints for different types of data, we can make a single request return all of the resources we define before requesting.
The **_advantage of using GraphQL’s strongly-typed schema_** benefits frontend developers because, as frontend developers, we know exactly what data is available, and with one request we can get all other resources, and we don't have to wait for multiple requests to return.

---

**Caching and Complexity**
When it comes to caching, it is a lot simpler with a **_REST API_** because it uses fixed URLs and standard HTTP methods. Since each endpoint always returns the same type of data, servers and browsers can easily cache responses.
**_GraphQL_** is harder to cache because it usually uses a single endpoint, and resources are not predefined, and their shape is different based on user needs. Since every request can possibly ask for different data, it's not as easy to reuse cached responses.
A use case where GraphQL’s flexibility outweighs caching complexity is a **_data-heavy app with complex relationships_**, like a dashboard that needs user info, posts, and related data all at once.
