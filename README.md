# Health Promotion Integration Service
**Kamphaeng Phet Community Municipal Hospital**
*LINE Official Account Platform – Health Promotion Division*

---

## 1. System Overview

The **Health Promotion Integration Service** is a specialized module designed to manage and execute public health communication strategies via the LINE Messaging API. Its primary function is to orchestrate high-fidelity content delivery, including targeted broadcasts and dynamic Flex Messages, enabling the hospital to effectively disseminate health information and campaign updates to the community.

| Attribute | Specification |
|:---|:---|
| **Module Name** | Health Promotion Webhook & Flex Engine |
| **Organization** | Kamphaeng Phet Community Municipal Hospital |
| **Primary Scope** | Broadcasts, Flex Messaging, and Event Handling |
| **Operational Role** | Content Delivery & Integration Middleware |

## 2. Interface Specifications

This section demonstrates the visual components rendered on the user's device, focusing on **Flex Messages** (e.g., Health Cards, Appointment Reminders) or the **Rich Menu** navigation used for health campaigns.

<p align="center">
  <img src="richmenu.png" alt="User Interface Preview" width="100%" style="border: 1px solid #ddd;">
</p>
<p align="center"><em>Figure 1: Health Promotion Interface & Flex Message Layout</em></p>

## 3. Architecture & Operational Workflow

The system utilizes a modular architecture to handle incoming events and outgoing broadcasts. The workflow below illustrates the process of validating a webhook event and generating a structured Flex Message response.

```mermaid
sequenceDiagram
    participant User as End User
    participant LINE as LINE Platform
    participant Webhook as Webhook Endpoint
    participant FlexEngine as Flex Message Engine
    participant Backend as Broadcast API

    User->>LINE: Interacts (e.g., Taps Campaign)
    LINE->>Webhook: HTTPS POST /webhook
    Note right of LINE: X-Line-Signature header
    
    rect rgb(240, 240, 240)
        Note over Webhook: Security & Validation
        Webhook->>Webhook: Verify Signature
    end

    alt Valid Request
        Webhook->>Backend: Fetch Campaign Data
        Backend-->>FlexEngine: Return Health Data
        FlexEngine->>FlexEngine: Construct JSON Payload
        FlexEngine->>LINE: Push/Reply Flex Message
        LINE->>User: Renders Flex Message
    end
