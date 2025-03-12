# Test and Use Case Document

## AI-Powered WhatsApp Chatbot for South African Higher Education Institutions

### 1. Use Case Diagram

The UML use case diagram visualizes how different actors interact with the AI-Powered WhatsApp Chatbot system.

### 2. Key Actors and Their Roles

1. **Student**
   - Primary user of the chatbot system
   - Initiates queries and receives information about academic matters, administrative processes, and campus services
   - Provides feedback on system responses
   - Participates in both basic and complex interactions

2. **Administrative Staff**
   - Manages and updates the knowledge base with accurate administrative information
   - Handles escalated queries that the chatbot cannot resolve
   - Reviews analytics reports to improve administrative processes
   - Processes administrative requests initiated through the chatbot

3. **IT Staff**
   - Monitors system performance and ensures technical reliability
   - Manages user authentication and security aspects
   - Resolves technical issues and performs system maintenance

4. **Academic Staff**
   - Updates course-specific information in the knowledge base
   - Reviews analytics reports to identify common student questions
   - Uses insights to improve course materials and communication

5. **University Management**
   - Reviews high-level analytics reports for strategic decision-making
   - Evaluates system effectiveness and return on investment
   - Sets policies for system usage and development

6. **System Maintainer**
   - Maintains and improves the technical components of the system
   - Updates NLP models and integrations
   - Configures multi-language support and system capabilities

7. **WhatsApp API**
   - External system actor that facilitates message delivery
   - Handles authentication of WhatsApp users
   - Supports multi-language message processing

### 3. Relationships Between Actors and Use Cases

1. **Include Relationships**
   - "Query Academic Information" includes "Authenticate User" as all student queries require verification of student identity
   - "Process Administrative Request" includes "Authenticate User" for security and personalization
   - "Escalate to Human Support" includes "Query Academic Information" as escalation often builds on initial query context
   - "Generate Analytics Reports" includes "Monitor System Performance" as performance metrics are part of analytics

2. **Actor-Use Case Relationships**
   - Students interact with the most use cases, reflecting their role as primary users
   - Administrative Staff handle both front-end (supporting students) and back-end (maintaining knowledge) functions
   - IT Staff focus on technical reliability and security
   - System Maintainers handle specialized technical aspects including multi-language support
   - WhatsApp API interacts with authentication and language handling

### 4. Alignment with Stakeholder Concerns

1. **Student Concerns**
   - "Query Academic Information" and "Process Administrative Request" address students' need for quick access to accurate information
   - "Receive Deadline Notifications" addresses the concern of missing important dates
   - "Handle Multi-language Interaction" addresses language barrier concerns
   - "Escalate to Human Support" ensures complex issues can still be resolved

2. **Administrative Staff Concerns**
   - "Manage Knowledge Base" provides an efficient way to update system information
   - "Generate Analytics Reports" helps identify improvement areas
   - "Escalate to Human Support" ensures complex issues are properly directed

3. **IT Department Concerns**
   - "Monitor System Performance" addresses uptime and reliability concerns
   - "Authenticate User" addresses security concerns

4. **University Management Concerns**
   - "Generate Analytics Reports" provides data for ROI evaluation
   - System coverage of multiple use cases demonstrates value for investment

5. **Academic Staff Concerns**
   - "Update Course Information" enables accurate representation of course content
   - "Generate Analytics Reports" provides insights into student questions and difficulties

### 5. Use Case Specifications

#### Use Case 1: Query Academic Information

**Description:** Allows students to request and receive information about courses, schedules, assessments, and academic policies via the WhatsApp chatbot.

**Primary Actor:** Student

**Preconditions:**
1. Student has initiated a conversation with the chatbot via WhatsApp
2. Student has been authenticated in the system
3. Academic information is available in the knowledge base

**Postconditions:**
1. Student receives accurate academic information
2. Query and response are logged for analytics
3. Student is offered opportunity to ask follow-up questions

**Basic Flow:**
1. Student sends a message containing an academic query
2. System analyzes the query using NLP to determine intent and extract entities
3. System searches the knowledge base for relevant academic information
4. System formulates a response with the requested information
5. System sends the response to the student via WhatsApp
6. System logs the interaction for future reference
7. System prompts for additional queries or feedback

**Alternative Flows:**
1. **Information Not Found:**
   a. System informs student that the requested information is not available
   b. System offers to escalate to human support or suggest related queries
   c. System logs the failed query for knowledge base improvement

