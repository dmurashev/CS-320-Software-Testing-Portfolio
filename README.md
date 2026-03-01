# CS-320 Software Testing Portfolio (Java + JUnit 5)

This repository contains three simple in-memory backend services for a mobile application (no database, no UI):

- **Contact Service**
- **Task Service**
- **Appointment Service**

Each service includes a domain model with strict field validation and a corresponding service class that supports controlled **add**, **delete**, and **update** operations by ID.

The repository also includes the **Project Two Summary and Reflections Report** documenting testing strategy and professional growth.

---

## Contact Service

Implements a validation-focused contact management component.

### Features
- Add contacts with a **unique contact ID**
- Delete contacts by **contact ID**
- Update contact fields by **contact ID**:
    - `firstName`
    - `lastName`
    - `phone`
    - `address`
- Full **JUnit 5** unit test coverage for validation and service behavior

### Validation Rules (Contact)
- `contactId`: required, max 10 characters, not updatable
- `firstName`: required, max 10 characters
- `lastName`: required, max 10 characters
- `phone`: required, exactly 10 digits
- `address`: required, max 30 characters

---

## Task Service

Implements task tracking with strict validation rules.

### Features
- Add tasks with a **unique task ID**
- Delete tasks by **task ID**
- Update task fields by **task ID**:
    - `name`
    - `description`
- Full **JUnit 5** unit test coverage

### Validation Rules (Task)
- `taskId`: required, max 10 characters, not updatable
- `name`: required, max 20 characters
- `description`: required, max 50 characters

---

## Appointment Service

Implements appointment scheduling with time-based validation.

### Features
- Add appointments with a **unique appointment ID**
- Delete appointments by **appointment ID**
- Validation enforced on creation
- Full **JUnit 5** unit test coverage

### Validation Rules (Appointment)
- `appointmentId`: required, max 10 characters, not updatable
- `appointmentDate`: required, must not be in the past
- `description`: required, max 50 characters

---

## Error Handling

Each domain uses structured runtime exceptions:

- `ValidationException`
- `DuplicateIdException`
- `NotFoundException`

These ensure:
- Required fields are not null
- Field lengths do not exceed limits
- IDs remain unique
- Dates meet logical constraints
- Invalid operations fail predictably

---

## Testing Strategy

Testing was requirement-driven and focused on correctness and robustness.

- **Boundary value analysis**
- **Negative testing**
- Duplicate ID validation
- Exception verification using `assertThrows()`
- Positive path verification using `assertEquals()`
- Branch coverage validation

The project achieves **80%+ test coverage**, with strong emphasis on validation-heavy code paths.

---

## Tech Stack
- Java
- JUnit 5
- IntelliJ IDEA

---

## Files

### Contact Service
- `Contact.java`
- `ContactService.java`
- `ContactTest.java`
- `ContactServiceTest.java`

### Task Service
- `Task.java`
- `TaskService.java`
- `TaskTest.java`
- `TaskServiceTest.java`

### Appointment Service
- `Appointment.java`
- `AppointmentService.java`
- `AppointmentTest.java`
- `AppointmentServiceTest.java`

### Project Two
- `CS320_ProjectTwo_Summary_and_Reflections.docx`

---

## Reflection

### How can I ensure that my code, program, or software is functional and secure?

I ensure functionality and security by translating documented requirements directly into validation logic and corresponding unit tests. Every constraint—such as maximum field lengths, immutable identifiers, uniqueness enforcement, and future-date validation—was implemented as explicit rules and verified through automated tests.

By applying boundary value analysis and negative testing, I confirm that valid input is accepted and invalid input is rejected safely. Testing both success and failure paths reduces regression risk and increases reliability.

---

### How do I interpret user needs and incorporate them into a program?

I interpret user needs by converting written specifications into enforceable constraints within the domain model. Each requirement becomes both a validation rule and a test case. This requirement-to-test traceability ensures that all documented constraints are implemented precisely and verified systematically.

---

### How do I approach designing software?

I approach software design with structured layering and disciplined validation:

- Define constraints clearly at the model level
- Separate domain models from service logic
- Enforce immutability where system integrity requires it
- Design components to be easily unit tested

Even in a simple in-memory architecture, I apply production-oriented discipline: strict validation, controlled exception handling, and systematic automated testing.
