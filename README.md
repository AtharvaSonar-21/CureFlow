# CureFlow 🏥
> **Enterprise Clinical Operations & Hospital ERP Platform**

[![Project Status: Under Active Development](https://img.shields.io/badge/Status-Under_Development-orange.svg)]()
[![Java](https://img.shields.io/badge/Java-17-blue.svg)]()
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.4-brightgreen.svg)]()
[![React](https://img.shields.io/badge/React-18-blue.svg)]()
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue.svg)]()
[![MySQL](https://img.shields.io/badge/MySQL-8.0-orange.svg)]()
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-CSS-38B2AC.svg)]()


CuraFlow is a full-stack hospital management platform designed to bring common clinical, administrative, and operational workflows into a single system.

The project is being developed to provide role-based access to hospital staff such as administrators, doctors, nurses, pharmacists, and patients while maintaining centralized and structured medical and operational data.

The main goal of CuraFlow is to build a practical enterprise-style application using **Java, Spring Boot, React, and MySQL**, with a focus on backend development, security, database design, and real-world business workflows.

---

## 🎯 Project Goals

- Build a modular hospital management platform.
- Develop a secure REST API using Spring Boot.
- Implement authentication and role-based authorization.
- Design and manage relational healthcare data using MySQL.
- Handle real-world workflows such as appointments, medical records, inventory, and billing.
- Practice clean backend architecture and transaction management.
- Provide a responsive web interface for different hospital users.

---

# 👥 User Roles

CuraFlow will support different users with different permissions.

### Hospital Administrator

- Manage hospital departments
- Manage doctors and staff
- Manage patients
- Monitor hospital operations
- Manage rooms and beds
- View operational reports

### Doctor

- View assigned appointments
- Manage consultations
- View patient medical history
- Record diagnoses
- Add prescriptions
- View patient vitals and reports

### Staff / Nurse

- Manage assigned patients
- Record patient vitals
- Assist with appointments and admissions
- Update relevant patient information

### Pharmacist

- Manage medicines
- Monitor inventory
- Track medicine batches and expiry dates
- Process medicine orders

### Patient

- Manage personal profile
- View appointments
- View medical records
- View prescriptions
- View diagnostic reports

---

# 🧩 Core Modules

CuraFlow will be developed as several interconnected modules.

## 1. Authentication & Access Control

The system will provide secure authentication and authorization.

Planned features:

- User registration and login
- JWT-based authentication
- Spring Security integration
- Role-Based Access Control (RBAC)
- Protected REST APIs
- Password hashing
- Role-specific permissions

---

## 2. Patient Management

This module will manage patient information throughout their interaction with the hospital.

Planned features:

- Patient registration
- Patient profiles
- Contact information
- Medical history
- Allergies
- Emergency contact information
- Patient search
- Patient status

---

## 3. Doctor & Staff Management

This module will help administrators manage hospital employees.

Planned features:

- Doctor profiles
- Staff profiles
- Department assignment
- Doctor specialization
- Availability management
- Staff scheduling
- Role assignment

---

## 4. Appointment & Scheduling

The appointment module will manage doctor availability and patient appointments.

Planned features:

- Appointment booking
- Doctor availability
- Appointment status
- Appointment rescheduling
- Appointment cancellation
- Prevention of conflicting appointments
- OPD scheduling

Example appointment states:

```text
SCHEDULED
CONFIRMED
COMPLETED
CANCELLED
NO_SHOW
````

---

## 5. Electronic Medical Records

The EMR module will maintain structured patient medical information.

Planned features:

* Consultation records
* Diagnoses
* Medical history
* Prescriptions
* Lab reports
* Patient vitals
* Previous consultations

Medical records will be associated with the relevant patient and healthcare professional.

---

## 6. Vitals & Clinical Tracking

This module will allow authorized healthcare staff to record patient vitals.

Planned parameters include:

* Blood pressure
* Heart rate
* Blood glucose
* Body temperature
* Oxygen saturation
* Weight

The system will maintain timestamped records so that changes can be viewed over time.

---

## 7. Pharmacy & Inventory

The pharmacy module will manage medicines and stock.

Planned features:

* Medicine catalogue
* Stock management
* Batch tracking
* Expiry date tracking
* Low-stock alerts
* Medicine issue records
* Inventory history

---

## 8. Blood Bank

The blood bank module will manage available blood components.

Planned features:

* Blood group records
* Blood component inventory
* Donor records
* Blood unit availability
* Blood issue records
* Expiry tracking

---

## 9. Hospital Equipment

This module will track hospital equipment and its allocation.

Planned features:

* Equipment registration
* Equipment categories
* Department allocation
* Availability status
* Maintenance records
* Equipment history

---

## 10. Billing & Invoicing

The billing module will manage patient-related charges.

Planned features:

* Consultation charges
* Diagnostic charges
* Medicine charges
* Room/bed charges
* Procedure charges
* Itemized invoices
* Payment status
* Invoice generation

Example payment states:

```text
PENDING
PARTIALLY_PAID
PAID
CANCELLED
```

---

## 11. Dashboard & Reporting

The system will provide dashboards based on user roles.

Possible metrics include:

* Total patients
* Today's appointments
* Available beds
* Doctor availability
* Pharmacy stock alerts
* Pending payments
* Hospital revenue
* Department statistics

---

# 🏗️ System Architecture

The application will follow a client-server architecture.

```text
                    ┌─────────────────────────┐
                    │     React Frontend      │
                    │                         │
                    │ React + TypeScript      │
                    │ Redux Toolkit           │
                    │ Tailwind CSS            │
                    └────────────┬────────────┘
                                 │
                            REST API
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │    Spring Boot API      │
                    │                         │
                    │ Controllers             │
                    │ Services                │
                    │ Repositories            │
                    │ Security                │
                    │ DTOs                    │
                    └────────────┬────────────┘
                                 │
                          JPA / Hibernate
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │        MySQL            │
                    │                         │
                    │ Users                   │
                    │ Patients                │
                    │ Doctors                 │
                    │ Appointments            │
                    │ Medical Records         │
                    │ Inventory               │
                    │ Billing                 │
                    └─────────────────────────┘
```

---

# 🛠️ Technology Stack

## Frontend

* React
* TypeScript
* Tailwind CSS
* Redux Toolkit
* React Router
* Axios

## Backend

* Java 17
* Spring Boot 3
* Spring MVC
* Spring Security
* Spring Data JPA
* Hibernate
* Maven

## Database

* MySQL 8

## Authentication

* JWT
* Spring Security
* BCrypt password hashing
* Role-Based Access Control

## Development Tools

* Git
* GitHub
* Postman
* IntelliJ IDEA
* VS Code
* MySQL Workbench

---

# 🔐 Security Design

Security will be an important part of the project.

Planned security features:

* JWT-based authentication
* Password hashing using BCrypt
* Role-based authorization
* Protected REST endpoints
* Input validation
* Global exception handling
* Authentication failure handling
* Authorization checks for sensitive resources

Example:

```java
@PreAuthorize("hasRole('DOCTOR')")
```

will be used where appropriate to restrict access to doctor-specific operations.

---

# 🗄️ Planned Database Model

The initial database will contain entities such as:

```text
User
Role
Department
Doctor
Staff
Patient
Appointment
MedicalRecord
Vital
Prescription
LabReport
Medicine
Inventory
BloodBank
Equipment
Invoice
Payment
```

Relationships will be designed using JPA/Hibernate.

For example:

```text
Patient
   │
   ├── Appointments
   ├── Medical Records
   ├── Vitals
   ├── Prescriptions
   ├── Lab Reports
   └── Invoices

Doctor
   │
   ├── Appointments
   └── Medical Records

Department
   │
   ├── Doctors
   └── Staff
```

---

# 📁 Planned Project Structure

```text
CuraFlow/
│
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/curaflow/
│   │   │   │       ├── config/
│   │   │   │       ├── controller/
│   │   │   │       ├── dto/
│   │   │   │       ├── entity/
│   │   │   │       ├── exception/
│   │   │   │       ├── repository/
│   │   │   │       ├── security/
│   │   │   │       └── service/
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   └── test/
│   ├── pom.xml
│   └── mvnw.cmd
│
├── frontend/
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── store/
│   │   ├── types/
│   │   └── utils/
│   ├── index.html
│   ├── package.json
│   ├── tsconfig.json
│   └── vite.config.ts
│
├── docs/
│   └── architecture.md
├── .gitignore
└── README.md
```

> 📘 **Full Architecture Specification**: Detailed system blueprints, security flow, UI design tokens, and database patterns are documented in [docs/architecture.md](docs/architecture.md).

---

# 🚀 Incremental Milestone Roadmap

CuraFlow is engineered incrementally following strict software engineering practices. Each milestone is runnable, verifiable, and Git-committable.

- [x] **1. Repository and project initialization**
- [x] **2. Spring Boot backend setup**
- [ ] **3. React + TypeScript frontend setup**
- [ ] **4. MySQL and JPA configuration**
- [ ] **5. Base backend architecture and exception handling**
- [ ] **6. User and role entities**
- [ ] **7. User registration**
- [ ] **8. JWT authentication**
- [ ] **9. Role-based authorization**
- [ ] **10. Frontend authentication and protected routes**
- [ ] **11. Department management**
- [ ] **12. Doctor management**
- [ ] **13. Staff management**
- [ ] **14. Patient management**
- [ ] **15. Appointment scheduling and availability**
- [ ] **16. Medical records**
- [ ] **17. Patient vitals**
- [ ] **18. Prescriptions and laboratory reports**
- [ ] **19. Pharmacy and inventory**
- [ ] **20. Blood bank**
- [ ] **21. Hospital equipment**
- [ ] **22. Rooms and beds**
- [ ] **23. Billing and payments**
- [ ] **24. OpenAPI/Swagger documentation**
- [ ] **25. Frontend application shell**
- [ ] **26. Admin dashboard**
- [ ] **27. Doctor dashboard**
- [ ] **28. Staff dashboard**
- [ ] **29. Pharmacist dashboard**
- [ ] **30. Patient dashboard**
- [ ] **31. Frontend CRUD/API integration**
- [ ] **32. Backend and integration testing**
- [ ] **33. Security hardening**
- [ ] **34. Dockerization**
- [ ] **35. GitHub Actions CI/CD**
- [ ] **36. Final documentation and deployment preparation**

### Optional Extensions
- [ ] **Kafka Notification System** (Appointment, billing, health events)
- [ ] **WebSocket Real-time Chat** (Patient-staff communication)

---

# 🧪 Testing Strategy

The project will include testing at different levels.

### Unit Testing

JUnit and Mockito will be used to test service-layer business logic.

### Integration Testing

Spring Boot integration tests will be used to test interactions between application components and the database.

### API Testing

Postman will be used to test REST API endpoints and authentication flows.

---

# 📚 Learning Objectives

Through CuraFlow, the main learning objectives are:

* Build REST APIs using Spring Boot
* Understand Spring Security and JWT
* Design relational databases
* Work with JPA and Hibernate
* Implement transactional business operations
* Build a layered backend architecture
* Understand authentication and authorization
* Connect a React frontend with a Spring Boot backend
* Write unit and integration tests
* Deploy a full-stack application

---

# 📌 Current Status

CuraFlow is currently in the **planning and initial development stage**.

The features and architecture described in this README represent the intended scope of the project. Features will be marked as completed as they are implemented and tested.

---

# 🔮 Future Scope

Future versions may include:

* Redis caching
* Asynchronous processing
* Notification services
* Email/SMS integration
* Advanced audit logging
* Dockerized deployment
* Cloud deployment
* CI/CD pipeline
* Advanced analytics
* API documentation
* Monitoring and observability

---

# 📄 License

This project will be released under the MIT License.