2. **Ambiguous Query:**
   a. System identifies multiple possible interpretations of the query
   b. System asks clarifying questions to determine exact intent
   c. Once clarified, system continues with basic flow

3. **System Timeout:**
   a. If processing exceeds time limits, system sends an interim message
   b. System continues processing or offers simplified response options

#### Use Case 2: Process Administrative Request

**Description:** Enables students to initiate and complete administrative processes such as document requests, registration queries, or fee inquiries through the chatbot.

**Primary Actor:** Student

**Preconditions:**
1. Student is authenticated in the system
2. The administrative process is supported by the chatbot
3. Required systems for process completion are accessible

**Postconditions:**
1. Administrative request is submitted or completed
2. Confirmation is provided to the student
3. Request details are recorded in appropriate systems

**Basic Flow:**
1. Student sends a message indicating an administrative request
2. System identifies the request type using NLP
3. System initiates a guided process with step-by-step instructions
4. System collects required information through conversational exchange
5. System validates collected information
6. System submits the request to appropriate university systems
7. System sends confirmation and next steps to the student
8. System logs the completed process

**Alternative Flows:**
1. **Incomplete Information:**
   a. System identifies missing required information
   b. System prompts student for specific missing details
   c. Once complete, system continues with basic flow

2. **Validation Failure:**
   a. System detects invalid information (format, content, etc.)
   b. System explains the issue and requests corrected information
   c. System validates new information and continues if valid

3. **System Integration Error:**
   a. System detects failure in submitting to university systems
   b. System informs student of temporary issue
   c. System offers escalation to human support with reference number

#### Use Case 3: Get Campus Service Information

**Description:** Provides students with information about campus services including library hours, IT support, health services, transportation, and facilities.

**Primary Actor:** Student

**Preconditions:**
1. Student is in an active chatbot session
2. Campus service information is available in the knowledge base

**Postconditions:**
1. Student receives accurate service information
2. Query is logged for analytics purposes

**Basic Flow:**
1. Student sends a query about campus services
2. System categorizes the query as service-related
3. System identifies the specific service being inquired about
4. System retrieves relevant service information (location, hours, contact details)
5. System formats information in a readable, structured format
6. System sends the response to the student
7. System offers related service information if applicable

**Alternative Flows:**
1. **Service Not Found:**
   a. System cannot identify the requested service
   b. System offers a list of available service categories
   c. Student selects from the list to continue

2. **Time-Sensitive Information:**
   a. System detects query relates to time-sensitive service (e.g., "Is the library open now?")
   b. System checks current date/time against service hours
   c. System provides contextualized response based on current time

#### Use Case 4: Receive Deadline Notifications

**Description:** Allows the system to proactively send reminders and notifications about important academic and administrative deadlines.

**Primary Actor:** Student

**Preconditions:**
1. Student has opted in to notifications
2. Student profile contains relevant program/course information
3. Deadline information is available in university systems

**Postconditions:**
1. Student receives timely notification of approaching deadlines
2. Notification delivery is logged in the system

**Basic Flow:**
1. System identifies approaching deadlines relevant to the student
2. System generates personalized notification message
3. System determines optimal timing for notification
4. System sends WhatsApp message with deadline information
5. System includes options for more information or reminders
6. System logs notification delivery

**Alternative Flows:**
1. **Notification Failure:**
   a. System detects message delivery failure
   b. System records failed notification
   c. System attempts retry based on configured rules

2. **Student Response:**
   a. Student responds to notification with a question
   b. System transitions to Query Academic Information use case
   c. System maintains context of the deadline in the conversation

#### Use Case 5: Manage Knowledge Base

**Description:** Allows administrative and academic staff to update, review, and maintain the information used by the chatbot to respond to queries.

**Primary Actor:** Administrative Staff or Academic Staff

**Preconditions:**
1. Staff member is authenticated with appropriate permissions
2. Knowledge base management interface is accessible

**Postconditions:**
1. Knowledge base is updated with accurate information
2. Changes are logged for audit purposes
3. Updated information is immediately available for student queries

**Basic Flow:**
1. Staff member accesses knowledge base management interface
2. Staff member navigates to relevant information category
3. Staff member reviews existing content
4. Staff member makes necessary additions, edits, or deletions
5. System validates changes for format and consistency
6. Staff member confirms changes
7. System updates knowledge base with new information
8. System logs the update with timestamp and user details

**Alternative Flows:**
1. **Validation Errors:**
   a. System detects formatting or consistency issues
   b. System provides specific error messages
   c. Staff member corrects issues and resubmits

