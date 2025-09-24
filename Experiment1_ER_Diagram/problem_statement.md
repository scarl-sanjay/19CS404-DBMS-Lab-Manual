# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
Hospital

## ER Diagram:
![Screenshot 2025-03-18 132715](https://github.com/user-attachments/assets/2e95a8aa-e080-4548-b6b1-5ba0cfed752f)


## Entities and Attributes:
1. Patient

Attributes: Patient Id (PK), Full Name, DOB, Address, Phone, Gender

2. Doctor

Attributes: Doctor Id (PK), Full Name, Specialization, Phone

3. Appointment

Attributes: Id (PK), Doctor Name, Patient Name, Appointment Date and Time

4. Department

Attributes: Department Id (PK), Department Name, Department Head

5. Medical Record

Attributes: Patient ID (FK), Doctor ID (FK), Medications, Treatments, Diagnosis, Results

6. Billing (Extension)

Attributes: Id (PK), Patient ID (FK), Amount, Status

## Relationships
1. Patient – Appointment

Relationship: A patient can have multiple appointments with doctors.

Type: 1:N (One patient → many appointments)

2. Doctor – Appointment

Relationship: A doctor can have multiple appointments.

Type: 1:N

3. Doctor – Department

Relationship: A department has multiple doctors.

Type: 1:N

4. Medical Record – Patient & Doctor

Relationship: A medical record is associated with both a patient and a doctor.

Type: M:N → Broken into two 1:N relationships via foreign keys.

5. Billing – Patient

Relationship: A patient can have multiple billing records.

Type: 1:N

## Constraints 
1. Primary Keys (PK):

* Uniquely identify each record (e.g., Patient Id, Doctor Id, Appointment Id).

2. Foreign Keys (FK):

* Ensure referential integrity.

-> Billing.PatientID → Patient.PatientID

-> MedicalRecord.PatientID → Patient.PatientID

-> MedicalRecord.DoctorID → Doctor.DoctorID

3. 1:N and M:N constraints

* Defined by cardinalities (e.g., 1 doctor can belong to 1 department but a department can have many doctors).

## Extension (Billing):
Billing is an added entity that stores financial details related to the patient. This is an extension because it’s optional in basic healthcare systems but important for more comprehensive systems (e.g., hospital ERP).

-> Links to Patient via PatientID

-> Allows tracking of payments (Amount) and Status (Paid/Pending/etc.)



## Design Choices:
1. Normalization:

* Each entity is well-separated to avoid data redundancy (e.g., Patient info not repeated in appointments).

2. Clarity and Maintainability:

* Medical records, billing, and appointments are modular for ease of update and clarity.

3. Extensibility:

* Easily extendable to include insurance, lab results, prescriptions, etc.

4. Data Integrity:

* Use of foreign keys ensures relational integrity between entities like Patient, Doctor, and Department.

5. Scalability:

* The design supports future expansion like adding multiple hospital branches or integrating external systems (e.g., lab, pharmacy).

## RESULT
Thus the ER diagram for the university database is successfully developed.
