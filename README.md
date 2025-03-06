<h1> Real-time Stock Market Monitoring App: REST, GraphQL, and WebSockets :- </h1>
<p></p>
<h2>1. Introduction</h2>

<p>Tracking stock markets requires real-time updates to track the price of stocks, volume, and market trends. This analysis compares REST, GraphQL, and WebSockets in building a real-time stock market tracking application. We go over their pros, cons, and suggest the optimum architecture for data management and real-time updates.</p>


<h2>2. REST and GraphQL for Data Requests and Updates</h2>
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
query { <p></p>
  stocks {<p></p>
    symbol<p></p>
    name<p></p>
    price<p></p>
    volume<p></p>
    changePercentage<p></p>
  }<p></p>
}<p></p>
<p></p>
Updating Stock Price :- <p></p>
mutation {<p></p>
  updateStock(symbol: "AAPL", price: 185.50) { <p></p>
    symbol<p></p>
    price<p></p>
    volume<p></p>
    changePercentage<p></p>
  }<p></p>
}<p></p>
