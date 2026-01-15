# Mock-Business-Requirements-Document-BRD-
The purpose of this document is to define the business requirements for implementing a patient queue management system at City Health Clinic. The system will streamline patient check‑in, prioritize returning patients, provide staff with real‑time visibility into the queue, and support SMS notifications to improve communication and reduce wait times.

# Business Requirements Document (BRD)
**Project Name:**  City Health Clinic BRD

**Version:** 1.0  
**Author:**  Kaleb B

**Date:**  1/10/26

---
## 🧭 Workflow Diagrams Summary – City Health Clinic Queue System

This repository includes three cross-functional workflow diagrams created as part of a simulated Systems Analyst project for a patient queue management system at **City Health Clinic**. These diagrams support the Business Requirements Document (BRD) and demonstrate workflow mapping, process analysis, and cross-functional system understanding.

---

### 📌 1. Patient Check-In Workflow  
**Diagram:** [](./diagrams/pt_check_in.png)

This diagram illustrates the end-to-end process a patient follows when checking in at the clinic. It uses swimlanes to clearly separate responsibilities across system actors.

**Key elements include:**
- Patient arrival and kiosk interaction  
- Service type selection (New, Returning, Prescription Pickup)  
- Optional phone number capture for SMS notifications  
- Queue entry creation and prioritization  
- Timestamp logging  
- Confirmation messaging  

**Supported BRD Requirements:**  
- Functional Requirements: **FR‑1**, **FR‑2**, **FR‑3**  
- Objectives: **O1**, **O2**, **O3**

---

### 📌 2. SMS Notification Workflow  
**Diagram:** [View SMS Notification Workflow](./diagrams/sms-notification-workflow.png)

This workflow shows how the queue system triggers and sends SMS notifications to patients based on their position in the queue or staff actions.

**Key elements include:**
- Queue system monitoring patient position  
- Decision logic for notification thresholds  
- SMS gateway sending messages  
- Patient receiving notifications  
- Optional second notification when staff update status  

**Supported BRD Requirements:**  
- Functional Requirements: **FR‑4**, **FR‑5**  
- Objectives: **O1**, **O4**

---

### 📌 3. Staff Queue Management Workflow  
**Diagram:** [View Staff Queue Management Workflow](./diagrams/staff-queue-management-workflow.png)

This workflow outlines how clinic staff interact with the queue system to manage patient flow and update statuses.

**Key elements include:**
- Staff dashboard login  
- Queue visibility and filtering  
- Decision logic for calling the next patient  
- Status updates (Waiting → Called → In Room → Completed)  
- System-driven tracking of queue changes  

**Supported BRD Requirements:**  
- Functional Requirements: **FR‑3**, **FR‑5**  
- Objectives: **O3**, **O4**

---

### 🎯 Purpose of These Diagrams

These workflow diagrams were created to:

- Validate business requirements with stakeholders  
- Support system configuration planning  
- Provide visual documentation for developers, QA, and project managers  
- Demonstrate Systems Analyst competencies in:  
  - Workflow mapping  
  - Requirements translation  
  - Cross-functional analysis  
  - Process optimization  


---
## 1. Purpose
The purpose of this document is to define the business requirements for implementing a patient queue management system at City Health Clinic. The system will streamline patient check‑in, prioritize returning patients, provide staff with real‑time visibility into the queue, and support SMS notifications to improve communication and reduce perceived wait times. This document serves as the primary reference for stakeholders, project managers, and implementation teams to ensure a shared understanding of the solution's desired outcomes, scope, and constraints. 

---

## 2. Background / Problem Statement
City Health Clinic currently manages patient flow using a manual, first‑come, first‑served process at the front desk. Patients check in verbally with staff, and staff maintain an informal list of who is waiting and for what service.
This approach leads to:
•	Limited visibility into queue order and wait times
•	No prioritization for returning patients
•	Inconsistent communication with patients about delays
•	No structured data for reporting or process improvement
The clinic requires a more structured, transparent, and data‑driven approach to managing patient queues.


---

## 3. Objectives and Success Criteria

### **Objectives**
- O1: [Objective 1]  Reduce perceived wait times and improve patient experience through clear communication and queue transparency. 
- O2: [Objective 2]  Ensure returning patients are prioritized in the queue according to clinic policy. 
- O3: [Objective 3]  Provide staff with a real-time view of patient queues by service type. 
- O4: [Objective 4]  Capture timestamped data for check-in and status changes to support reporting and process optimization. 
- O5: [Objective 5] Enable SMS notifications for key events (e.g., “You’re next,” “Please proceed to Room 3”).

