# mongodb-event-management-system
# Event Management & Ticketing System (MongoDB)

This project demonstrates the design of a MongoDB-based backend system for managing events, ticket bookings, and user interactions. It focuses on schema design, sample data modeling, CRUD operations, aggregation pipelines, and indexing.

## Collections Used

### Users
Stores information about users of the system. Users can be either organizers or attendees.

Sample Data:
```js
{
  userId: "USR001",
  name: "Aarav Sharma",
  email: "aarav.sharma@gmail.com",
  phone: "9876543210",
  role: "organizer",
  createdAt: new Date()
}
Categories
Used to classify events based on their type.

Sample Data:

js
Copy code
{
  categoryId: "CAT02",
  name: "Technology",
  description: "Technology conferences and workshops"
}
Events
Stores details of events created by organizers.

Sample Data:

js
Copy code
{
  eventId: "EVT001",
  title: "Indie Music Night",
  category: "Music",
  venue: "Delhi Convention Centre",
  organizerId: "USR001",
  price: 1500,
  totalTickets: 300,
  availableTickets: 180,
  status: "upcoming"
}
Tickets
Represents ticket bookings made by users for events.

Sample Data:

js
Copy code
{
  ticketId: "TKT001",
  eventId: "EVT001",
  userId: "USR002",
  quantity: 2,
  totalAmount: 3000,
  status: "booked"
}
Features Implemented
Event creation and management

Ticket booking functionality

Event categorization

CRUD operations on all collections

Aggregation reports (ticket sales, revenue, attendees)

Indexing for query optimization

Note
The schemas, sample data, and queries included in this project are created for academic and demonstration purposes to explain MongoDB concepts and expected system behavior.
