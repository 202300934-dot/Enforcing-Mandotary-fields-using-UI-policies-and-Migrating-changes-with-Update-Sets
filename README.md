# Enforcing Mandatory Fields using UI Policies and Migrating Changes with Update Sets

## Project Overview

This project demonstrates how to enforce mandatory fields dynamically in the ServiceNow platform using UI Policies and migrate configuration changes across instances using Update Sets. The solution ensures that important incident information is always captured before the incident progresses in the workflow.

The implementation focuses on improving data accuracy and maintaining consistent configurations across multiple ServiceNow environments.

---

## Problem Statement

In the incident management process, users sometimes update incident records without filling important fields such as **Priority**. When the **Incident State** is changed to **In Progress**, missing priority information can cause delays in issue resolution and poor prioritization of incidents.

This project addresses the problem by enforcing the **Priority field as mandatory** whenever the **Incident State is set to "In Progress"**.

---

## Objectives

* Enforce mandatory fields using **UI Policies**
* Improve data completeness in incident records
* Demonstrate configuration management using **Update Sets**
* Show how to migrate configurations between ServiceNow instances

---

## Technologies Used

* ServiceNow Platform
* UI Policies
* UI Policy Actions
* Update Sets
* Web Browser (Chrome / Edge)

---

## Project Workflow

### 1. Create Update Set

1. Navigate to **System Update Sets → Local Update Sets**
2. Create a new Update Set
3. Set the Update Set as **Current**

### 2. Create UI Policy

1. Navigate to **System UI → UI Policies**
2. Create a new UI Policy for the **Incident table**
3. Set the condition:

   ```
   State = In Progress
   ```

### 3. Add UI Policy Action

1. Add the **Priority field**
2. Set:

   * Mandatory = True
   * Visible = True

### 4. Capture Changes in Update Set

Verify that the UI Policy and UI Policy Action are captured in the active Update Set.

### 5. Export Update Set

Export the Update Set as an **XML file**.

### 6. Import Update Set

Import the XML file into another ServiceNow instance using:

```
System Update Sets → Retrieved Update Sets
```

### 7. Commit Update Set

Preview and commit the Update Set to apply the configuration.

---

## Testing

1. Navigate to **Incident Module**
2. Open or create an incident
3. Change the **State to "In Progress"**
4. The **Priority field becomes mandatory**

---

## Results

* Mandatory field validation is enforced dynamically
* Incident records contain complete information
* Configurations can be migrated easily between instances

---

## Advantages

* No scripting required
* Easy configuration and maintenance
* Improved data quality
* Supports scalable configuration management

---

## Conclusion

This project successfully demonstrates how UI Policies can enforce business rules dynamically in ServiceNow. Using Update Sets ensures that configuration changes can be easily transferred between different ServiceNow instances, making the system more reliable and efficient.

---

