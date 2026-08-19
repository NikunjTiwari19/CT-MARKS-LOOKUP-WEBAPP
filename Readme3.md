# CT-Marks-WebApp ( CT-Plus )

A web-based system to manage, display, and analyze Class Test (CT) marks of students, with support for revaluation requests and role-based access for Students, Subject Teachers, Class Incharges, and the HOD.

---

## 1. Problem Statement

In most academic institutions, Class Test (CT) marks are managed manually or through scattered spreadsheets and notice boards. This leads to several issues:

- Students have no centralized, real-time way to view their marks.
- Students who wish to challenge their evaluated marks have no formal, trackable process for requesting revaluation.
- Subject Teachers have no structured system to update marks or manage revaluation requests efficiently.
- Class Incharges cannot easily monitor the performance of their entire class across multiple subjects.
- The HOD lacks a consolidated view of marks and activity logs across multiple classes and subjects, making performance analysis and audit difficult.

There is a need for a single, role-based web application that streamlines mark entry, viewing, revaluation, and performance analysis for all stakeholders.

---

## 2. Objective

- To design and develop a web application that digitizes the CT marks management process.
- To allow students to view their marks and raise revaluation requests online.
- To enable subject teachers to enter/edit marks and respond to revaluation notifications.
- To allow class incharges to monitor all students' marks across all subjects for their class.
- To provide the HOD with a consolidated dashboard to view marks, analyze performance across multiple classes, and track all mark-related activities.
- To automatically classify students into performance categories based on their marks.

---

## 3. Users and Their Roles

| Role | Description | Key Permissions |
|---|---|---|
| **Student** | End user whose marks are recorded | View own marks, view performance category, apply for revaluation |
| **Subject Teacher** | Faculty handling a specific subject | View/enter/edit marks for their subject, receive revaluation notifications, approve/reject revaluation, update revised marks |
| **Class Incharge** | Faculty responsible for a specific class | View marks of all students in their class, across all subjects |
| **HOD (Head of Department)** | Department head | View and analyze marks across multiple classes/subjects, view all activity logs (e.g., mark updates, revaluation actions) |

### Role Hierarchy
```
HOD
 └── Class Incharge
       └── Subject Teacher
             └── Student
```

---

## 4. Application Flow / UI Flow

### 4.1 General Flow
```
Login/Register
     │
     ▼
Role-based Dashboard Redirect
     │
     ├── Student Dashboard
     │      ├── View Marks
     │      ├── View Performance Category
     │      └── Apply for Revaluation
     │
     ├── Subject Teacher Dashboard
     │      ├── View/Enter/Edit Marks
     │      ├── Revaluation Notifications
     │      └── Approve/Reject & Update Revalued Marks
     │
     ├── Class Incharge Dashboard
     │      ├── View Class Marks (All Subjects)
     │      └── View Class Performance Summary
     │
     └── HOD Dashboard
            ├── View Marks (Multiple Classes)
            ├── Performance Analysis (Charts/Reports)
            └── Activity Log (All mark updates & revaluation actions)
```
### 4.2 Application Flow
```
                          ┌────────────────────┐
                          │      Login Page     │
                          │ (Role-based Login)   │
                          └──────────┬──────────┘
                                     │
        ┌────────────────┬──────────┼───────────────┬────────────────┐
        ▼                ▼                          ▼                ▼
   ┌─────────┐     ┌──────────────┐         ┌───────────────┐  ┌──────────┐
   │ Student │     │Subject Teacher│         │Class Incharge  │  │   HOD    │
   │Dashboard│     │  Dashboard    │         │  Dashboard     │  │Dashboard │
   └────┬────┘     └──────┬───────┘         └───────┬────────┘  └────┬─────┘
        │                 │                          │                │
        ▼                 ▼                          ▼                ▼
 View Marks by       View/Edit Marks           View all students'  View/Analyze
 Subject (%)         for own subject           marks (all subjects) marks across
        │             │                          │                  classes/subjects
        ▼             ▼                          ▼                  │
 View Performance   Receive Revaluation      Class Performance       ▼
 Category           Notifications            Summary            View Teacher
        │             │                                          Activity Log
        ▼             ▼                                              │
 Apply for         Update Marks after                                ▼
 Revaluation       Revaluation                              Generate Reports
```

## 5. Input Forms for All Users

### 5.1 Login / Registration Form
- Name
- Roll Number / Employee ID
- Email
- Password
- Role (Student / Subject Teacher / Class Incharge / HOD)
- Class / Department (as applicable)

### 5.2 Student — Revaluation Application Form
- Student Name (auto-filled)
- Roll Number (auto-filled)
- Subject
- CT Number (**CT1 and CT2** )
- Current Marks Obtained (auto-filled)
- Reason for Revaluation
- Supporting Comment (optional)
- Submit Button

### 5.3 Subject Teacher — Marks Entry / Edit Form
- Subject Name
- Class / Section
- CT Number
- Student Roll Number / Name
- Marks Obtained (out of total marks)
- Remarks (optional)
- Save / Update Button

### 5.4 Subject Teacher — Revaluation Response Form
- Request ID (auto-filled)
- Student Name (auto-filled)
- Original Marks (auto-filled)
- Revised Marks
- Decision (Approved / Rejected / No Change)
- Teacher's Remarks

### 5.5 Class Incharge — View/Filter Form
- Select Class
- Select Subject (or "All Subjects")
- Select CT Number
- Search by Roll Number / Name (optional)

### 5.6 HOD — Analysis Filter Form
- Select Department
- Select Class(es) (multi-select)
- Select Subject(s) (multi-select)
- Select CT / Date Range
- Generate Report Button

---

## 6. Performance Categorization

Based on marks obtained, students are automatically categorized:

| Percentage Range | Category |
|---|---|
| 85% and above | Excellent |
| 70% – 84% | Good |
| 50% – 69% | Average |
| Below 50% | Needs Improvement |

This ensures every student is evaluated on a common, fair scale regardless of the total marks of each individual CT.


---

## 7. Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend Logic | JavaScript |
| Database | SQL |
| Version Control | Git |
| Repository Hosting | GitHub |

---
## 8. Future Enhancements

- Email/SMS notifications for marks update and revaluation status.
- Graphical dashboards (charts) for performance trends over time.
- Export marks/reports as PDF or Excel.
- Mobile-responsive / dedicated mobile app.
- Integration with attendance and overall academic performance systems.
- Role-based two-factor authentication for security.
- Bulk marks upload via CSV/Excel for teachers.
- AI-based prediction of at-risk students based on performance trends.

---
## Team Members

1. Nikunj Tiwari
2. P. Yashwant Rao
3. Parth Gupta
4. Prakhar Singh


---
##  Conclusion

The CT Marks Web Application provides a centralized, role-based platform that simplifies mark management 
and revaluation across all levels of an academic department — from students to the HOD. It reduces manual 
effort, improves transparency, ensures accountability through activity tracking, and enables data-driven 
performance analysis. This project can serve as a scalable foundation for a full-fledged academic 
management system.

A web-based system to manage, display, and analyze Class Test (CT) marks of students, with support for revaluation requests and role-based access for Students, Subject Teachers, Class Incharges, and the HOD.

---


