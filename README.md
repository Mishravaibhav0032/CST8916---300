<b>Group :- 14</b>
<h1> Real-time Stock Market Monitoring App: REST, GraphQL, and WebSockets :- </h1>
<p></p>
<h2>1. Introduction :-</h2>

<p>Tracking stock markets requires real-time updates to track the price of stocks, volume, and market trends. This analysis compares REST, GraphQL, and WebSockets in building a real-time stock market tracking application. We go over their pros, cons, and suggest the optimum architecture for data management and real-time updates.</p>


<h2>2. REST and GraphQL for Data Requests and Updates :-</h2>
<P></P>
<h3>2.1 Using REST for Stock Market Data Handling.</h3>
<P></P>
<p>REST (Representational State Transfer) is a popular API design that utilizes HTTP to interact with regular CRUD operations (Create, Read, Update, Delete). It has defined endpoints for data retrieval and updates.</p>

<p>Example REST API Endpoints :-</p>

<li>GET /stocks :- Fetches a list of all stocks and their latest prices.</li>
<li>GET /stocks/{symbol} :- Retrieves real-time data for a specific stock (e.g., AAPL, TSLA).</li>
<li>POST /stocks :- Adds a new stock entry to the system.</li>
<li>PUT /stocks/{symbol} :- Updates stock price, volume, and other market data.</li>
<li>DELETE /stocks/{symbol} :- Removes a stock from tracking.</li> <p></p>

<p>Advantages of REST for Stock Tracking :-</p>

1. Easy-to-use and well-documented API design.<p></p>
2. Compatible with web and mobile applications.<p></p>
3. Enables caching of oft-used data.<p></p>

<p>Drawbacks of REST for Stock Tracking :-</p>

1. Some endpoints cause under-fetching or over-fetching of data.<p></p>
2. Polling requires current updates, which increase the server load.<p></p>
3. Stateless nature implies that the server does not keep a continuous connection.<p></p>

<h3>2.2 Utilizing GraphQL in Handling Stock Market Data. </h3>
<p></p>
GraphQL is a query language that allows clients to get exactly the needed data, enhancing performance and reducing network overhead.
<p></p>
Example GraphQL Queries and Mutations:
<p></p>
Obtaining Stock Information :- <p></p>

```graphql
query {
  stocks {
    symbol
    name
    price
    volume
    changePercentage
  }
}
```

<p> Updating Stock Price :- </p>

```graphql
mutation {
  updateStock(symbol: "AAPL", price: 185.50) {
    symbol
    price
    volume
    changePercentage
  }
}
```

<p>Advantages of Utilizing GraphQL for Stock Tracking :-</p>

1. Flexible queries that fetch just needed information.<p></p>
2. Has one endpoint (/graphql), minimizing complexity.<p></p>
3. Supports subscriptions, enabling real-time updates without polling.<p></p>

<p>Drawbacks of GraphQL for Stock Monitoring :- </p>

1. More involved setup than REST.<p></p>
2. It is harder to use caching methods.<p></p>
3. May be slower for big, deeply nested queries.<p></p>

<p></p>
<h3>2.3 REST vs. GraphQL Comparison for Stock Market Monitoring :- </h3><p></p>
 
| Feature             |	REST                                        | GraphQL                                |
| ------------------- | ------------------------------------------- | -------------------------------------- |
| Data Fetching       | Fixed structure, may over-fetch/under-fetch | Fetches only needed fields             |
| Number of Endpoints |	Multiple                                    | Single (/graphql)                      |
| Real-time Support   | Polling required                            | Native subscriptions for live updates  |
| Ease of Use         | Simple but rigid                            | Flexible but requires a learning curve |
| Caching             | Easy to implement                           | More complex                           |

<h2> 3. WebSockets for Real-time Communication :-</h2>

