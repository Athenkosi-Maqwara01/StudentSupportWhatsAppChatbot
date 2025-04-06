# State Transition Diagrams & Explanations for WhatsApp Chatbot System

---

##  Student Query State Diagram Explanation
![Editor _ Mermaid Chart-2025-04-06-181208](https://github.com/user-attachments/assets/80230bd9-ba74-47bd-9d86-e4d8ef13e06c)

### Key States:
- **New** – Initial state when a student submits a query via WhatsApp  
- **Processing** – System is analysing the query using NLP  
- **UnderstandingFailed** – System couldn’t recognise the user’s intent  
- **Understood** – Query intent has been successfully recognised  
- **FetchingData** – System is retrieving requested information  
- **DataUnavailable** – Requested information couldn’t be found  
- **ResponseReady** – Response has been prepared  
- **Responded** – Response has been delivered to the student  
- **EscalationRequired** – Query needs human intervention  
- **Escalated** – Query has been transferred to human support  
- **Rejected** – Query contains prohibited content  

### Key Transitions:
- New → Processing when NLP analysis begins  
- If failed: UnderstandingFailed → EscalationRequired after multiple attempts  
- Understood → FetchingData → ResponseReady  
- DataUnavailable may result in escalation  
- Terminal states: Responded or Escalated  

### Mapping to Functional Requirements:
- **FR-001**: Process student inquiries about registration  
- **FR-009**: Escalate complex queries  
- **FR-013**: Filter prohibited content  
- **US-010**: Robust NLP implementation  

---

## Notification State Diagram Explanation
![Editor _ Mermaid Chart-2025-04-06-182917](https://github.com/user-attachments/assets/52ae1dd0-1aa7-4abb-ace1-bad73b8c6e25)

### Key States:
- **Created**  
- **Scheduled**  
- **ReadyToSend**  
- **Sending**  
- **Sent**  
- **Failed**  
- **ReadyToRetry**  
- **Abandoned**  
- **Delivered**  
- **Undeliverable**  
- **Read**  
- **Expired**  
- **Actioned**  
- **Dismissed**

### Key Transitions:
- Scheduled or immediate sends  
- Retry logic for failed deliveries  
- Various end states: Read, Actioned, Expired, etc.

### Mapping to Functional Requirements:
- **FR-007**: Administrative broadcasts  
- **FR-008**: Payment reminders (Scheduled)  
- **FR-015**: User engagement tracking  
- **FR-010**: Delivery reliability  

---

##  User Account State Diagram Explanation
![Editor _ Mermaid Chart-2025-04-06-183142](https://github.com/user-attachments/assets/8f9c2608-3ab4-4c64-8b5e-52d73f53d0de)

### Key States:
- **Unregistered**  
- **OptIn**  
- **Registered**  
- **Active**  
- **Suspended**  
- **Dormant**  
- **Archived**  
- **Terminated**  
- **Blacklisted**

### Key Transitions:
- OptIn → Registered  
- Inactivity → Dormant → Archived  
- Suspension can lead to reinstatement or termination  
- Terminated or Blacklisted are end states  

### Mapping to Functional Requirements:
- **FR-014**: Regulatory compliance  
- **FR-013**: Abuse management  
- **FR-010**: System performance  
- **US-012**: POPIA compliance  

---

##  Course Material State Diagram Explanation
![Editor _ Mermaid Chart-2025-04-06-183346](https://github.com/user-attachments/assets/bd57a3de-565b-4c96-a45a-7d24c0137ac4)

### Key States:
- **Draft**  
- **Pending**  
- **Rejected**  
- **Approved**  
- **Published**  
- **VersionObsolete**  
- **Deprecated**  
- **Unpublished**  
- **Archived**  
- **Discarded**

### Key Transitions:
- Approval workflow → Published  
- May move to Archived or Deprecated based on relevance  

### Mapping to Functional Requirements:
- **FR-005**: Update learning materials  
- **US-005**: Version control  
- **FR-014**: Notify updates  

---

##  Payment Transaction State Diagram Explanation
![image](https://github.com/user-attachments/assets/53698fbf-8375-46d0-89f2-3b03637ae16a)

### Key States:
- **Initiated**  
- **Processing**  
- **Verifying**  
- **Authorized**  
- **Declined**  
- **Completed**  
- **Reversed**  
- **Reconciled**  
- **Flagged**  
- **Disputed**  
- **Resolved**  
- **Expired**  
- **Failed**

### Key Transitions:
- Gateway communication and verification  
- Reconciliation and auditing paths  

### Mapping to Functional Requirements:
- **FR-012**: Process financial queries  
- **US-009**: Reconciled transaction checks  
- **FR-008**: Payment reminders  
- **US-009**: Support audit trails  

---

## Support Ticket State Diagram Explanation
![image](https://github.com/user-attachments/assets/62c2382d-ac13-478a-aa7b-3ed479aef5a9)

### Key States:
- **New**  
- **Open**  
- **InProgress**  
- **OnHold**  
- **Resolved**  
- **Closed**  
- **Escalated**  
- **Rejected**

### Key Transitions:
- SLA triggers escalation  
- Resolved → Confirmation → Closed  

### Mapping to Functional Requirements:
- **US-007**: Ticket lifecycle  
- **SLA compliance**  
- **Update and confirmation**  

---

##  Distress Alert State Diagram Explanation
![image](https://github.com/user-attachments/assets/d3182903-2003-4708-95da-a33706541f39)

### Key States:
- **Detected**  
- **Analysing**  
- **LowRisk / MediumRisk / HighRisk**  
- **FalsePositive**  
- **Monitored**  
- **Notified**  
- **Acknowledged**  
- **InProgress**  
- **Escalated**  
- **Resolved**  
- **Followed**  
- **Closed**  
- **Dismissed**

### Key Transitions:
- Risk assessment → Notification  
- Emergency triggers based on severity  
- Resolution and follow-up paths  

### Mapping to Functional Requirements:
- **US-010**: Detect student distress  
- NLP detection and immediate escalation  
- Supports 24/7 functionality  

