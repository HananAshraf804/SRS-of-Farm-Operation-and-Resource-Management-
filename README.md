. Introduction
1.1 Purpose
The purpose of this SRS document is to define the functional and non-functional requirements of the Farm Operation and Resource Management System. The system aims to simplify and digitize daily farm operations, resource tracking, machinery management, and staff activity logs. It will be used by farm operators, supervisors, and administrators.
1.2 Scope
This web-based system will:
Record daily farm activities (seeding, spraying, fertilizing, irrigatin, harvesting, etc.)
Track machinery, bikes, workers, and store inventory
Allow offline access and storage using Local Storage
Provide an Urdu interface for on-field staff
Generate daily/weekly reports
Allow data backup through JSON export/import
The system runs locally in the browser and requires no server or internet connection.
1.3 Definitions
Local Storage: Browser-based offline data storage
JSON: Lightweight data interchange format
Operator: Person who enters daily operational data
Supervisor: Person responsible for supervising workers, bikes, and field activities
Admin: Full-access user who manages and views all system data
1.4 Overview
This document describes system modules, user roles, functional/non-functional requirements, design constraints, and system models needed to develop the Farm Operation and Resource Management System.
2. Overall Description
2.1 Product Perspective
The system is standalone and runs entirely offline. It functions as a digital logbook for farm operations and resource management. No backend, server, or cloud service is used; all data is stored in the user's browser.
2.2 Product Features
Field and crop management
Machinery and bike management
Worker and operator activity tracking
Stock management
Training/video repository
Reporting system
JSON data export/import
Urdu interface support
2.3 User Classes and Characteristics
Admin
Full system access
Can view, edit, delete, export, and import all records
Supervisor
Manages bikes, videos, and operational monitoring
Limited editing permissions
Operator
Performs daily data entry for fields, machinery, and resources
2.4 Operating Environment
Runs on: Chrome, Firefox, Edge
Platform: Desktop and Mobile
No internet required
Technologies: HTML, CSS, JavaScript (Vanilla), Local Storage
2.5 Design & Implementation Constraints
Storage limited to Local Storage capacity (~5–10 MB depending on browser)
No server or cloud backup within system (must use export/import)
Performance depends on browser
No real-time multi-user access
2.6 Assumptions and Dependencies
User will use the same device unless exporting/importing data
Browser supports Local Storage
Urdu font rendering is supported
3. Specific Requirements
3.1 Functional Requirements
A. Field / Crop Module
FR-1: The system shall allow adding new fields with crop information.
FR-2: The system shall record seed, pesticide, fertilizer quantities.
FR-3: The system shall store sowing and harvesting dates.
FR-4: The system shall allow updating and deleting field records.
B. Machinery Module
FR-5: The system shall store machinery details (tractor, bike, etc.).
FR-6: The system shall record machinery status (Working/Repairing).
FR-7: The system shall record fuel usage and maintenance notes.
FR-8: The system shall assign operators to machinery.
C. Workers & Operators
FR-9: The system shall store worker information.
FR-10: The system shall record daily worker tasks and hours.
FR-11: The system shall track resource usage by workers.
D. Bikes / Transport
FR-12: The system shall record bike model, number, and condition.
FR-13: The system shall assign bikes to supervisors.
E. Videos & Training Material
FR-14: The system shall allow adding video links or local references.
FR-15: The system shall categorize videos by purpose (training/report).
FR-16: The system shall associate videos with officers/supervisors.
F. Stock Management
FR-17: The system shall maintain stock of store items (seeds, sprays, fertilizers).
FR-18: The system shall record daily usage and update stock levels.
FR-19: The system shall show low-stock alerts.
G. Reporting
FR-20: The system shall generate daily/weekly summaries.
FR-21: The system shall support JSON export and import.
FR-22: The system may support CSV/print reports.
H. Urdu Interfac
FR-23: The system shall support Urdu language and RTL design.
3.2 Non-Functional Requirements
3.2.1 Performance
System shall load within 3 seconds.
Local Storage operations shall execute instantly for typical data sizes.
3.2.2 Security
System shall store data locally without external access.
Role-based access (Admin/Supervisor/Operator) shall be supported.
3.2.3 Usability
Mobile-friendly UI
Easy search/filtering options
Clear and simple forms
3.2.4 Reliability
Must work offline at all times
Data export/import ensures backup reliability
3.2.5 Maintainability
Well-structured HTML/CSS/JS files
Code documented with comments
Modular functions for easy updates
4. System Models
4.1 Use Case Diagram
(If needed, I can generate the diagram image.)
Actors:
Admin
Supervisor
Operator
Use Cases:
.Manage Fields
.Manage Machinery
.Manage Workers
.Manage Stock
.View Reports
.Export/Import Data
.Manage Videos
4.2 Data Flow Diagram (DFD)
Levels:
.DFD 0: Farm Management System
.DFD 1: Field Management, Machinery, Workers, Stock, Reports
(You can request diagrams and I’ll generate them.)
4.3 Entity Relationship Diagram (ERD)
Entities:
. Field
. Machinery
. Worker
. Bike
. Video
. Stock Item
. Report
Relationships:
Field → Worker
Worker → Tasks
Machinery → Operator
Bike → Supervisor
5. Appendices
5.1 Sample JSON Structure (Local Storage Format)
{
  "fields": [],
  "machinery": [],
  "workers": [],
  "bikes": [],
  "videos": [],
  "stock": []
}
5.2 Future Enhancements
Use IndexedDB for larger data storage
Add user login system
Add charts (production trends, usage stats)
Image upload for field photos
Convert to PWA for improved offline capability
