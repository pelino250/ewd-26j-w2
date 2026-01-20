## Activity: The Moto-Taxi SQL Sprint

**Time:** 30 Minutes

**Platform:** GitHub Classroom (Local or Codespaces)

**Goal:** Build, populate, and query a relational database using a unified schema.

### 1. Unified Schema Requirements (DDL) (10 Minutes)

Every group must use the following table and column names to ensure the app's services can communicate. Write your `CREATE TABLE` statements in a file named `schema.sql`.

| Table | Required Columns | Key Constraints |
| --- | --- | --- |
| **`riders`** | `rider_id` (INT), `name` (VARCHAR), `motorcycle_plate` (VARCHAR) | <br>`rider_id` is PK 

 |
| **`passengers`** | `passenger_id` (INT), `name` (VARCHAR), `phone` (VARCHAR) | <br>`passenger_id` is PK 

 |
| **`trips`** | `trip_id` (INT), `rider_id` (INT), `passenger_id` (INT), `fare` (DECIMAL), `trip_date` (DATETIME) | `trip_id` is PK; `rider_id` & `passenger_id` are FKs 

 |

### 2. The Population Challenge (DML) (8 Minutes)

Using `data.sql`, populate the system. Your data must respect the **Referential Integrity** of the schema.

**Task:** Insert 3 unique Riders and 3 unique Passengers.

**The Challenge:** Insert 5 Trips where at least **one Rider** has completed **two different Trips**.

**Constraint:** You cannot insert a Trip for a `rider_id` that does not exist in the `riders` table.


### 3. The Performance Query (DQL) (10 Minutes)

Write a script named `analysis.sql` to answer this business request: *"Which rider has generated the most revenue today?"*

**Requirement:** Your query must use an `INNER JOIN` to connect `riders` and `trips`.

**Logic:** Use `SUM(fare)` grouped by the rider's name and sorted in descending order.


### 4. Submission (2 Minutes)

1. Verify your code by running: `mysql -u root -p < schema.sql data.sql analysis.sql`.
2. Commit and push your three `.sql` files to your GitHub Classroom repository.
