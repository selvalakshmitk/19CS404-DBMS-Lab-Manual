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
<img width="903" height="652" alt="image" src="https://github.com/user-attachments/assets/9481e101-6040-4af9-bbe6-96de78415762" />
 
![ER Diagram](er_diagram_fitness.png)

### Entities and Attributes

| Entity                        | Attributes (PK, FK)                                                           | Notes                                                 |
| ----------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------- |
| **MEMBER**                    | **Member_ID (PK)**, Name, DOB, Email, Phone, Status                           | Stores gym member details                             |
| **PROGRAM**                   | **Program_ID (PK)**, Program_Name, Program_Type, Description                  | Stores fitness program information                    |
| **TRAINER**                   | **Trainer_ID (PK)**, Trainer_Name, Phone, Email                               | Stores trainer details                                |
| **PERSONAL_TRAINING_SESSION** | **Session_ID (PK)**, Session_Date, Timings, Session_Type                      | Stores personal training session details              |
| **ATTENDANCE**                | **Attendance_ID (PK)**, Check_In_Time, Check_Out_Time, Status                 | Stores attendance records                             |
| **MEMBERSHIP_PAYMENT**        | **Payment_ID (PK)**, Date, Amount, Payment_Method, Receipt_No, Member_ID (FK) | Stores membership payment information                 |
| **SESSION_PAYMENT**           | **Session_ID (FK)**, Date, Amount, Payment_Method, Receipt_No                 | Stores payment details for personal training sessions |


### Relationships and Constraints

| Relationship                                      | Cardinality                           | Participation                    | Notes                                                                       |
| ------------------------------------------------- | ------------------------------------- | -------------------------------- | --------------------------------------------------------------------------- |
| **MEMBER enrolled in PROGRAM**                    | Many-to-Many (M:N)                    | Partial                          | A member can enroll in many programs and a program can have many members    |
| **PROGRAM assigned to TRAINER**                   | Many-to-One (M:1)                     | Total on PROGRAM side            | A trainer can handle many programs, each program is assigned to one trainer |
| **MEMBER books PERSONAL_TRAINING_SESSION**        | One-to-Many (1:M)                     | Partial                          | A member can book multiple sessions                                         |
| **PERSONAL_TRAINING_SESSION records ATTENDANCE**  | One-to-One (1:1) or One-to-Many (1:M) | Partial                          | Attendance is recorded for sessions                                         |
| **PERSONAL_TRAINING_SESSION has SESSION_PAYMENT** | One-to-One (1:1)                      | Total on SESSION_PAYMENT side    | Each session payment belongs to one session                                 |
| **MEMBER makes MEMBERSHIP_PAYMENT**               | One-to-Many (1:M)                     | Total on MEMBERSHIP_PAYMENT side | A member can make multiple payments                                         |

### Assumptions
- Each Member_ID, Program_ID, Trainer_ID, Session_ID, Attendance_ID, and Payment_ID uniquely identifies a record.
- One trainer may manage multiple fitness programs.
- A member may enroll in multiple programs and book multiple personal training sessions.
- Membership payments and session payments are maintained separately.
- Attendance is tracked for personal training sessions only. 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
