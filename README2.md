
### 1. Problem Statement :-

In educational institutions, Class Test (CT) marks of students are often recorded and managed manually using notebooks, spreadsheets, or separate files. This traditional approach can make it difficult for faculty members to efficiently enter, update, organize, and retrieve students' marks. It may also lead to errors, duplication of data, loss of records, and difficulty in maintaining marks for different classes, subjects, and examinations.

The aim of this project is to develop a web-based CT-Marks Management System that minimizes manual data entry and simplifies the process of collecting, storing, verifying, and managing students' Class Test (CT) marks. The system will provide faculty with efficient methods such as Excel/CSV upload, automated data extraction, and marksheet scanning using OCR, reducing the need to enter marks individually.

-----------------------------------------------------------------------

### 2. Users and their Roles :-

We will give a total of four logins which are as follows-

### Student Access -

Students should have mostly read-only access. Student can,
Login using Student ID/Roll Number.
View their CT marks.
View marks for different subjects and CTs.
View total/average CT marks.
View their performance history.
Download/view their marks report.
Raise a query if they believe a mark is incorrect.

### Faculty Access -

Faculty will be responsible for entering and maintaining marks. Faculty can,
Login to their faculty dashboard.
See their assigned subjects/classes.
Upload/scan a physical marksheet using OCR.
Manually correct extracted marks.
Add/update CT marks.
View student-wise and class-wise marks.
Respond to student queries.
Submit/finalize marks for HOD verification.

### HOD Access -

The HOD should act s the supervisor between faculty and the institute.
The HOD doesn't necessarily enter marks themselves. Instead, they monitor, approve, and communicate with faculty. HOD can,
View all faculty under their department.
View CT submission status.
Review uploaded marks.
Approve submitted marks.
Reject marks if errors are found.
Send the submission back to faculty for correction.
Lock/finalize approved marks.
View class-wise and subject-wise performance.
Communicate with faculty regarding pending or incorrect submissions.


### Institute/Admin Access -

The Institute/Admin should have the highest-Level access.
The institute primarily manages the entire system and academic structure. Admins can,
Create/manage departments.
Create/manage HOD accounts.
Create/manage faculty accounts.
Create/manage student accounts.
Assign faculty to subjects/classes.
Assign HODs to departments.
View all departments.
View all CT records.
Manage user permissions.

-----------------------------------------------------------------------

### 3. Flow of UI :-
```text
                                      ┌─────────────┐
                                      │    LOGIN    │
                                      └──────┬──────┘
                                             │
          ┌──────────────────────────────────┼────────────────────────────────────────────────────────────────────┐
          │                                  │                                  │                                 │
          ▼                                  ▼                                  ▼                                 ▼
   ┌─────────────┐                    ┌─────────────┐                    ┌─────────────┐                    ┌─────────────┐
   │   STUDENT   │                    │   FACULTY   │                    │     HOD     │                    │    ADMIN    │
   └──────┬──────┘                    └──────┬──────┘                    └──────┬──────┘                    └──────┬──────┘
          │                                  │                                  │                                  │
          ▼                                  ▼                                  ▼                                  ▼
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐
│ Student Dashboard │              │ Faculty Dashboard │              │   HOD Dashboard   │              │  Admin Dashboard  │
└─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘
          │                                  │                                  │                                  │
          ▼                                  ▼                                  ▼                                  ▼
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐
│ View Academic     │              │ My Classes /      │              │ View Assigned     │              │ Manage            │
│ Details           │              │ My Subjects       │              │ Faculty           │              │ Departments       │
└─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘
          │                                  │                                  │                                  │
          ▼                                  ▼                                  ▼                                  ▼
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐
│ Select Subject    │              │ Select CT         │              │ Monitor CT-Marks  │              │ Manage HOD,       │
│                   │              │                   │              │ Submission        │              │ Faculty & Student │
└─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘              │ Accounts          │
          │                                  │                                  │                        └─────────┬─────────┘
          ▼                                  ▼                                  ▼                                  │
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐                        ▼
│ View CT Marks     │              │ Upload Excel      │              │ Review Submitted  │              ┌───────────────────┐
│                   │              │ Sheet             │              │ Marks             │              │ Assign Faculty    │
└─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘
          │                                  │                                  │                                  │
          ▼                                  ▼                                  ▼                                  ▼
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐
│ View Performance  │              │ Automatic Student │              │ Approve / Request │              │ Monitor CT-Marks  │
│                   │              │ Matching          │              │ Correction        │              │                   │
└─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘              └─────────┬─────────┘
          │                                  │                                  │                                  │
          ▼                                  ▼                                  ▼                                  ▼
┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐              ┌───────────────────┐
│ Raise Query       │              │ Validation        │              │ Communicate with  │              │ View Reports      │
│                   │              │                   │              │ Faculty           │              │                   │
└───────────────────┘              └─────────┬─────────┘              └───────────────────┘              └─────────┬─────────┘
                                             │                                                                     │
                                             ▼                                                                     ▼
                                   ┌───────────────────┐                                                    ┌───────────────────┐
                                   │ Preview           │                                                    │ Manage System     │
                                   └─────────┬─────────┘                                                    └───────────────────┘
                                             │
                                             ▼
                                   ┌───────────────────┐
                                   │ Confirm & Submit  │
                                   └─────────┬─────────┘
                                             │
                                             ▼
                                   ┌───────────────────┐
                                   │ HOD Verification  │
                                   └───────────────────┘
```
-----------------------------------------------------------------------
### 4] USER INPUTS

### STUDENT INPUT

Student ID / Roll Number, Password, Subject Selection, CT Selection, Query/Complain
  
### FACULTY INPUT

Faculty ID / Email, Password, CT Selection, Excel/CSV Upload, Marksheet Scan/Image, Corrections Remarks   

### HOD INPUT

HOD ID / Email, Password, Faculty/Subject/CT Selection, Approval/Rejection, Correction Request, Remarks  

### ADMIN INPUT

Admin ID / Email, Password, Department Details, HOD Details, Faculty Details, Student Details, Class/ Section, Subject Details, Faculty Assignments, Academic Session, User Permissions |


### 5] APPLICATION OF THIS WEBAPP

The system can be used by faculty to upload CT marks through Excel/CSV files or scanned marksheets, allowing the application to automatically extract and match student information. HODs can use the system to monitor submissions, verify marks, request corrections, and approve finalized records. Students can access their approved CT marks and performance reports, while the institute administration can manage users, departments, subjects, classes, and academic records.

-----------------------------------------------------------------------