### **Success Criteria**
- S1: [Measurable success criterion]  Staff can view and manage the queue from a centralized dashboard. 
- S2: [Measurable success criterion]  Returning patients are consistently placed ahead of new patients when arrival times are similar. 
- S3: [Measurable success criterion]  At least 95% of check-ins are recorded with timestamps and service type. 
- S4: [Measurable success criterion]  SMS notifications are successfully sent for at least 90% of configured events during pilot. 
- S5: [Measurable success criterion]  Staff report improved visibility and reduced confusion in post-implementation feedback.  

---

## 4. Scope

### **4.1 In Scope**
•	Implementation of a digital queue management system for patient check-in at City Health Clinic.

•	Support for three service types:
    o	New Patient
    o	Returning Patient
    o	Prescription Pickup
    
•	Configuration of a kiosk-based check-in interface for patients.

•	Configuration of a staff dashboard to view and manage the queue.

•	Implementation of prioritization rules to favor returning patients over new patients, where applicable.

•	Capture of check-in timestamps and status changes for reporting.

•	Configuration of SMS notifications for key queue events.

•	Basic training and documentation for clinic staff on using the system.


### **4.2 Out of Scope**
•	Integration with the clinic’s Electronic Health Record (EHR) system.

•	Online appointment scheduling or pre‑check‑in via web or mobile app.

•	Payment processing or billing workflows.

•	Advanced analytics dashboards beyond basic queue and wait time reporting.

•	Multi‑site deployment (this project is limited to a single clinic location).


---

## 5. Stakeholders
•	**Project Sponsor**: Clinic Director – accountable for overall success and funding.

•	**Primary Business Owner**: Front Desk / Reception Manager – responsible for day to day queue operations.

•	**End Users – Staff:**
      o	Front desk staff
      o	Nurses / medical assistants
      o	Clinic manager
      
•	**End Users – Patients:**
      o	New patients
      o	Returning patients
      o	Prescription pickup visitors
      
•	**Technical Stakeholders:**
      o	Systems Analyst / Configuration Specialist
      o	Implementation Project Manager
      o	Vendor Support / Product Team (for the queue system)
      
•	**Compliance / Security**:
      o	Data protection / privacy officer (if applicable)
 

---

## 6. Current State (As‑Is)
•	Patients arrive at the clinic and approach the front desk.

•	Front desk staff ask the reason for visit and manually note the patient’s name and purpose.

•	Patients wait in the lobby until their name is called verbally.

•	There is no formal prioritization for returning patients or prescription pickups.

•	Staff have limited visibility into how many patients are waiting for each type of service.

•	No structured data is captured for wait times, arrival patterns, or service demand.


---

## 7. Future State (To‑Be)
•	Patients arrive and check in using a kiosk at the clinic entrance.

•	Patients select their service type: New Patient, Returning Patient, or Prescription Pickup.

•	The system assigns them a place in the queue based on service type and prioritization rules.

•	Staff view a real‑time dashboard showing all waiting patients, their service type, and status.

•	Returning patients are prioritized over new patients when appropriate, according to configured rules.

•	The system records check‑in time and status changes for each patient.

•	SMS notifications are sent to patients at key points (e.g., when they are near the front of the queue or when it’s their turn).

•	Staff can update patient status (e.g., “Waiting,” “In Room,” “Completed”) from the dashboard.


---

## 8. Functional Requirements

### **FR‑1: Patient check‑in via kiosk**
- FR‑1.1:  The system shall provide a kiosk interface for patients to check in upon arrival.
- FR‑1.2:  The kiosk shall allow patients to select one of the following service types: New Patient, Returning Patient, Prescription Pickup.
- FR‑1.3:  The kiosk shall capture basic identifying information (e.g., name or ticket number, depending on privacy policy).

### **FR‑2: Queue management and prioritization**
- FR‑2.1:  The system shall create a queue entry for each patient upon successful check‑in.
- FR‑2.2:  The system shall assign queue order based on arrival time and service type.
- FR‑2.3:  The system shall prioritize Returning Patient entries over New Patient entries when arrival times are similar, according to configurable rules.
- FR-2.4:  The system shall support separate views or filters by service type.

### **FR‑3: Staff dashboard**
- FR‑3.1:  The system shall provide a staff dashboard displaying all active queue entries.
- FR‑3.2:  The dashboard shall display at minimum: patient identifier, service type, check‑in time, and current status.
- FR‑3.3:  Staff shall be able to update patient status (e.g., Waiting, Called, In Room, Completed).

