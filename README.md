# Contact Service (Java + JUnit 5)

This project implements a simple in-memory **Contact Service** for a mobile application (no database, no UI).

It includes a `Contact` model with strict field validation and a `ContactService` class that supports **add**, **delete**, and **update** operations by contact ID.

This repository also includes the **Project Two Summary and Reflections Report**, which documents my testing strategy and professional growth in software testing and quality assurance.

---

## Features
- Add contacts with a **unique contact ID**
- Delete contacts by **contact ID**
- Update contact fields by **contact ID**:
    - `firstName`
    - `lastName`
    - `phone`
    - `address`
- Full **JUnit 5** unit test coverage for validation and service behavior

---

## Validation Rules (Contact)
- `contactId`: required, max 10 characters, not updatable
- `firstName`: required, max 10 characters
- `lastName`: required, max 10 characters
- `phone`: required, exactly 10 digits
- `address`: required, max 30 characters

---

## Error Handling
The service uses structured runtime exceptions to ensure predictable system behavior:

- `ValidationException`
- `DuplicateIdException`
- `NotFoundException`

These exceptions are thrown when:
- Required fields are null or invalid
- Field lengths exceed defined limits
- Duplicate IDs are added
- Delete or update operations target non-existing records

---

## Testing Strategy
Testing was requirement-driven and focused on correctness and robustness.

- **Boundary value analysis**
- **Negative testing**
- Duplicate ID validation
- Exception verification using `assertThrows()`
- Positive path verification using `assertEquals()`
- Branch coverage validation

The project achieves **80%+ unit test coverage**, with strong emphasis on validation logic and defensive programming.

---

## Tech Stack
- Java
- JUnit 5
- IntelliJ IDEA

---

## Files
- `Contact.java`
- `ContactService.java`
- `ContactTest.java`
- `ContactServiceTest.java`
- `CS320_ProjectTwo_Summary_and_Reflections.docx`

---

# Reflection

## How can I ensure that my code, program, or software is functional and secure?

I ensure functionality and security by translating documented requirements directly into validation logic and corresponding unit tests. Every constraint—such as maximum field lengths, immutable identifiers, and uniqueness enforcement—was implemented as explicit validation rules and verified through automated testing.

By applying boundary value analysis and negative testing, I confirm that valid input is accepted and invalid input is rejected safely. Testing both success and failure paths reduces regression risk and increases long-term reliability.

---

## How do I interpret user needs and incorporate them into a program?

I interpret user needs by converting written specifications into enforceable validation logic within the domain model. Each requirement becomes both a rule in the code and a test case verifying compliance. This requirement-to-test traceability ensures that all documented constraints are implemented precisely and systematically verified.

---

## How do I approach designing software?

I approach software design with structured layering and disciplined validation:

- Define constraints clearly at the model level
- Separate domain models from service logic
- Enforce immutability where system integrity requires it
- Design components to be easily unit tested

Even in a simple in-memory architecture, I apply production-oriented discipline: strict validation, controlled exception handling, and systematic automated testing to ensure reliable behavior.
