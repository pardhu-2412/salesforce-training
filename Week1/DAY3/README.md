# 🎓 Day 3 – Data Modeling in Salesforce

# 📌 1. Difference Between App, Object, Record, and Field

| Term | Meaning | Example |
|------|----------|----------|
| App | Collection of related features and objects | College Management App |
| Object | Table used to store data | Student Object |
| Record | Single row of data inside object | One student details |
| Field | Stores specific information | Name, Age |

### Simple Explanation

- App organizes the complete system.
- Object stores similar type of data.
- Record represents one entry.
- Field stores individual information.

---

# 📘 2. Standard vs Custom Objects

| Standard Objects | Custom Objects |
|------------------|----------------|
| Already available in Salesforce | Created by users |
| Example: Account, Contact | Example: Student, Course |
| Used for common business needs | Used for project requirements |
| Limited customization | Fully customizable |

✅ Simple Explanation

- Standard objects are provided by Salesforce.
- Custom objects are created based on project needs.

---

# 🏗️ 3. College Data Model

## 📦 Objects

1. Student  
2. Faculty  
3. Course  
4. Department  

---

## 🔗 Relationships

| Relationship | Type |
|--------------|------|
| Student → Course | Many Students belong to one Course |
| Faculty → Department | Many Faculties belong to one Department |
| Course → Department | Many Courses belong to one Department |

---

# 🧮 4. Formula Fields

## ✅ Formula Field 1 – Full Name

Object:
Student

Formula
First_Name__c & " " & Last_Name__c

## ✅ Formula Field 2 – Remaining Seats

Object:
Course

Formula
Total_Seats__c - Filled_Seats__c

## ✅ Formula Field 3 – Percentage

Object:
Student

Formula
(Marks_Obtained__c / Total_Marks__c) * 100

---

# 🔒 5. Validation Rules

## ✅ Validation Rule 1 – Email Cannot Be Empty

Formula
ISBLANK(Email)

## ✅ Validation Rule 2 – Age Cannot Be Negative

Formula
Age__c < 0

## ✅ Validation Rule 3 – Filled Seats Cannot Exceed Total Seats

Formula
Filled_Seats__c > Total_Seats__c

---

💡 6. Reflection — Why Structured Enterprise Data Matters

Structured enterprise data helps organizations store and manage information in a clear and organized way. Systems like Salesforce connect related data using objects and relationships, making it easier to search, analyze, and generate reports.

Structured data reduces duplication, improves accuracy, increases security, and supports automation. Unlike random spreadsheets, enterprise systems provide better collaboration, faster decision-making, and scalable business operations.
