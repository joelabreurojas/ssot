# Functional & Non-Functional Requirements

## 1. Functional Requirements (FR)
<!-- 
    List the technical capabilities the system MUST have. 
    Focus on input, processing, and output.
-->
| ID | Requirement | Description |
| :--- | :--- | :--- |
| FR-01 | [e.g., File Upload] | The system must allow users to upload PDF documents up to 20MB. |
| FR-02 | [e.g., Data Parsing] | The system must extract text content from uploaded documents. |

---

## 2. Non-Functional Requirements (NFR)
<!-- 
    List the quality attributes of the system. 
-->
| Category | Requirement | Target Metric |
| :--- | :--- | :--- |
| **Performance** | Response Time | Queries must return an answer in less than 15 seconds. |
| **Security** | Data Encryption | All user documents must be encrypted at rest. |
| **Reliability** | Uptime | The system should have 99.5% availability. |
| **Scalability** | Concurrent Users | The system must support 100 concurrent chat sessions. |