2. **Concurrent Editing:**
   a. System detects another user editing same content
   b. System notifies staff member of potential conflict
   c. System provides options for resolution

#### Use Case 6: Monitor System Performance

**Description:** Enables IT staff and system maintainers to track system health, performance metrics, and identify issues requiring attention.

**Primary Actor:** IT Staff or System Maintainer

**Preconditions:**
1. Staff member has appropriate monitoring permissions
2. Monitoring systems are operational

**Postconditions:**
1. Performance data is reviewed
2. Issues are identified and documented if present

**Basic Flow:**
1. Staff member accesses monitoring dashboard
2. System displays key performance indicators (response time, uptime, error rates)
3. System shows usage statistics (active users, query volume, peak times)
4. System presents NLP performance metrics (intent recognition accuracy, etc.)
5. Staff member reviews data for anomalies or concerns
6. Staff member exports or shares relevant metrics if needed

**Alternative Flows:**
1. **Alert Condition:**
   a. System detects metrics exceeding thresholds
   b. System generates alert notification
   c. Staff member acknowledges and investigates alert
   d. System logs alert and response actions

2. **Detailed Investigation:**
   a. Staff member identifies potential issue requiring deeper analysis
   b. Staff member accesses detailed logs and transaction data
   c. System provides filtering and search capabilities
   d. Staff member documents findings and recommended actions

#### Use Case 7: Generate Analytics Reports

**Description:** Creates comprehensive reports on system usage, common queries, resolution rates, and other metrics for continuous improvement.

**Primary Actor:** University Management, Administrative Staff, or Academic Staff

**Preconditions:**
1. User has appropriate analytics access permissions
2. Sufficient data exists for meaningful analysis

**Postconditions:**
1. Analytics report is generated and delivered
2. Report access is logged for audit purposes

**Basic Flow:**
1. User requests specific analytics report type
2. User selects reporting parameters (date range, departments, query types)
3. System processes data according to parameters
4. System generates visualizations and statistical summaries
5. System compiles complete report with insights and trends
6. System delivers report in requested format (dashboard, PDF, etc.)
7. System logs report generation

**Alternative Flows:**
1. **Insufficient Data:**
   a. System detects parameters result in limited data points
   b. System warns user about statistical validity
   c. System suggests parameter adjustments

2. **Custom Analysis:**
   a. User requests non-standard analysis
   b. System provides data export option
   c. System logs special request for future report development

#### Use Case 8: Handle Multi-language Interaction

**Description:** Enables the chatbot to detect, process, and respond to queries in multiple South African languages, ensuring accessibility for a diverse student population.

**Primary Actor:** Student

**Preconditions:**
1. Student initiates conversation in supported language
2. NLP models for the language are active
3. Knowledge base content is available in the language

**Postconditions:**
1. Student receives accurate response in their chosen language
2. Language preference is recorded for future interactions

**Basic Flow:**
1. Student sends message in preferred language
2. System detects language using language identification model
3. System routes query to appropriate language-specific NLP model
4. System processes intent and entities for the language
5. System retrieves information from language-specific knowledge base
6. System formulates response in the detected language
7. System sends response to student
8. System records language preference for session continuity

**Alternative Flows:**
1. **Unsupported Language:**
   a. System cannot confidently identify language or language not supported
   b. System responds in English with language options
   c. Student selects preferred language from options
   d. System continues in selected language

2. **Mixed Language:**
   a. System detects code-switching or mixed language use
   b. System identifies primary language for response
   c. System notes language mixing for future model improvement

### 6. Test Cases

#### Functional Test Cases

