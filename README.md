# Restaurant-Management-System-SDD
Software Design Document
<Restaurant Management System (RMS) >



Submitted by
<M.Rizwan(F22BINFT1M01216)>

Submitted to
<Dr.Musarat Karim>



Department of Information Technology
Faculty of Computing
The Islamia University of Bahawalpur

Summery
The Software Design Document (SDD) for the Restaurant Management System (RMS) presents a detailed design of a desktop-based offline application developed for small to medium-sized restaurants. The document translates the requirements defined in the Software Requirements Specification (SRS) into a structured and implementable system design.
The RMS follows a layered architectural approach consisting of a presentation layer, application logic layer, data access layer, and database layer. This architecture ensures modularity, maintainability, and efficient data handling. The system includes key functional modules such as authentication, staff management, menu management, order processing, billing, customer management, and reporting.
A relational database (MySQL or SQLite) is used to store user data, menu items, customer details, orders, and sales information. The data flow design outlines how orders are processed from item selection to bill generation. The user interface is designed to be simple and user-friendly, enabling non-technical staff to operate the system efficiently.
Security features such as password-protected login and role-based access control are implemented to protect sensitive data. Error handling, performance optimization, and scalability considerations are included to ensure system reliability and future growth.

        Table of Contents
    1. Introduction
    1.1 Purpose
    1.2 Scope
    1.3 Intended Audience
    1.4 Definitions, Acronyms, and Abbreviations
    2. System Overview
    2.1 System Description
    2.2 Design Goals
    3. System Architecture
    3.1 Architectural Style
    3.2 Architecture Diagram (Textual Representation)
    4. Module Design
    4.1 Authentication Module
    4.2 Staff Management Module
    4.3 Menu Management Module
    4.4 Order Management Module
    4.5 Billing Module
    4.6 Customer Management Module
    4.7 Reporting Module
    5. Database Design
    5.1 Database Overview
    5.2 Table Descriptions
    6. Data Flow Design
    6.1 Order Processing Flow
    7. User Interface Design
    7.1 Main Screens
    7.2 UI Design Principles
    8. Security Design
    9. Error Handling and Validation
    10. Performance Considerations
    11. Maintainability and Scalability
    12. Conclusion

                             1. Introduction
1.1 Purpose
This Software Design Document (SDD) describes the architecture, design components, data structures, and interactions of the Restaurant Management System (RMS). It translates the Software Requirements Specification (SRS) into a detailed design that will guide developers during implementation and maintenance.
1.2 Scope
The RMS is a desktop-based offline application designed for small to medium-sized restaurants. It supports order management, menu management, billing, customer records, and reporting using a local database.
1.3 Intended Audience
    • Software Developers
    • System Designers
    • Project Evaluators
    • Maintenance Engineers
1.4 Definitions, Acronyms, and Abbreviations
    • RMS – Restaurant Management System
    • SRS – Software Requirements Specification
    • SDD – Software Design Document
    • GUI – Graphical User Interface
    • DB – Database

2. System Overview
2.1 System Description
The RMS is a standalone desktop application that operates without internet connectivity. It uses a graphical user interface to interact with users and a local database (MySQL or SQLite) to store all restaurant-related data.
2.2 Design Goals
    • High usability for non-technical staff
    • Fast processing of orders and billing
    • Secure access control
    • Easy maintenance and scalability

3. System Architecture
3.1 Architectural Style
The system follows a layered architecture:
    1. Presentation Layer (GUI)
    2. Application Logic Layer
    3. Data Access Layer
    4. Database Layer
3.2 Architecture Diagram (Textual Representation)
+----------------------+
| Presentation Layer |
| (Desktop GUI) |
+----------------------+
|
+----------------------+
| Application Logic |
| (Orders, Billing, |
| Reports, Validation)|
+----------------------+
|
+----------------------+
| Data Access Layer |
| (CRUD Operations) |
+----------------------+
|
+----------------------+
| Database Layer |
| (MySQL / SQLite) |
+----------------------+

4. Module Design
4.1 Authentication Module
Responsibilities:
    • Admin and staff login
    • Credential validation
    • Role-based access control
Inputs: Username, Password
Outputs: Login success/failure

4.2 Staff Management Module
Responsibilities:
    • Add, edit, delete staff accounts
    • Assign roles (Admin/Staff)
Access: Admin only

4.3 Menu Management Module
Responsibilities:
    • Add, update, delete menu items
    • Categorize items
    • Display menu for order creation
Data Used: MenuItems table

4.4 Order Management Module
Responsibilities:
    • Create customer orders
    • Add/remove multiple items
    • Calculate totals
Interactions: Menu Module, Billing Module

4.5 Billing Module
Responsibilities:
    • Calculate bill amount
    • Apply tax and discounts
    • Generate printable bills
Outputs: Invoice / Bill

4.6 Customer Management Module
Responsibilities:
    • Store customer details
    • Maintain order history
Data Used: Customers, Orders tables

4.7 Reporting Module
Responsibilities:
    • Generate daily sales reports
    • Identify best-selling items
Outputs: Tabular or printable reports

5. Database Design
5.1 Database Overview
The RMS uses a relational database (MySQL or SQLite) to store persistent data locally.
5.2 Table Descriptions
Users
    • user_id (PK)
    • username
    • password
    • role
MenuItems
    • item_id (PK)
    • name
    • category
    • price
Customers
    • customer_id (PK)
    • name
    • contact
Orders
    • order_id (PK)
    • customer_id (FK)
    • order_date
    • total_amount
OrderDetails
    • order_detail_id (PK)
    • order_id (FK)
    • item_id (FK)
    • quantity
    • price

6. Data Flow Design
6.1 Order Processing Flow
    1. Staff selects menu items
    2. System calculates subtotal
    3. Billing module applies tax/discount
    4. Order stored in database
    5. Bill generated

7. User Interface Design
7.1 Main Screens
    • Login Screen
    • Admin Dashboard
    • Staff Dashboard
    • Menu Management Screen
    • Order Creation Screen
    • Billing Screen
    • Reports Screen
7.2 UI Design Principles
    • Simple layout
    • Minimal clicks
    • Clear labels and buttons

8. Security Design
    • Password-protected login
    • Role-based access control
    • Local database security

9. Error Handling and Validation
    • Input validation for all forms
    • Error messages for invalid actions
    • System logs for critical errors

10. Performance Considerations
    • Optimized database queries
    • Lightweight GUI components
    • Fast response time (<5 seconds per operation)

11. Maintainability and Scalability
    • Modular design
    • Easy addition of new features
    • Database extensibility

12. Conclusion
This Software Design Document provides a detailed blueprint for implementing the Restaurant Management System. It ensures that the system meets the requirements specified in the SRS while maintaining high usability, reliability, and maintainability.
