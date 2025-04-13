# Challenges in Choosing Granularity for States/Actions

## Balancing Detail vs. Readability
One of the primary challenges was finding the optimal balance between comprehensive detail and diagram readability. For complex objects like the **Payment Transaction** and **Support Ticket**, including every possible state would create overwhelmingly complex diagrams. However, oversimplification risks missing critical transitions that impact system behaviour.

For example, in the Payment Transaction state diagram, I initially considered including sub-states for the **"Processing"** state (like *"Contacting Gateway," "Awaiting Response,"* etc.). While technically accurate, these details would have cluttered the diagram without adding significant value for most stakeholders. Instead, I opted for a higher-level **"Processing"** state with clearer transition paths.

## Domain-Specific Granularity Requirements

Different objects required varying levels of granularity based on their complexity and business importance:

- **High Granularity Objects**:  
  The **Distress Alert** diagram required fine-grained states to accurately reflect the critical nature of mental health support. Here, distinguishing between *"LowRisk," "MediumRisk,"* and *"HighRisk"* states was essential despite adding complexity.

- **Medium Granularity Objects**:  
  For **User Account** states, a moderate level of detail captured the essential lifecycle while keeping the diagram manageable. States like *"Suspended"* and *"Dormant"* were distinct enough to warrant separate representations.

- **Lower Granularity Objects**:  
  The **Course Material** diagram benefited from a simpler approach, focusing on key publishing states rather than detailing every possible sub-state in the content creation process.

## Time-Based Considerations

Deciding when to represent time-based transitions presented another granularity challenge. For instance, in the **Student Query** diagram, I chose to represent multiple failed understanding attempts explicitly rather than simplifying to a single *"Failed"* state, as this better reflected the actual system behaviour of trying multiple approaches before escalation.

---

# Challenges in Aligning Diagrams with Agile User Stories

## Translating User-Centric Stories to Technical States

User stories are inherently user-focused and often don't explicitly mention system states.  
For example, **US-007** states:

> "As a student, I want to log support tickets through WhatsApp so that I can get help when needed."

This doesn’t specify the underlying ticket states. Deriving appropriate technical states while ensuring they fulfil the user's actual needs required careful analysis.

## Ensuring Complete Coverage of Acceptance Criteria

Each user story contains specific acceptance criteria that must be reflected in the state and activity diagrams.  
For instance, **US-009** requires that:

> "Students can check their fee status."

This needed representation in the **Payment Transaction** state diagram through states like **"Reconciled"** and transitions that enable status checking.

## Handling Cross-Cutting Concerns

Many user stories had overlapping concerns that affected multiple diagrams.  
**US-010** about distress detection influenced both the **Distress Alert** state diagram and the **Student Distress Detection** activity workflow. Ensuring consistency across these related diagrams while maintaining their distinct purposes required constant cross-referencing.

## Maintaining Agile Flexibility

State diagrams tend to formalise behaviour, which can seem contrary to Agile's emphasis on adaptability.  
Finding the right balance between definitive state modelling and allowing for future refinement was challenging, particularly for features likely to evolve over time like the **NLP understanding capabilities** in the **Student Query** state diagram.

---

# Comparison of State Diagrams vs. Activity Diagrams

## Fundamental Differences

### Object State Diagrams:
- **Focus on Being**: Captured what an object *is* at any given moment.
- **Object-Centric**: Represented a single system entity (e.g., *Student Query*, *Payment Transaction*).
- **Event-Driven Transitions**: Transitions triggered by specific events.
- **Comprehensive State Coverage**: Represented all possible states, including edge cases and error conditions.

### Activity Diagrams:
- **Focus on Doing**: Showed what the system *does* in sequence.
- **Process-Centric**: Represented end-to-end workflows involving multiple components.
- **Sequential Flow**: Activities followed procedural sequences with decision points.
- **Actor Interactions**: Swimlanes showed responsibilities across different system actors and users.

## Complementary Relationship

The two modelling approaches complemented each other:

- The **Course Material** state diagram defined possible states of a course document, while the **Course Material Update** activity workflow showed the lecturer’s update process.
- The **Payment Transaction** state diagram modelled payment states, while the **Fee Payment Reminder** activity workflow showed the reminder process.
- The **Distress Alert** state diagram defined alert states, while the **Student Distress Detection** workflow illustrated detection and response steps.

---

# Implementation Insights

## Stakeholder Understanding
- **Activity Diagrams**: More intuitive for non-technical stakeholders, resembling familiar business processes.
- **State Diagrams**: Provided deeper insight for developers into system data models and logic transitions.

Using both created a comprehensive view:
- **State Diagrams**: Defined rules for object transitions.
- **Activity Diagrams**: Showed object interactions in business processes.

---

# Technical Implementation Considerations

- **State Diagrams** informed **database schema design**, including status fields and state transition validations.
- **Activity Diagrams** translated into **application logic**, API endpoints, and component integrations.

---

# Conclusion

The balance between state and activity modelling provided a robust foundation for implementing the WhatsApp chatbot system. Each diagram type addressed different aspects of system behaviour, while collectively maintaining alignment with user stories and functional requirements.