| Test Case ID | Requirement ID | Description | Steps | Expected Result | Actual Result | Status |
|--------------|---------------|-------------|-------|----------------|--------------|--------|
| TC-001 | FR-1 | Student initiates conversation | 1. Student sends "Hello" to chatbot number<br>2. Wait for response | System responds within 5 seconds with welcome message explaining available services | | |
| TC-002 | FR-2 | Categorization of student query | 1. Student sends "When is the registration deadline for second semester?"<br>2. Wait for system to process | System correctly categorizes as registration query and provides deadline information | | |
| TC-003 | FR-3 | Step-by-step guidance for registration | 1. Student sends "How do I register for courses?"<br>2. Follow prompts through complete process | System provides sequential steps for registration process with clear instructions at each stage | | |
| TC-004 | FR-4 | Multi-turn conversation | 1. Student asks about CS101 course<br>2. Student follows up with "Who teaches it?"<br>3. Student asks "What are the prerequisites?" | System maintains context across all messages, understanding that "it" refers to CS101 in follow-up questions | | |
| TC-005 | FR-8 | Personalized information | 1. Authenticated student asks "What are my course schedules?"<br>2. Wait for response | System provides schedule specific to student's enrolled courses | | |
| TC-006 | FR-9 | Query escalation | 1. Student sends complex query about special accommodation for exams<br>2. Wait for system response | System recognizes low confidence, provides initial information, and offers escalation to human support | | |
| TC-007 | FR-11 | Multi-language support | 1. Student sends query in isiZulu<br>2. Wait for response | System correctly identifies language, processes query, and responds in isiZulu | | |
| TC-008 | FR-12 | Feedback collection | 1. Complete a query conversation<br>2. Observe closure message | System offers feedback option at conversation close | | |
| TC-009 | FR-13 | Student verification | 1. New student attempts to access personal information<br>2. System requests verification<br>3. Student provides student ID | System verifies identity within 3 seconds and proceeds with personalized information | | |
| TC-010 | FR-15 | Analytics report generation | 1. Admin requests weekly usage report<br>2. Specifies date range<br>3. Submits request | System generates comprehensive report with visualizations of key metrics within expected timeframe | | |

#### Non-Functional Test Cases

| Test Case ID | Requirement ID | Description | Steps | Expected Result | Actual Result | Status |
|--------------|---------------|-------------|-------|----------------|--------------|--------|
| NFT-001 | NFR-14 | Response time performance | 1. Generate 50 standard queries from test scripts<br>2. Measure response time for each<br>3. Calculate 95th percentile | 95th percentile response time does not exceed 3 seconds | | |
| NFT-002 | NFR-9 | Concurrent user scalability | 1. Simulate 10,000 concurrent users during 30-minute period<br>2. Generate varied query patterns<br>3. Monitor system performance | No degradation in response time with 10x normal load | | |
| NFT-003 | NFR-11 | Communication encryption | 1. Use network analysis tools to monitor traffic<br>2. Attempt to intercept messages<br>3. Verify encryption protocols | All communication uses TLS 1.3 or higher with zero unencrypted data transmission | | |
| NFT-004 | NFR-13 | Admin interface security | 1. Attempt to access admin functions without credentials<br>2. Attempt access with valid credentials but missing second factor<br>3. Access with complete authentication | Access denied without full multi-factor authentication | | |
| NFT-005 | NFR-2 | Error message helpfulness | 1. Send 20 intentionally malformed queries<br>2. Review system responses | For 100% of malformed queries, system provides helpful error messages with at least 3 alternative suggestions | | |
| NFT-006 | NFR-15 | System uptime | 1. Monitor system availability over 30-day academic term<br>2. Record any downtime<br>3. Calculate availability percentage | System achieves 99.5% uptime during academic term | | |
| NFT-007 | NFR-4 | Deployment flexibility | 1. Deploy identical system containers to AWS cloud<br>2. Deploy to on-premises test environment<br>3. Test core functionality in both environments | Identical functionality available in both deployment environments | | |
| NFT-008 | NFR-8 | Logging effectiveness | 1. Generate 50 distinct error conditions<br>2. Examine resulting logs<br>3. Attempt to diagnose issues using only logs | Logs contain sufficient detail to diagnose at least 95% of issues without additional information | | |

### 7. Traceability Matrix

The following matrix demonstrates the relationship between stakeholder concerns from Assignment 4, functional requirements, and the test cases designed to validate them.

| Stakeholder Concern | Functional Requirement | Test Case ID |
|---------------------|------------------------|--------------|
| Quick access to accurate information | FR-1, FR-2 | TC-001, TC-002 |
| Consistent availability outside business hours | FR-15 | TC-010, NFT-006 |
| Easy-to-use interface | FR-3 | TC-003, NFT-005 |
| Privacy and security | FR-13 | TC-009, NFT-003, NFT-004 |
| Reduction in repetitive queries | FR-5, FR-8 | TC-005 |
| Accurate representation of processes | FR-5, FR-6 | TC-005 |
| Clear escalation paths | FR-9 | TC-006 |
| Seamless integration with existing systems | FR-13, FR-14 | TC-009, NFT-007 |
| Security of data transfer | FR-13 | TC-009, NFT-003 |
| Minimal maintenance overhead | FR-15 | TC-010, NFT-006 |
| Return on investment | FR-15 | TC-010 |
| Multi-language support | FR-11 | TC-007 |