### **FR‑4: SMS notifications**
- FR-4.1:  The system shall support sending SMS notifications to patients who provide a valid phone number.
- FR-4.2:  The system shall support at least the following notification events:
                o	Patient is near the front of the queue
                o	Patient is called to a room or station
- FR-4.3:  Notification content shall be configurable within predefined templates.

### **FR‑5: Data capture and reporting**
- FR-5.1:  The system shall record check‑in timestamps for all patients.
- FR-5.2:  The system shall record status change timestamps (e.g., when a patient is called or completed).
- FR-5.3:  The system shall store data in a format that supports basic reporting on wait times and volume by service type.

### **FR‑6: Administration and configuration**
- FR-6.1:  Authorized users shall be able to configure service types and prioritization rules.
- FR-6.2:  Authorized users shall be able to enable/disable SMS notifications.
- FR-6.3:  Authorized users shall be able to manage user access to the staff dashboard.

---

## 9. Non‑Functional Requirements (NFRs)

### **Performance**
- NFR‑1.1:  The kiosk interface shall respond to user input within 2 seconds under normal operating conditions.
- NFR‑1.2:  The staff dashboard shall refresh queue data at least every 10 seconds.

### **Availability**
- NFR‑2.1:  The system shall be available during clinic operating hours, with planned maintenance scheduled outside those hours whenever possible.

### **Usability**
- NFR‑3.1:  The kiosk interface shall be designed for ease of use, with clear labels and minimal steps.
- NFR‑3.2:  The staff dashboard shall present information in a clear, readable format suitable for quick decision‑making.

### **Security & Compliance**
- NFR‑4.1:  The system shall comply with applicable data protection and privacy regulations (e.g., HIPAA, if applicable).
- NFR‑4.2:  Access to the staff dashboard shall require authenticated login.
- NFR-4.3:  Patient data shall be stored and transmitted securely using industry‑standard encryption where applicable.

### **Maintainability**
- NFR‑5.1:  Configuration changes (e.g., service types, prioritization rules) shall be possible without code changes.
- NFR‑5.2:  System configuration shall be documented to support future updates and troubleshooting.

---

## 10. Assumptions and Constraints

### **Assumptions**
- A1:  A kiosk device (or tablet) will be available at the clinic entrance for patient use.
- A2:  Patients will be willing and able to use the kiosk for check‑in with minimal assistance.
- A3:  The clinic has reliable internet connectivity to support the cloud‑based queue system.
- A4:  SMS delivery depends on patients providing valid phone numbers and carrier availability.

### **Constraints**
- C1:  The solution must operate within the capabilities of the selected queue management product; custom development is limited or not available.
- C2:  Budget and timeline are constrained to a single‑location implementation.
- C3:  Integration with existing EHR systems is not part of this phase.

---

## 11. High‑Level Workflows (Textual)

### **WF‑1: Patient check‑in workflow (high level)**
1.  Patient arrives at clinic.
2.  Patient approaches kiosk.
3.  Patient selects service type (New, Returning, Pickup).
4.  Patient provides required information (e.g., name or ticket, phone number for SMS).
5.  System creates queue entry and displays confirmation

### **WF‑2: Staff queue management workflow**
1.  Staff log into the staff dashboard.
2.  Staff view current queue by service type and status.
3.  Staff call next patient based on queue order and prioritization rules.
4.  Staff update patient status (e.g., Called, In Room, Completed)

### **WF‑3: Notification workflow**
1.  System monitors queue position for each patient.
2.  When a patient reaches a configured threshold (e.g., next in line), system triggers SMS notification.
3.  When staff update status to “Called” or equivalent, system may trigger another SMS if configured.


---

## 12. Acceptance Criteria
- AC‑1:  Patients can successfully check in via kiosk for all three service types without staff intervention in at least 90% of cases during pilot.
- AC‑2:  Staff can view all active patients in a single dashboard, with correct service type and check‑in time displayed.
- AC‑3:  Returning patients are prioritized over new patients according to the configured rules in at least 95% of observed cases.
- AC‑4:  SMS notifications are sent for configured events and received by patients in at least 90% of test cases.
- AC-5:  Basic reports or exports show check‑in timestamps and status changes for all patients during a given day.
- AC-6:  Staff confirm in a post‑implementation review that the system improves visibility and reduces confusion compared to the previous manual process.

---

## 13. Out of Scope / Future Enhancements
The following items are not included in the current project but may be considered for future phases:

•	Online appointment scheduling integrated with the queue system.

•	Integration with the clinic’s EHR to pre‑populate patient data.

•	Multi‑location queue management and centralized reporting.

•	Advanced analytics dashboards for long‑term trend analysis.


---


