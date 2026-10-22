
# Software Requirements Specification

## Project Title
Design and Development of a Privacy-Aware QR/NFC-Based Emergency Medical Information System

## 1. Project Overview
The project aims to develop a privacy-aware web-based platform that enables rapid access to user-authorized emergency medical information through QR codes and NFC identification cards.

## 2. Problem Statement
During emergencies, individuals may be unconscious or unable to communicate essential medical information. This can make it difficult for responders to identify known allergies, relevant medical conditions, and emergency contacts.

The proposed system aims to improve access to this information while protecting sensitive personal data.

## 3. Project Objectives
- Develop a responsive web application.
- Implement user registration and authentication.
- Enable users to create and manage emergency medical profiles.
- Generate unique QR/NFC identifiers.
- Provide controlled access to emergency information.
- Implement privacy settings and access control.
- Provide emergency contact information.
- Integrate authoritative first-aid information resources.

## 4. Functional Requirements

FR-01: The system shall support user registration and login.

FR-02: Users shall be able to create and update their personal profiles.

FR-03: Users shall be able to manage relevant medical information, including known allergies, medications, and medical conditions.

FR-04: Users shall be able to add emergency contacts.

FR-05: The system shall generate unique emergency profile identifiers for QR/NFC access.

FR-06: Scanning a QR code or tapping a compatible NFC card shall open the corresponding emergency profile.

FR-07: Users shall be able to configure which information is publicly accessible.

FR-08: The system shall restrict access to private medical information.

FR-09: The emergency profile shall provide access to emergency calling functionality.

FR-10: The system shall provide links to authoritative first-aid guidance.

FR-11: Users shall be able to deactivate or replace their emergency identifiers.

## 5. Non-Functional Requirements

NFR-01: The interface shall support mobile devices.

NFR-02: The system shall use HTTPS for secure communication.

NFR-03: Private medical information shall require authorization.

NFR-04: The interface shall be understandable and accessible during emergencies.

NFR-05: The system shall handle invalid or revoked identifiers safely.

NFR-06: The system shall follow data minimization principles.

NFR-07: The application shall provide clear error messages when information is unavailable.

## 6. Technology Stack

### Frontend
- TypeScript
- React
- Next.js
- Tailwind CSS

### Backend
- Java
- Spring Boot
- Spring Security
- Spring Data JPA / Hibernate

### Database
- PostgreSQL

### Design and Testing
- Figma
- Postman
- JUnit
- GitHub
- YouTrack

### Hardware Integration
- QR Codes
- NFC Cards (NTAG213/215)

Version Control: GitHub

Project Management: YouTrack or equivalent

## 7. Current Development Status
The project is in the initial planning and documentation stage. The requirements listed in this document describe planned functionality and do not indicate completed implementation.

