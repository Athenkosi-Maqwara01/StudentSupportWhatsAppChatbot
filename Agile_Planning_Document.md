# Agile Planning Document
## AI-Powered WhatsApp Chatbot for Enhancing Student Support in South African Higher Education Institutions

## Table of Contents
- [1. User Stories](#1-user-stories)
- [2. Product Backlog](#2-product-backlog)
- [3. Sprint Planning](#3-sprint-planning)
- [4. Traceability Matrix](#4-traceability-matrix)

## 1. User Stories

### User Story Table

| Story ID | User Story | Acceptance Criteria | Priority |
|----------|------------|---------------------|----------|
| US-001 | As a student, I want to ask questions about registration deadlines so that I can plan my enrollment properly. | - Chatbot provides accurate registration dates for current semester<br>- Response time < 3 seconds<br>- Information matches official university calendar | High |
| US-002 | As a student, I want to check my course schedule through WhatsApp so that I can plan my day efficiently. | - Schedule information displayed in clear, readable format<br>- Includes course name, time, location, and lecturer<br>- Option to filter by day/week<br>- Available 24/7 | High |
| US-003 | As a student, I want to receive fee payment reminders so that I don't miss important deadlines. | - Notification sent 7 days before deadline<br>- Includes amount due and payment methods<br>- Reminders should be respectful in tone<br>- Contains link to payment portal | Medium |
| US-004 | As a university administrator, I want to broadcast important announcements to students so that they stay informed about campus events. | - Message reaches all targeted students<br>- Delivery confirmation<br>- Support for text, links, and images<br>- Scheduling capability for future broadcasts | High |
| US-005 | As a lecturer, I want to update course materials through the system so that students have the latest resources. | - File upload functionality (PDF, DOC, PPT)<br>- Automatic notification to enrolled students<br>- Version control for materials<br>- Confirmation of successful upload | Medium |
| US-006 | As an IT administrator, I want to monitor chatbot performance so that I can identify and resolve issues quickly. | - Real-time dashboard showing query volume and response times<br>- Alert system for service disruptions<br>- Weekly performance reports<br>- Error logging and categorization | Medium |
| US-007 | As a student, I want to get assistance with common IT issues so that I can resolve technical problems without visiting the IT help desk. | - Step-by-step troubleshooting guides<br>- Solutions for at least 20 common IT issues<br>- Option to escalate to human support<br>- Follow-up to confirm resolution | Low |
| US-008 | As a student with disabilities, I want the chatbot to be accessible with screen readers so that I can use the service independently. | - Complies with WCAG 2.1 standards<br>- Compatible with common screen readers<br>- Text alternatives for non-text content<br>- Keyboard navigable interface | High |
| US-009 | As a finance officer, I want to check if a student has outstanding fees so that I can process requests appropriately. | - Secure authentication before displaying financial data<br>- Accurate real-time fee status<br>- Detailed breakdown of charges<br>- Audit trail of queries | Medium |
| US-010 | As a student counselor, I want to receive alerts about students in distress so that I can provide timely support. | - NLP detection of distress signals in student queries<br>- Immediate notification to counseling services<br>- Private and secure handling of sensitive information<br>- 24/7 alert functionality | High |
| US-011 | As a new student, I want to get information about campus facilities so that I can navigate the university effectively. | - Accurate location information<br>- Operating hours<br>- Contact details for each facility<br>- Integration with campus map | Low |
| US-012 | As a system administrator, I want user data encrypted with industry standards so that security compliance is met. | - AES-256 encryption for all stored data<br>- Secure transmission protocols<br>- Regular security audits<br>- Compliance with POPIA regulations | High |

## 2. Product Backlog

### MoSCoW Prioritization and Effort Estimation

| Story ID | User Story | Priority (MoSCoW) | Effort Estimate (Story Points) | Dependencies |
|----------|------------|-------------------|-------------------------------|--------------|
| US-001 | Ask questions about registration deadlines | Must-have | 3 | None |
| US-002 | Check course schedule through WhatsApp | Must-have | 5 | API integration with university schedule system |
| US-008 | Accessibility with screen readers | Must-have | 3 | None |
| US-004 | Broadcast important announcements | Must-have | 5 | WhatsApp Business API integration |
| US-012 | Data encryption for security compliance | Must-have | 8 | None |
| US-010 | Alerts about students in distress | Should-have | 8 | NLP sentiment analysis implementation |
| US-005 | Update course materials | Should-have | 5 | File storage system integration |
| US-003 | Fee payment reminders | Should-have | 3 | Integration with finance system |
| US-006 | Monitor chatbot performance | Should-have | 5 | Monitoring system implementation |
| US-009 | Check outstanding fees | Could-have | 5 | Secure finance API integration |
| US-007 | IT issue assistance | Could-have | 8 | Knowledge base for IT solutions |
| US-011 | Campus facilities information | Won't-have (for first release) | 3 | Campus GIS data integration |

### Prioritization Justification

**Must-have stories** align directly with core student support functions and critical system requirements:
- US-001 and US-002 address primary student information needs (registration and scheduling)
- US-008 ensures inclusivity and compliance with accessibility standards
- US-004 provides essential communication capability for administrators
- US-012 addresses critical non-functional security requirements essential for protecting student data

**Should-have stories** provide important functionality but aren't critical for initial MVP:
- US-010 represents an important student wellness feature but requires complex NLP implementation
- US-005 and US-003 provide valuable but secondary information delivery systems
- US-006 is important for system maintenance but not essential for initial user value

**Could-have stories** add value but can be deferred:
- US-009 and US-007 represent specialized use cases that expand beyond core functionality
- These enhance the system but aren't essential for initial deployment

**Won't-have stories** are valuable but explicitly excluded from initial releases:
- US-011 provides supplementary information that can be added in future iterations

## 3. Sprint Planning

### Sprint Goal
**"Establish core WhatsApp communication infrastructure and implement basic student information query functionality to deliver an initial working chatbot within two weeks."**

This sprint focuses on creating a foundation that allows students to interact with the chatbot via WhatsApp and receive accurate responses to basic queries. This will demonstrate the system's core value proposition while establishing the technical infrastructure for future enhancements.

### Sprint Backlog

| Task ID | Task Description | Assigned To | Estimated Hours | Status |
|---------|------------------|-------------|-----------------|--------|
| T-001 | Set up WhatsApp Business API integration | Backend Developer | 8 | To Do |
| T-002 | Design conversation flow for registration queries | NLP Specialist | 6 | To Do |
| T-003 | Implement secure data storage with encryption | Security Engineer | 10 | To Do | 
| T-004 | Create API connector to university registration system | Backend Developer | 12 | To Do |
| T-005 | Develop NLP model for understanding registration queries | NLP Specialist | 16 | To Do |
| T-006 | Implement basic logging and error handling | Backend Developer | 6 | To Do |
| T-007 | Set up automated testing for chatbot responses | QA Engineer | 8 | To Do |
| T-008 | Design and implement basic admin dashboard | Frontend Developer | 10 | To Do |
| T-009 | Create user documentation for initial release | Technical Writer | 6 | To Do |
| T-010 | Conduct accessibility testing with screen readers | Accessibility Specialist | 8 | To Do |

### Selected User Stories for Sprint 1

| Story ID | User Story | Story Points |
|----------|------------|--------------|
| US-001 | Ask questions about registration deadlines | 3 |
| US-002 | Check course schedule through WhatsApp | 5 |
| US-008 | Accessibility with screen readers | 3 |
| US-012 | Data encryption for security compliance | 8 |

### Sprint Velocity: 19 Story Points

The sprint aims to establish the core functionality that provides immediate value to students (registration information and scheduling) while ensuring system security and accessibility. These stories were selected because they represent the minimum viable product that can demonstrate value to stakeholders while establishing the technical foundation for future development.

## 4. Traceability Matrix

This matrix shows how the user stories relate to the functional requirements (FR) and use cases (UC) from previous assignments.

| User Story ID | Related Functional Requirements | Related Use Cases |
|---------------|--------------------------------|-------------------|
| US-001 | FR-001: Process student inquiries about registration<br>FR-003: Provide accurate academic deadlines | UC-001: Student Inquires About Registration |
| US-002 | FR-002: Access student academic schedules<br>FR-004: Present course information | UC-002: Student Checks Course Schedule |
| US-003 | FR-008: Send payment reminders<br>FR-012: Process financial queries | UC-005: System Sends Automated Reminders |
| US-004 | FR-007: Enable administrative broadcasts<br>FR-015: Support multimedia content | UC-003: Administrator Broadcasts Announcement |
| US-005 | FR-005: Update learning materials<br>FR-014: Notify students of updates | UC-006: Lecturer Updates Course Materials |
| US-006 | FR-010: Monitor system performance<br>FR-013: Generate system reports | UC-008: IT Admin Monitors System Performance |
| US-007 | FR-006: Provide IT troubleshooting<br>FR-009: Escalate complex queries | UC-004: Student Requests IT Support |
| US-008 | FR-011: Support accessibility standards | UC-007: Disabled Student Uses Screen Reader |
| US-009 | FR-012: Process financial queries<br>FR-008: Access fee information | UC-005: Finance Officer Verifies Fee Status |
| US-010 | FR-009: Detect and escalate urgent issues<br>FR-015: Support wellness monitoring | UC-010: System Identifies Student in Distress |
| US-011 | FR-006: Provide campus information | UC-001: Student Requests Facility Information |
| US-012 | FR-013: Implement data security<br>FR-014: Maintain regulatory compliance | UC-009: System Secures Sensitive Data |
