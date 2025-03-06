# System Requirements Document (SRD)

## AI-Powered WhatsApp Chatbot for Enhancing Student Support in South African Higher Education Institutions

### 1. Introduction
This document outlines the functional and non-functional requirements for the AI-powered WhatsApp chatbot system designed to provide academic and administrative support to students in South African higher education institutions.

### 2. Functional Requirements

#### 2.1 User Interaction

**FR-1:** The system shall allow students to initiate conversations via WhatsApp using text messages to a designated institutional number.

- **Acceptance Criteria:** New users receive an automated welcome message explaining available services within 5 seconds of initial contact.

**FR-2:** The system shall recognize and process at least 15 categories of student queries including course information, registration, fees, exams, deadlines, and campus services.

- **Acceptance Criteria:** Query categorization accuracy must exceed 85% in system testing.

**FR-3:** The system shall provide step-by-step guidance for complex administrative processes (registration, fee payment, etc.) with sequential messages.

- **Acceptance Criteria:** Completion rate of guided processes must exceed 70% without human intervention.

**FR-4:** The system shall support multi-turn conversations by maintaining context for at least 10 exchange rounds or 30 minutes of inactive time.

- **Acceptance Criteria:** System correctly refers to previously mentioned entities in 90% of follow-up questions.

#### 2.2 Information Management

**FR-5:** The system shall retrieve real-time course information including schedules, venue changes, and assessment dates from university systems.

- **Acceptance Criteria:** Information provided matches source systems with 100% accuracy and refreshes at intervals not exceeding 30 minutes.

**FR-6:** The system shall allow administrative staff to update FAQs and response templates through a web-based management interface.

- **Acceptance Criteria:** Updates made by authorized staff reflect in chatbot responses within 5 minutes.

**FR-7:** The system shall support attachment sharing for documents such as forms, maps, and guides when specifically requested by users.

- **Acceptance Criteria:** Document delivery success rate exceeds 95% with appropriate file format conversions if needed.

**FR-8:** The system shall provide personalized information based on student profile data (program, year, residence status) when available and relevant.

- **Acceptance Criteria:** Personalized responses are provided for at least 60% of queries where student identity is verified.

#### 2.3 System Behavior

**FR-9:** The system shall automatically escalate to human operators when confidence in AI-generated responses falls below a configurable threshold (default 70%).

- **Acceptance Criteria:** Low-confidence queries are correctly identified and escalated in 95% of cases.

**FR-10:** The system shall log all interactions for quality assurance and improvement purposes while anonymizing personal information.

- **Acceptance Criteria:** 100% of conversations are logged with student identifiers encrypted or hashed.

**FR-11:** The system shall support at least three South African languages (English, isiZulu, Afrikaans) for basic interactions.

- **Acceptance Criteria:** Language detection accuracy exceeds 95% and appropriate responses are provided in the detected language.

**FR-12:** The system shall offer options for students to provide feedback on response quality after each substantive interaction.

- **Acceptance Criteria:** Feedback collection mechanism is presented in 100% of conversation closures with a response rate exceeding 30%.

#### 2.4 Integration Capabilities

**FR-13:** The system shall integrate with the university's Student Information System (SIS) to verify student identity and retrieve student-specific data.

- **Acceptance Criteria:** Student verification completes within 3 seconds with 99.9% accuracy.

**FR-14:** The system shall connect to the university's Learning Management System (LMS) to retrieve course-specific information.

- **Acceptance Criteria:** Course information queries return accurate data from the LMS within 5 seconds.

**FR-15:** The system shall generate weekly and monthly analytics reports on usage patterns, common queries, and resolution rates.

- **Acceptance Criteria:** Reports are automatically generated and distributed to designated stakeholders with visualization of key metrics.

### 3. Non-Functional Requirements

#### 3.1 Usability

**NFR-1:** The chatbot interface shall use clear, concise language at a high school reading level, avoiding technical jargon unless directly relevant to the query.

- **Metric:** Flesch-Kincaid readability score of 70 or higher for standard responses.

**NFR-2:** The system shall provide helpful error messages and recovery options when it cannot understand or process a query.

- **Metric:** At least 3 alternative suggestions offered when initial query fails.

**NFR-3:** The chatbot shall respond to queries using a consistent format with clear demarcation between different information types (facts, instructions, links).

- **Metric:** 90% of user satisfaction surveys confirm information clarity and readability.

#### 3.2 Deployability

**NFR-4:** The system shall be containerized using Docker to enable deployment across different cloud platforms and on-premises environments.

- **Metric:** Successful deployment on at least 2 different platforms (e.g., AWS, Azure, on-premises) with identical functionality.

**NFR-5:** The system shall include automated deployment scripts that complete installation and configuration in less than 30 minutes on compatible systems.

- **Metric:** Zero manual configuration steps required post-deployment script execution.

#### 3.3 Maintainability

**NFR-6:** The system shall be built with modular architecture allowing components (NLP engine, knowledge base, integrations) to be updated independently.

- **Metric:** Component replacement or upgrade possible without system-wide downtime.

**NFR-7:** The system shall include comprehensive technical documentation including API specifications, database schemas, and deployment guides.

- **Metric:** Documentation updated within 48 hours of any significant system change.

**NFR-8:** The system shall incorporate a robust logging mechanism that captures all system events with appropriate severity levels to facilitate troubleshooting.

- **Metric:** Logs sufficiently detailed to diagnose 95% of reported issues without additional information.

#### 3.4 Scalability

**NFR-9:** The system shall support horizontal scaling to handle at least 10,000 concurrent users during peak periods (registration, exam times).

- **Metric:** No degradation in response time with 10x normal user load.

**NFR-10:** The database component shall scale to store and efficiently query at least 5 years of anonymized conversation history.

- **Metric:** Query performance degradation not exceeding 15% with 5 years of data compared to 1 month.

#### 3.5 Security

**NFR-11:** All communication between the system and WhatsApp shall be encrypted using industry-standard TLS 1.3 or higher.

- **Metric:** Security scan showing zero unencrypted data transmission.

**NFR-12:** The system shall comply with Protection of Personal Information Act (POPIA) requirements for data collection, storage, and processing.

- **Metric:** Successful compliance audit with all critical POPIA requirements.

**NFR-13:** Access to administration interfaces shall require multi-factor authentication and role-based permissions.

- **Metric:** 100% of administrative actions traceable to authenticated individuals.

#### 3.6 Performance

**NFR-14:** The system shall process and respond to standard queries within 3 seconds under normal load conditions.

- **Metric:** 95th percentile response time not exceeding 3 seconds.

**NFR-15:** The system shall achieve 99.5% uptime during academic terms, with scheduled maintenance occurring during university breaks.

- **Metric:** Downtime not exceeding 3.6 hours per month during term time.

**NFR-16:** The system shall support at least 100 new conversations per minute during peak periods without performance degradation.

- **Metric:** Consistent response times maintained during simulated high-load testing.

