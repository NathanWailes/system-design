### Summary of Ticketmaster System Design

#### Functional Requirements
1. Users should be able to search for events.
2. Users should be able to view events.
3. Users should be able to book tickets.

#### Non-Functional Requirements
1. Scalability for searching/viewing events.
2. Consistency for booking.

#### Core Entities
- **Event**: Stores event details.
- **Performer**: Information about the performer.
- **Venue**: Event location details.
- **Ticket**: Individual ticket details.
- **Booking**: Manages user ticket purchases.

#### High-Level Design Summary

##### Search Events
- **Endpoint**: `GET /events/search?parameters`
- **Components**: Client, Load Balancer, API Gateway, Search Service, Events DB.
- **Flow**: Client sends search query, Search Service fetches matching events from Events DB, returns results to client.

##### View Events
- **Endpoint**: `GET /events/details/{eventId}`
- **Components**: Client, Load Balancer, API Gateway, Event CRUD Service, Events DB.
- **Flow**: Client requests event details through Load Balancer and API Gateway, Event CRUD Service fetches data from Events DB, returns details to client.

##### Book Tickets
- **Endpoints**: `POST /booking/checkout`, `POST /booking/confirm`
- **Components**: Client, Load Balancer, API Gateway, Booking Service, Redis (for locking), Payment Processor (e.g., Stripe), Events DB.
- **Flow**:
  1. **Checkout**: Client sends booking request, Booking Service locks ticket in Redis, creates in-progress booking in DB.
  2. **Confirm**: Client completes payment, Stripe processes payment, confirms booking in DB, updates ticket status to "sold".

#### Potential Deep Dives Summary

1. How do we support millions of concurrent requests during peak events?
   - **Solution**: Use caching, load balancing, and horizontal scaling.

2. How do we ensure seat map updates in real-time during high-demand events?
   - **Solution**: Implement Server-Sent Events (SSE) for real-time updates or use a virtual waiting queue.

3. How do we handle complex queries and high-volume traffic efficiently?
   - **Solution**: Use a full-text search engine like Elasticsearch.

4. How do we speed up frequent searches and reduce load?
   - **Solution**: Implement query result caching and edge caching techniques using Redis or Memcached.

[Source](https://www.hellointerview.com/learn/system-design/answer-keys/ticketmaster)
