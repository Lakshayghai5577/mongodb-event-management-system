# mongodb-event-management-system
This project is a MongoDB-based backend design for an **Event Management and Ticketing System**.  
It demonstrates how events can be created, categorized, browsed, and booked using MongoDB collections, queries, and aggregations.

The project is created as part of a MongoDB assignment to strengthen understanding of **schema design, data modeling, CRUD operations, aggregation pipelines, and indexing**.

---

## Project Objectives
- Design a structured MongoDB schema for an event management system  
- Model relationships between users, events, tickets, and categories  
- Perform CRUD operations on all collections  
- Generate analytical reports using aggregation pipelines  
- Apply indexing to optimize frequent queries  

---

## Collections Overview

### 1. Users Collection
The Users collection stores details of all users in the system.  
A user can be either:
- **Organizer** – creates and manages events  
- **Attendee** – browses events and books tickets  

**Key Fields:**
- userId  
- name  
- email  
- phone  
- role  
- createdAt  

**Sample Document:**
```js
{
  userId: "USR001",
  name: "Aarav Sharma",
  email: "aarav.sharma@gmail.com",
  phone: "9876543210",
  role: "organizer",
  createdAt: new Date()
}
2. Categories Collection
The Categories collection is used to classify events based on their nature.
This helps in filtering events and generating category-wise reports.

Examples: Music, Technology, Sports, Arts, Business, Education, Comedy

Key Fields:

categoryId

name

description

Sample Document:

js
Copy code
{
  categoryId: "CAT02",
  name: "Technology",
  description: "Technology conferences and workshops"
}
3. Events Collection
The Events collection stores details of events created by organizers.
Each event:

Belongs to a category

Is created by one organizer

Contains ticket pricing and availability

Key Fields:

eventId

title

description

category

dateTime

venue

organizerId

price

totalTickets

availableTickets

status

Sample Document:

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
4. Tickets Collection
The Tickets collection represents ticket bookings made by users for events.
A user can book multiple tickets for the same event.

Key Fields:

ticketId

eventId

userId

bookingDate

quantity

totalAmount

status

Sample Document:

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
Relationships Between Collections
One organizer can create multiple events

One event can have multiple ticket bookings

One user can book tickets for multiple events

Each event belongs to one category

Relationships are maintained using reference fields such as organizerId, eventId, and userId.

CRUD Operations
The project includes examples of:

Creating users, events, and tickets

Reading and filtering event data

Updating ticket availability after booking

Deleting records such as cancelled events

These operations demonstrate basic interaction with MongoDB collections.

Aggregation Pipelines
The following aggregation reports are implemented:

Top 5 events by ticket sales

Total revenue earned by an organizer

Number of attendees per event

Events grouped by category and status

These queries showcase MongoDB’s data analysis capabilities.

Indexing
Indexes are applied on commonly queried fields such as:

Event date

Event category

Ticket lookups by user and event

Indexing improves query performance and efficiency.

Implementation Note
The schemas, sample data, and queries included in this project are created for academic and demonstration purposes to explain MongoDB concepts and expected system behavior.
No live database connection is submitted as per assignment instructions.

Indexing for query optimization

Note
The schemas, sample data, and queries included in this project are created for academic and demonstration purposes to explain MongoDB concepts and expected system behavior.
