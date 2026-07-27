# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_fitness.png)
<img width="1080" height="598" alt="WhatsApp Image 2026-07-27 at 18 31 07" src="https://github.com/user-attachments/assets/ff84007d-8ec7-47ff-a333-b9bc7e3cbdda" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Member  | member_id          |       |
|Trainer | trainer_id         |       |
|Program | program_id         |       |
|Session |session_id          |       |
|Payment |payment_id          |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|books         |M:N         |               |       |
|Enrolls       |M:N         |               |       |
|Assigns       |1:N         |               |       |
|Includes      |1:N         |               |       |
|Conducts      |1:N         |               |       |
|Attends       |M:N         |               |       |
|Makes         |1:N         |               |       |

### Assumptions
1. MEMBER — Books — TRAINER
Cardinality: Many-to-Many (M:N)
(A member can book many trainers, and a trainer can be booked by many members)

2.  MEMBER — Enrolls — PROGRAM
Cardinality: Many-to-Many (M:N)
(A member can enroll in multiple programs, and a program can have many members)

3.  TRAINER — Assigns — PROGRAM
Cardinality: One-to-Many (1:N)
(One trainer can handle multiple programs, but each program is assigned to one trainer)

4.  PROGRAM — Includes — SESSION
Cardinality: One-to-Many (1:N)
(One program includes multiple sessions, each session belongs to one program)

5.  TRAINER — Conducts — SESSION
Cardinality: One-to-Many (1:N)
(One trainer conducts many sessions, each session is conducted by one trainer)

6.  MEMBER — Attends — SESSION
Cardinality: Many-to-Many (M:N)
(Members can attend many sessions, and each session can have many members)

7.  MEMBER — Makes — PAYMENT
Cardinality: One-to-Many (1:N)
(One member can make multiple payments, each payment belongs to one member)

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)
<img width="1080" height="436" alt="image" src="https://github.com/user-attachments/assets/e59397b2-462b-400a-8513-457406535f26" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Member  | MemberID           |       |
|Book    | BookID             |       |
|Loan    | LoanID             |       |
|Fine    | FineID             |       |
|Registration| RegID          |       |
|Event   | EventID            |       |
|Speaker | SpeakerID          |       |
|Room    | RoomID             |       |
|Room_Booking| BookingID      |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|borrows       |1:N         |               |       |
|registersfor  |1:N         |               |       |       
|may have      |1:0/1       |               |       |
|has           |M:N         |               |       |
|booked for    |1:N         |               |       |

### Assumptions
1. MEMBER — borrows — BOOK
Cardinality: 1 : N
(One member can borrow many books, one book borrowed by one member at a time)

2.  MEMBER — registers for — REGISTRATION
Cardinality: 1 : N
(One member can have multiple registrations)

3.  REGISTRATION — EVENT
Cardinality: N : 1
(Many registrations belong to one event)

4.  BOOK — LOAN
Cardinality: 1 : N
(One book can have many loan records)

5.  LOAN — may have — FINE
Cardinality: 1 : 0/1
(A loan may or may not have a fine)

6.  EVENT — has — SPEAKER
Cardinality: M : N
(An event can have many speakers, a speaker can attend many events)

7.  EVENT — booked for — ROOM_BOOKING
Cardinality: 1 : N
(One event can have multiple room bookings)

8.  ROOM — ROOM_BOOKING
Cardinality: 1 : N
(One room can be booked many times)


---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)
<img width="1080" height="779" alt="image" src="https://github.com/user-attachments/assets/f6dc4cc4-1d64-49ac-a726-e0e724c01593" />



### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|Customer|CustomerID(PK)      |       |
|Reservation|ReservationID(PK)|       |
|Table|TableID(PK)            |       |
|Waiter|WaiterID(PK)          |       |
|Order|OrderID(PK)            |       |
|Order_item|OrderItemID(PK)   |       |
|Bill|BillID(PK)              |       |
|Category|CategoryID(PK)      |       |
|Dish|DishID(PK)              |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|  makes       |1:M         |               |       |
| reserved for |M:1         |               |       |
| served by    |M:1         |               |       |
|places        |1:M         |
|contains      |1:M         |
|generates     |1:1         |
|for           |1:1         |
|belongsto     |M:1         |

### Assumptions
1. RESERVATION → CUSTOMER is total participation because every reservation must have a customer.
2. ORDER → CUSTOMER is also total participation.
3. TABLE & WAITER have partial participation (they can exist without reservations).
4. ORDER_ITEM depends on ORDER, so it has total participation.
5. BILL and ORDER are tightly linked → both total (1,1).


---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
