# ⭐ Day 6 – Triggers & SOQL

## 📘 What is SOQL?

SOQL (Salesforce Object Query Language) is used to retrieve data from Salesforce objects such as Account, Contact, Lead, and Opportunity. It works similarly to SQL but is specially designed for Salesforce. Developers use SOQL in Apex classes, triggers, APIs, and the Developer Console to search, filter, and display records from the Salesforce database.

### Example
```sql
SELECT Id, Name FROM Contact
```

---

## ⚡ What is an Apex Trigger?

An Apex Trigger is a piece of Apex code that executes automatically when records are inserted, updated, deleted, or undeleted in Salesforce. Triggers help automate business operations and ensure that actions happen immediately when data changes occur.

### Example
```apex
trigger ContactTrigger on Contact (before insert) {
    for(Contact c : Trigger.new){
        c.Description = 'New Customer Added';
    }
}
```

---

## 🔄 Difference Between Flow and Trigger

| Flow | Trigger |
|---|---|
| No-code or low-code automation | Code-based automation |
| Easy for admins to build | Used mainly by developers |
| Best for simple business logic | Best for complex logic |
| Slower in large operations | Better performance for bulk operations |
| Uses drag-and-drop interface | Uses Apex programming language |

### Summary
Flows are user-friendly automation tools, while triggers provide advanced customization and control for enterprise-level requirements.

---

## 🔁 Difference Between Before Trigger and After Trigger

| Before Trigger | After Trigger |
|---|---|
| Executes before saving record | Executes after saving record |
| Used for validations and updating fields | Used for related records and notifications |
| Faster because changes happen before save | Useful when record ID is required |
| Modifies record values directly | Performs actions after database commit |

### Example
- Before Trigger → Validate or update fields before save.
- After Trigger → Create related tasks after save.

---

## 💡 Trigger Use Cases

### 1. Automatic Follow-Up Task
Create a task automatically when an Opportunity is marked as Closed Won.

### 2. Duplicate Contact Prevention
Prevent inserting contacts with duplicate email addresses.

### 3. Auto Update Customer Status
Automatically update customer status when records change.

### 4. Parent Record Update
Update Account information when related Contacts are modified.

### 5. Validation of Business Rules
Stop records from saving if important business conditions are not met.

---

## 🔍 Query Examples (English Query Ideas)

### Retrieve all contacts with last name Smith
```sql
SELECT Id, Name FROM Contact WHERE LastName = 'Smith'
```

### Find all opportunities with Closed Won stage
```sql
SELECT Id, Name FROM Opportunity WHERE StageName = 'Closed Won'
```

### Get all leads created today
```sql
SELECT Id, Name FROM Lead WHERE CreatedDate = TODAY
```

---

## 🧠 Reflection – Why Enterprise Systems React Automatically to Data Changes

Enterprise systems manage large amounts of data every day, so manual monitoring is not practical. Automatic reactions help organizations improve efficiency, reduce human errors, and maintain accurate business operations. Using triggers and automation tools, systems can instantly validate records, create tasks, update related information, and notify users whenever data changes occur. This makes enterprise applications faster, smarter, and more reliable.
