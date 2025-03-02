# Architectural Documentation

## Student Support WhatsApp Chatbot                                                                                                                                                                                                                                                                                                                                                                               
***An AI-Powered WhatsApp Chatbot for Enhancing Student Support in South African Higher Education Institutions***

### Domain
Higher Education - Targeted at universities and colleges to improve communication efficiency and student support services.

### Problem Statement
Address delays in student support by providing an AI chatbot that answers FAQs and guides students in real time, thereby reducing administrative burden and improving student satisfaction.

## C4 Model Architecture

### Level 1: Context Diagram
The Context Diagram illustrates how the chatbot system interacts with external entities:

- **Students**: End users who interact with the chatbot via WhatsApp
- **AI WhatsApp Chatbot System**: The core system that processes queries and generates responses
- **University Information Systems**: Legacy systems containing academic and administrative data
- **WhatsApp Business API**: The communication channel that enables message exchange

Key Interactions:
- Students send queries through WhatsApp
- The chatbot system processes queries and returns appropriate responses
- The chatbot retrieves necessary information from university systems
- WhatsApp Business API facilitates message exchange between students and the chatbot

### Level 2: Container Diagram
The Container Diagram breaks down the system into its main components:

1. **WhatsApp Interface**: Manages communication with the WhatsApp Business API
2. **Chatbot Backend Service**: Core service that orchestrates query processing and response generation
3. **NLP Engine**: Processes natural language queries to extract intent and entities
4. **Knowledge Base**: Contains FAQs, course information, and other structured data
5. **University API Gateway**: Interfaces with university systems to retrieve real-time data
6. **User Session Manager**: Maintains conversation context and user session information

Data Flow:
- Messages from WhatsApp are received by the WhatsApp Interface
- Backend Service coordinates processing with the NLP Engine
- Knowledge Base and University API Gateway provide information for responses
- User Session Manager maintains conversational context
- Responses are sent back through the WhatsApp Interface

### Level 3: Component Diagram
The Component Diagram details the internal structure of the containers:

1. **Message Handler**: Receives and prepares messages for processing
2. **Intent Classifier**: Determines the purpose of the student query
3. **Entity Extractor**: Identifies key information points in the query
4. **Response Generator**: Creates appropriate responses based on intent and entities
5. **FAQ Matcher**: Matches queries against frequently asked questions
6. **Database Connector**: Accesses the knowledge base
7. **API Client**: Communicates with university systems
8. **Context Manager**: Maintains conversation flow and context

Processing Flow:
- Message Handler processes incoming messages
- Intent Classifier and Entity Extractor analyze query content
- Response Generator uses the analysis to create appropriate responses
- Supporting components (FAQ Matcher, Database Connector, API Client) provide necessary information
- Context Manager ensures conversational continuity

### Level 4: Code Diagram
The implementation will follow a modular approach with the following structure:

```
src/
├── api/
│   ├── whatsapp.js        # WhatsApp API integration
│   └── university.js      # University systems API client
├── nlp/
│   ├── classifier.js      # Intent classification
│   ├── extractor.js       # Entity extraction
│   └── preprocessor.js    # Text preprocessing
├── knowledge/
│   ├── faq.js             # FAQ handling
│   └── database.js        # Knowledge base operations
├── session/
│   └── manager.js         # Session management
├── response/
│   ├── generator.js       # Response generation
│   └── templates.js       # Response templates
└── index.js               # Application entry point
```

## Technology Stack

1. **Backend Framework**: Node.js with Express
2. **NLP Processing**: TensorFlow.js or Hugging Face Transformers
3. **Database**: MongoDB for knowledge base and session storage
4. **API Integration**: RESTful APIs with Axios
5. **Messaging**: WhatsApp Business API
6. **Containerization**: Docker for deployment
7. **CI/CD**: GitHub Actions
8. **Cloud Infrastructure**: AWS or Azure for hosting

## Security Considerations

1. **Data Protection**: End-to-end encryption for message transmission
2. **Authentication**: OAuth 2.0 for API access
3. **Authorization**: Role-based access control
4. **Data Retention**: Compliance with POPIA (Protection of Personal Information Act)
5. **Audit Logging**: Comprehensive logging for system activities

## Scalability Approach

1. **Horizontal Scaling**: Multiple instances of containers
2. **Load Balancing**: Distribution of incoming requests
3. **Caching**: Redis for frequent queries
4. **Database Sharding**: For growing data volumes
5. **Microservices Architecture**: For independent scaling of components

## Implementation Considerations

1. **Language Support**: Multi-language support for South Africa's official languages
2. **Offline Capability**: Graceful handling of connectivity issues
3. **Feedback Loop**: Mechanism for continuous improvement
4. **Monitoring**: Real-time system health and performance tracking
5. **Analytics**: Usage patterns and query analysis for system enhancement