<h3>3.1 How WebSockets Facilitate Real-time Stock Market Tracking?</h3>
<p>WebSockets provide a persistent connection between client and server, which allows for real-time stock prices without sequential API requests.</p>
<p>How WebSockets Function in a Stock Tracking Application :-</p>
1. Client connects to the WebSocket server: ws://stockserver.com/live<p></p>
2. Server posts live updates whenever prices change.<p></p>
3. Client gets live updates without polling or any further HTTP requests.<p></p>
<p></p>
WebSocket Example Message Format: <p></p>

```
{
  "symbol": "AAPL",
  "price": 185.75,
  "change": "-0.5%",
  "timestamp": "2025-03-04T14:32:00Z"
}
```
<p>Advantages of WebSockets for Stock Tracking :-</p>

1. Minimizes latency with real-time push updates.<p></p>
2. Has an ongoing, low-overhead connection.<p></p>
3. Perfect for real-time financial information and trading applications.<p></p>

<p>Drawbacks of using WebSockets for Stock Monitoring :-</p>

1. Needs additional server resources to keep the connections open.<p></p>
2. Is hard to scale to large numbers of simultaneous users.<p></p>

<h3>3.2 WebSockets vs. REST vs. GraphQL for Real-time Data Flow :- </h3>

| Feature       | REST                               | GraphQL                 | WebSockets                           |
| ------------- | ---------------------------------- | ----------------------- | ------------------------------------ |
| Communication | Request-response                   | Request-response        | Persistent bi-directional connection |
| Data Updates	| Polling required                   | Subscriptions supported | Instant push updates                 |
| Scalability	  | Easy but inefficient for real-time | Better than REST        | Requires load balancing              |
| Use Case	    | General APIs                       | Optimized data fetching | Live streaming data                  |

<h2>4. Why GraphQL?</h2>
<p></p>
1. Efficient Data Fetching :- Fetches only the necessary stock information.<p></p>
2. Single Endpoint :-  /graphql simplifies API management.<p></p>
3. GraphQL Subscriptions :- Provides event-driven stock updates.<p></p>

<h2>5. Why WebSockets?</h2>

1. Real-time Market Updates :- Essential for fast-moving stock data.<p></p>
2. Low Latency :- Ensures traders receive accurate and instant information.<p></p>
3. Ideal for Live Trading Dashboards :- Supports continuous updates without polling.<p></p>

<h2>6. Final Architecture :-</h2>

GraphQL handles initial stock data retrieval.<p></p>
WebSockets provide live price updates.<p></p>
GraphQL subscriptions enable targeted real-time updates.<p></p>

<h2>7. Group Contributions :- </h2>

Member 1 :- Documented REST and GraphQL implementations.<p></p>
Member 2 :- Researched and wrote about WebSockets and final recommendations.<p></p>

<h2>8. References :- </h2>

(1) Codecademy. (n.d.). What is REST? Codecademy. https://www.codecademy.com/article/what-is-rest <p></p>
(2) Hygraph. (2024, October 17). What is GraphQL? https://hygraph.com/learn/graphql  <p></p>
(3) GeeksforGeeks. (2024b, August 22). What is web socket and how it is different from the HTTP? GeeksforGeeks. https://www.geeksforgeeks.org/what-is-web-socket-and-how-it-is-different-from-the-http/  <p></p>
(4) DeepSeek - Into the Unknown. (n.d.). https://deepsearchs.com/chat/?gad_source=1&gclid=CjwKCAiAiaC-BhBEEiwAjY99qDlqzhu2WlD5uhubsFQqqmNnaJNIzkJVCq8HHE3p5XU5Ovm_gwFtfBoCDewQAvD_BwE  <p></p>

<h2>9. Video Presentation Link :-</h2>
https://drive.google.com/file/d/1-aKOG0gCowofL4TOaqux3qa5Elz2ERk4/view?usp=drive_link
<h2>10. Conclusion :-</h2>
<p></p>
With GraphQL for high-performance data querying and WebSockets for real-time communication, our stock market monitor application provides high performance, low latency, and great scalability. This stack provides stable real-time stock monitoring and thus represents the best choice for our use case.

<h6>Group Member Details :-</h6><p></p>
Name :- Vaibhav Mishra - 041165850
Name :- Meet Prajapati - 041178387
