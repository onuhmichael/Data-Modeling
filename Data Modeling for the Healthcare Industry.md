---

# **Data Modeling for the Healthcare Industry**

---

## **Introduction to Data Modeling**

Hey there! Ready to explore the world of data modeling within the healthcare industry? Whether you're just starting out or looking to enhance your understanding, this tutorial is crafted to guide you through the entire data modeling lifecycle using a healthcare system as our practical example. By the end, you'll grasp how to effectively model data, making complex concepts accessible and applicable to real-world healthcare scenarios.

### **What is Data Modeling?**

Think about how integral patient data is to healthcare—it's the backbone of quality care and efficient operations. Data modeling is like creating a blueprint for managing this vital information. It's the process of defining and structuring data to be stored in databases, ensuring it's organized, accessible, and meaningful. In software development and data management, especially in healthcare, data modeling is crucial for accurate patient records, regulatory compliance, and seamless interoperability between systems.

### **Key Concepts**

Let's break down some fundamental concepts that'll be our building blocks:

- **Entities**: The "things" or objects we're storing information about (e.g., Patient, Healthcare Provider, Medical Service).
- **Attributes**: Characteristics or properties of an entity (e.g., a Patient's Name, Date of Birth).
- **Relationships**: How entities are connected (e.g., Patients receive Medical Services).
- **Cardinality**: The numerical relationships between entities (one-to-one, one-to-many, many-to-many).
- **Primary Keys**: Unique identifiers for records in a table (e.g., PatientID).
- **Foreign Keys**: Fields that link one table to another, establishing relationships between entities.

### **Types of Data Models**

There are a few layers to data modeling:

1. **Conceptual Data Model**: A high-level view that outlines what data is required and how it's related—think of it as a map of concepts.
2. **Logical Data Model**: Adds detail to the conceptual model, specifying entities, attributes, and relationships without worrying about how they'll be implemented.
3. **Physical Data Model**: The logical model adapted for a specific database system, detailing tables, columns, data types, and constraints.


### Specialized Models and Approaches

**1. Relational Model & Entity–Relationship (ER) Modeling:**

- **Description**: Uses tables (relations) to organize data and employs entity–relationship diagrams to visually represent entities (objects) and their interconnections.
- **Uses**: Widely used in traditional databases for its simplicity and ease of use.
- **Azure Database**: Azure SQL Database
- **Open-Source Database**: MySQL, PostgreSQL

**Pros:**
  - **Simplicity**: Easy to understand and implement.
  - **Mature Technology**: Extensive support and tools available.
  - **Scalability**: Supports large datasets.

**Cons:**
  - **Complex Queries**: Can become cumbersome with very complex relationships.
  - **Cost**: Managed services (e.g., Azure SQL Database) can be expensive.

**Cost Factors:**
  - **Azure SQL Database**: Subscription and usage-based pricing.
  - **Open-Source**: Free, but requires self-managed infrastructure and maintenance costs.


**2. Hierarchical & Network Models:**

- **Description**: 
  - **Hierarchical Model**: Organizes data in a tree-like structure with parent-child relationships (e.g., file systems).
  - **Network Model**: Structures data as a graph with records and sets, allowing more complex relationships.
- **Uses**: Useful in specific legacy systems or specialized applications that require a rigid structure.
- **Azure Database**: Azure Cosmos DB (supports hierarchical and graph data models)
- **Open-Source Database**: Neo4j (for graph data models)

**Pros:**
  - **Efficiency**: Efficient for certain types of queries.
  - **Specialized Applications**: Tailored for specific use cases like file systems and complex relationships.

**Cons:**
  - **Rigidity**: Less flexible for evolving data structures.
  - **Complexity**: Can be harder to design and maintain.

**Cost Factors:**
  - **Azure Cosmos DB**: Pay-as-you-go pricing based on throughput and storage.
  - **Neo4j**: Free community edition, but enterprise features come with costs.


**3. Dimensional Modeling:**

- **Description**: Commonly used in data warehousing, organizes data into fact tables (quantitative data) and dimension tables (descriptive attributes). Example schemas include star schema and snowflake schema.
- **Uses**: Optimized for fast analytical querying and reporting.
- **Azure Database**: Azure Synapse Analytics
- **Open-Source Database**: Apache Hive, Apache Druid

**Pros:**
  - **Performance**: Fast query performance for analytical queries.
  - **Simplicity**: Simple and intuitive for users to understand.

**Cons:**
  - **Storage**: Can require significant storage.
  - **Cost**: Managed services can be expensive for large-scale data warehousing.

**Cost Factors:**
  - **Azure Synapse Analytics**: Pay-per-use pricing for compute and storage.
  - **Open-Source**: Free, but requires self-managed infrastructure.


**4. Object-Oriented & Object-Relational Models:**

- **Description**: Integrates programming concepts like objects, inheritance, and encapsulation into the data model.
  - **Object-Oriented Model**: Represents data as objects, similar to object-oriented programming languages.
  - **Object-Relational Model**: Extends the relational model to support complex data types and object-oriented features.
- **Uses**: Useful for applications that require tight integration between data and application logic.
- **Azure Database**: Azure SQL Database (supports object-relational features)
- **Open-Source Database**: PostgreSQL

**Pros:**
  - **Integration**: Seamless integration with object-oriented programming languages.
  - **Flexibility**: Supports complex data types and relationships.

**Cons:**
  - **Complexity**: Can be more complex to design and manage.
  - **Performance**: May have performance overhead for certain queries.

**Cost Factors:**
  - **Azure SQL Database**: Subscription and usage-based pricing.
  - **PostgreSQL**: Free, but requires self-managed infrastructure and maintenance costs.


**5. Graph Models:**

- **Description**: Represents complex relationships using nodes (entities) and edges (connections). Ideal for applications like social networks, recommendation systems, and fraud detection.
- **Uses**: Supports efficient querying of graph structures and traversal operations.
- **Azure Database**: Azure Cosmos DB (supports graph data models)
- **Open-Source Database**: Neo4j

**Pros:**
  - **Complex Relationships**: Handles complex relationships efficiently.
  - **Performance**: Fast traversal and querying of graph structures.

**Cons:**
  - **Complexity**: Can be more complex to design and understand.
  - **Cost**: Managed services can be expensive for large-scale applications.

**Cost Factors:**
  - **Azure Cosmos DB**: Pay-as-you-go pricing based on throughput and storage.
  - **Neo4j**: Free community edition, but enterprise features come with costs.

---

**6. Entity–Attribute–Value (EAV) Models:**

- **Description**: Efficient for handling sparse or highly variable data. Stores each attribute (property) as a separate row, rather than using a fixed schema with many columns.
- **Uses**: Useful in scenarios where the set of attributes can change frequently or is not well-defined.
- **Azure Database**: Azure Cosmos DB (supports flexible data models)
- **Open-Source Database**: MongoDB

**Pros:**
  - **Flexibility**: Handles varying attributes efficiently.
  - **Scalability**: Scales well with large datasets and high variability.

**Cons:**
  - **Complexity**: More complex querying and management.
  - **Performance**: May have performance overhead for certain operations.

**Cost Factors:**
  - **Azure Cosmos DB**: Pay-as-you-go pricing based on throughput and storage.
  - **MongoDB**: Free community edition, but managed services (e.g., MongoDB Atlas) have costs.


## **Requirements Gathering**

Before building our data model, we need to understand the healthcare system's needs. Let's simulate a conversation with a healthcare administrator to gather requirements.

### **Simulating a Client Interview**

*You*: "Can you share the key information your healthcare system needs to manage?"

*Administrator*: "Absolutely! We need to track patient information, healthcare providers, appointments, medical services, electronic health records, prescriptions, billing, and insurance details. We also need to ensure compliance with healthcare regulations and maintain data security."

### **Identifying Key Data Elements and Business Rules**

From our conversation, we've identified the following key components:

- **Patient Details**:
  - *Demographics*: First Name, Last Name, Date of Birth, Gender, Address, Contact Information.
  - *Insurance Information*: Insurance Provider, Policy Number.
  - *Medical History*: Allergies, Chronic Conditions, Past Procedures.

- **Healthcare Providers**:
  - *Providers*: Provider ID, Name, Specialty, Contact Information.
  - *Types*: Doctors, Nurses, Specialists, Therapists.

- **Appointments**:
  - Appointment Date and Time, Patient, Provider, Reason for Visit, Status.

- **Medical Services**:
  - Services Offered, Service Codes, Descriptions, Costs.

- **Electronic Health Records (EHR)**:
  - Patient Notes, Test Results, Imaging Reports, Visit Summaries.

- **Prescriptions**:
  - Medication Name, Dosage, Frequency, Prescribing Provider, Pharmacy Details.

- **Billing and Insurance**:
  - Charges, Payments, Insurance Claims, Billing Dates, Payment Status.

- **Regulatory Compliance**:
  - Data Security Measures, Audit Trails, Consent Forms.

---

## **Conceptual Data Model**

Now that we know what data we need, let's start crafting our conceptual data model.

### **Identifying Entities and Relationships**

**Entities**:

1. **Patient**
2. **HealthcareProvider**
3. **Appointment**
4. **MedicalService**
5. **EHR**
6. **Prescription**
7. **Billing**
8. **Insurance**
9. **ComplianceRecord**

**Relationships**:

- A **Patient** can have multiple **Appointments**.
- An **Appointment** is associated with one **Patient** and one **HealthcareProvider**.
- **HealthcareProviders** offer **MedicalServices**.
- **EHR** entries are created for each **Appointment**.
- **Prescriptions** are written by **HealthcareProviders** for **Patients**.
- **Billing** records are generated for **Appointments** and linked to **Patients** and **Insurance**.
- **ComplianceRecords** are associated with **Patients** and **Appointments**.

### **Creating the ER Diagram**

<img width="485" alt="image" src="https://github.com/user-attachments/assets/05e2ac5e-6f73-48aa-b72f-be9ba1d8e506" />


- **Patient** — (books) — **Appointment** — (with) — **HealthcareProvider**
- **Appointment** — (includes) — **MedicalService**
- **Patient** — (has) — **EHR**
- **HealthcareProvider** — (prescribes) — **Prescription**

## **Logical Data Model**

Let's add more detail to our model, defining attributes and refining relationships.

### **Defining Entities with Attributes**

#### **Patient**

- **PatientID** *(Primary Key)*
- FirstName
- LastName
- DateOfBirth
- Gender
- Address
- PhoneNumber
- Email
- InsuranceID *(Foreign Key)*
- EmergencyContact

#### **HealthcareProvider**

- **ProviderID** *(Primary Key)*
- FirstName
- LastName
- Specialty
- PhoneNumber
- Email
- ProviderType

#### **Appointment**

- **AppointmentID** *(Primary Key)*
- PatientID *(Foreign Key)*
- ProviderID *(Foreign Key)*
- AppointmentDate
- AppointmentTime
- ReasonForVisit
- Status

#### **MedicalService**

- **ServiceID** *(Primary Key)*
- ServiceCode
- Description
- Cost

#### **EHR**

- **RecordID** *(Primary Key)*
- PatientID *(Foreign Key)*
- AppointmentID *(Foreign Key)*
- Notes
- TestResults
- ImagingReports
- RecordDate

#### **Prescription**

- **PrescriptionID** *(Primary Key)*
- PatientID *(Foreign Key)*
- ProviderID *(Foreign Key)*
- MedicationName
- Dosage
- Frequency
- StartDate
- EndDate
- PharmacyDetails

#### **Billing**

- **BillingID** *(Primary Key)*
- PatientID *(Foreign Key)*
- AppointmentID *(Foreign Key)*
- TotalAmount
- PaymentStatus
- BillingDate
- InsuranceClaimStatus

#### **Insurance**

- **InsuranceID** *(Primary Key)*
- InsuranceProvider
- PolicyNumber
- CoverageDetails
- ContactInformation

#### **ComplianceRecord**

- **ComplianceID** *(Primary Key)*
- PatientID *(Foreign Key)*
- AppointmentID *(Foreign Key)*
- ConsentFormsSigned
- PrivacyAcknowledgment
- RecordDate

### **Normalization Principles (Up to 3NF)**

Our design should follow normalization principles to ensure efficient data storage and integrity.

- **First Normal Form (1NF)**: Ensure all attributes are atomic—no repeating groups or arrays.
- **Second Normal Form (2NF)**: All non-key attributes are fully dependent on the primary key.
- **Third Normal Form (3NF)**: No transitive dependencies; non-key attributes depend only on the primary key.

### **Resolving Many-to-Many Relationships**

A **HealthcareProvider** can offer multiple **MedicalServices**, and a **MedicalService** can be offered by multiple **HealthcareProviders**.

To handle this, we'll create a junction table:

#### **ProviderService**

- **ProviderID** *(Foreign Key)*
- **ServiceID** *(Foreign Key)*
- **EffectiveDate**
- **EndDate**

This table records which providers offer which services and during what periods.

---

## **Physical Data Model**

Now, let's translate our logical model into a physical one using **PostgreSQL**.

### **Database Schema Creation**

#### **SQL Scripts to Create Tables**

```sql
-- Patients Table
CREATE TABLE Patient (
    PatientID SERIAL PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    DateOfBirth DATE NOT NULL,
    Gender VARCHAR(10),
    Address TEXT,
    PhoneNumber VARCHAR(15),
    Email VARCHAR(100),
    InsuranceID INT REFERENCES Insurance(InsuranceID),
    EmergencyContact VARCHAR(100)
);

-- Healthcare Providers Table
CREATE TABLE HealthcareProvider (
    ProviderID SERIAL PRIMARY KEY,
    FirstName VARCHAR(50) NOT NULL,
    LastName VARCHAR(50) NOT NULL,
    Specialty VARCHAR(100),
    PhoneNumber VARCHAR(15),
    Email VARCHAR(100),
    ProviderType VARCHAR(50)
);

-- Appointments Table
CREATE TABLE Appointment (
    AppointmentID SERIAL PRIMARY KEY,
    PatientID INT NOT NULL REFERENCES Patient(PatientID),
    ProviderID INT NOT NULL REFERENCES HealthcareProvider(ProviderID),
    AppointmentDate DATE NOT NULL,
    AppointmentTime TIME NOT NULL,
    ReasonForVisit TEXT,
    Status VARCHAR(20)
);

-- Medical Services Table
CREATE TABLE MedicalService (
    ServiceID SERIAL PRIMARY KEY,
    ServiceCode VARCHAR(20) NOT NULL,
    Description TEXT,
    Cost DECIMAL(10,2)
);

-- Electronic Health Records Table
CREATE TABLE EHR (
    RecordID SERIAL PRIMARY KEY,
    PatientID INT NOT NULL REFERENCES Patient(PatientID),
    AppointmentID INT NOT NULL REFERENCES Appointment(AppointmentID),
    Notes TEXT,
    TestResults TEXT,
    ImagingReports TEXT,
    RecordDate DATE NOT NULL
);

-- Prescriptions Table
CREATE TABLE Prescription (
    PrescriptionID SERIAL PRIMARY KEY,
    PatientID INT NOT NULL REFERENCES Patient(PatientID),
    ProviderID INT NOT NULL REFERENCES HealthcareProvider(ProviderID),
    MedicationName VARCHAR(100) NOT NULL,
    Dosage VARCHAR(50),
    Frequency VARCHAR(50),
    StartDate DATE,
    EndDate DATE,
    PharmacyDetails TEXT
);

-- Billings Table
CREATE TABLE Billing (
    BillingID SERIAL PRIMARY KEY,
    PatientID INT NOT NULL REFERENCES Patient(PatientID),
    AppointmentID INT NOT NULL REFERENCES Appointment(AppointmentID),
    TotalAmount DECIMAL(10,2),
    PaymentStatus VARCHAR(20),
    BillingDate DATE,
    InsuranceClaimStatus VARCHAR(20)
);

-- Insurance Table
CREATE TABLE Insurance (
    InsuranceID SERIAL PRIMARY KEY,
    InsuranceProvider VARCHAR(100) NOT NULL,
    PolicyNumber VARCHAR(50),
    CoverageDetails TEXT,
    ContactInformation TEXT
);

-- Compliance Records Table
CREATE TABLE ComplianceRecord (
    ComplianceID SERIAL PRIMARY KEY,
    PatientID INT NOT NULL REFERENCES Patient(PatientID),
    AppointmentID INT NOT NULL REFERENCES Appointment(AppointmentID),
    ConsentFormsSigned BOOLEAN,
    PrivacyAcknowledgment BOOLEAN,
    RecordDate DATE NOT NULL
);

-- ProviderService Junction Table
CREATE TABLE ProviderService (
    ProviderID INT NOT NULL REFERENCES HealthcareProvider(ProviderID),
    ServiceID INT NOT NULL REFERENCES MedicalService(ServiceID),
    EffectiveDate DATE,
    EndDate DATE,
    PRIMARY KEY (ProviderID, ServiceID)
);
```

---

## **Implementation and Testing**

Let's populate our database with some sample data and run queries to test our model.

### **Inserting Sample Data**

#### **Adding Patients**

```sql
INSERT INTO Patient (FirstName, LastName, DateOfBirth, Gender, Address, PhoneNumber, Email, InsuranceID, EmergencyContact)
VALUES
('Olivia', 'Taylor', '1987-03-22', 'Female', '123 Health Way', '555-0100', 'olivia.taylor@example.com', 1, 'John Taylor - 555-0200'),
('Liam', 'Johnson', '1992-11-05', 'Male', '456 Wellness Rd', '555-0300', 'liam.johnson@example.com', 2, 'Emma Johnson - 555-0400');
```

#### **Adding Healthcare Providers**

```sql
INSERT INTO HealthcareProvider (FirstName, LastName, Specialty, PhoneNumber, Email, ProviderType)
VALUES
('Sophia', 'Brown', 'Family Medicine', '555-0500', 'sophia.brown@healthcare.com', 'Doctor'),
('Mason', 'Davis', 'Physiotherapy', '555-0600', 'mason.davis@healthcare.com', 'Therapist');
```

#### **Adding Insurance Records**

```sql
INSERT INTO Insurance (InsuranceProvider, PolicyNumber, CoverageDetails, ContactInformation)
VALUES
('HealthyLife Insurance', 'HL123456', 'Comprehensive Coverage', 'contact@healthylife.com, 555-0700'),
('WellCare Insurance', 'WC789012', 'Standard Coverage', 'support@wellcare.com, 555-0800');
```

#### **Adding Appointments**

```sql
INSERT INTO Appointment (PatientID, ProviderID, AppointmentDate, AppointmentTime, ReasonForVisit, Status)
VALUES
(1, 1, '2025-05-10', '09:30', 'Annual Checkup', 'Scheduled'),
(2, 2, '2025-05-11', '11:00', 'Back Pain Consultation', 'Scheduled');
```

#### **Adding Medical Services**

```sql
INSERT INTO MedicalService (ServiceCode, Description, Cost)
VALUES
('FM101', 'General Consultation', 150.00),
('PT202', 'Physiotherapy Session', 100.00);
```

#### **Adding ProviderService Records**

```sql
INSERT INTO ProviderService (ProviderID, ServiceID, EffectiveDate)
VALUES
(1, 1, '2024-01-01'),
(2, 2, '2024-01-01');
```

#### **Adding EHR Records**

```sql
INSERT INTO EHR (PatientID, AppointmentID, Notes, RecordDate)
VALUES
(1, 1, 'Patient in good health. Recommended annual screening.', '2025-05-10'),
(2, 2, 'Patient reports back pain. Suggested exercise regimen.', '2025-05-11');
```

#### **Adding Prescriptions**

```sql
INSERT INTO Prescription (PatientID, ProviderID, MedicationName, Dosage, Frequency, StartDate)
VALUES
(2, 2, 'Ibuprofen', '200 mg', 'Twice a day', '2025-05-11');
```

#### **Adding Billing Records**

```sql
INSERT INTO Billing (PatientID, AppointmentID, TotalAmount, PaymentStatus, BillingDate, InsuranceClaimStatus)
VALUES
(1, 1, 150.00, 'Paid', '2025-05-10', 'Approved'),
(2, 2, 100.00, 'Pending', '2025-05-11', 'Submitted');
```

#### **Adding Compliance Records**

```sql
INSERT INTO ComplianceRecord (PatientID, AppointmentID, ConsentFormsSigned, PrivacyAcknowledgment, RecordDate)
VALUES
(1, 1, TRUE, TRUE, '2025-05-10'),
(2, 2, TRUE, TRUE, '2025-05-11');
```

### **Demonstration Queries**

#### **1. Find All Appointments for a Specific Patient**

```sql
SELECT a.AppointmentDate,
       a.AppointmentTime,
       hp.FirstName || ' ' || hp.LastName AS ProviderName,
       a.ReasonForVisit
FROM Appointment a
JOIN HealthcareProvider hp ON a.ProviderID = hp.ProviderID
WHERE a.PatientID = 1;
```

*Result*:

| AppointmentDate | AppointmentTime | ProviderName  | ReasonForVisit  |
|-----------------|-----------------|---------------|-----------------|
| 2025-05-10      | 09:30           | Sophia Brown  | Annual Checkup  |

#### **2. List All Medical Services Offered by a Provider**

```sql
SELECT ms.ServiceCode,
       ms.Description,
       ms.Cost
FROM MedicalService ms
JOIN ProviderService ps ON ms.ServiceID = ps.ServiceID
WHERE ps.ProviderID = 1;
```

*Result*:

| ServiceCode | Description          | Cost    |
|-------------|----------------------|---------|
| FM101       | General Consultation | 150.00 |

#### **3. Retrieve EHR Notes for a Patient's Appointment**

```sql
SELECT e.RecordDate,
       e.Notes
FROM EHR e
WHERE e.PatientID = 2 AND e.AppointmentID = 2;
```

*Result*:

| RecordDate | Notes                                           |
|------------|-------------------------------------------------|
| 2025-05-11 | Patient reports back pain. Suggested exercises. |

---

## **Advanced Topics**

Let's delve into additional concepts that enhance our data model's utility and robustness.

### **Data Warehousing and Analytics**

A data warehouse stores historical data from various sources, enabling analysis and reporting.

- **Use Case**: Analyzing patient visit patterns to improve healthcare services.
- **Benefits**: Better resource allocation, improved patient care strategies.

### **Performance Optimization Techniques**

#### **Indexing**

Creating indexes on frequently searched columns speeds up query execution.

```sql
CREATE INDEX idx_patient_lastname ON Patient(LastName);
CREATE INDEX idx_appointment_date ON Appointment(AppointmentDate);
```

#### **Query Optimization**

Efficient queries reduce database load.

- **Use EXPLAIN**: Analyze query execution plans.
- **Specific Selects**: Retrieve only necessary columns.
- **Avoid Unnecessary Joins**: Simplify where possible.

### **Data Governance and Security Considerations**

#### **Access Control**

Implement role-based access to protect sensitive information.

- **Roles**: Administrator, Provider, Receptionist, Billing Specialist.
- **Permissions**: Define CRUD operations for each role.

#### **Encryption**

Protect data at rest and in transit.

- **TLS/SSL**: Secure database connections.
- **Data Encryption**: Encrypt sensitive fields like medical records.

#### **Compliance**

Ensure adherence to regulations like **HIPAA** (Health Insurance Portability and Accountability Act).

- **Audit Trails**: Log data access and changes.
- **Consent Management**: Track patient consent for data usage.
- **Data Anonymization**: When using data for research or analytics.

---

## **Conclusion & Next Steps**

You've journeyed through the entire data modeling lifecycle for a healthcare system. From grasping foundational concepts to implementing and querying a functional database, you've built a solid foundation to continue your exploration in data modeling.

### **Key Takeaways**

- **Data Modeling**: Essential for structuring healthcare data efficiently.
- **Normalization**: Maintains database integrity and reduces redundancy.
- **Practical Application**: Translating complex healthcare requirements into a workable database schema.

### **Where to Go From Here**

- **Practice**: Try modeling data for other complex systems like insurance or pharmaceuticals.
- **Expand Your Skills**: Look into data integration, interoperability standards (like HL7 FHIR), and advanced database management.
- **Stay Informed**: Healthcare technology evolves quickly; keep learning and adapting.

---

## **Quiz & Exercises**

Test your understanding and reinforce your learning with these exercises.

### **Exercise 1: Identifying Entities for Telehealth Services**

*Task*: Define entities and relationships for integrating telehealth services, including virtual appointments, digital prescriptions, and remote monitoring.

**Consider**:

- **Entities**: VirtualAppointment, DigitalPrescription, RemoteMonitoring, Device.
- **Relationships**:
  - A **Patient** can have multiple **VirtualAppointments**.
  - **HealthcareProviders** can issue **DigitalPrescriptions**.
  - **Patients** can use **Devices** for **RemoteMonitoring**.

### **Exercise 2: SQL Query Challenge**

*Task*: Write an SQL query to find all prescriptions prescribed by a specific provider within the last month.

**Hint**:

- Use JOIN to connect **Prescription** and **HealthcareProvider** tables.
- Filter by **ProviderID** and prescription **StartDate**.

**Example SQL**:

```sql
SELECT p.PrescriptionID,
       p.MedicationName,
       p.Dosage,
       p.PatientID,
       p.StartDate
FROM Prescription p
JOIN HealthcareProvider hp ON p.ProviderID = hp.ProviderID
WHERE hp.FirstName = 'Sophia' AND hp.LastName = 'Brown'
  AND p.StartDate BETWEEN CURRENT_DATE - INTERVAL '1 month' AND CURRENT_DATE;
```

### **Exercise 3: Data Normalization Practice**

*Task*: Normalize the following unstructured data into at least 2NF.

**Unstructured Data**:

| PatientName   | ProviderName  | AppointmentDate | ServiceDescription | InsuranceProvider   | PolicyNumber |
|---------------|---------------|-----------------|--------------------|---------------------|--------------|
| Olivia Taylor | Sophia Brown  | 2025-05-10      | General Consultation| HealthyLife Insurance | HL123456     |
| Liam Johnson  | Mason Davis   | 2025-05-11      | Physiotherapy Session| WellCare Insurance    | WC789012     |

**Steps**:

1. **First Normal Form (1NF)**:
   - Ensure atomic values.
2. **Second Normal Form (2NF)**:
   - Remove partial dependencies.
   - Separate into multiple tables:
     - **Patient** (PatientID, PatientName, InsuranceID)
     - **HealthcareProvider** (ProviderID, ProviderName)
     - **Appointment** (AppointmentID, PatientID, ProviderID, AppointmentDate)
     - **MedicalService** (ServiceID, ServiceDescription)
     - **Insurance** (InsuranceID, InsuranceProvider, PolicyNumber)

---

**Keep exploring and pushing your boundaries—data modeling is a powerful skill that'll open up endless possibilities in the tech and healthcare worlds!**

---

