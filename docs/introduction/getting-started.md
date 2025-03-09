---
title: Getting Started
parent: Introduction
nav_order: 1
last_modified_date: 25.02.2025
---

## Getting Started

OPDX is designed with privacy and interoperability in mind, allowing users to control the visibility of their profile data while enabling a broad ecosystem of services to access it securely.

### Use Cases

- **Avatar & Profile Retrieval:** Services can display user avatars or other profile information associated with an email address (similar to how Gravatar works).
- **Cross-Service Identity:** OPDX can be used to centralize profile information across different services, allowing seamless integration without needing to re-enter personal details.

### Quick Start Guide

If you're a developer looking to integrate OPDX into your application, there are two main areas to focus on:

---

#### Client-Side Implementation
\
The client-side is responsible for fetching and displaying profile data from an OPDX-compatible API (hosted by the email provider or service). You’ll typically use the user's email address (hashed for privacy) to make the request and display the profile information in your app.\
\
[→ Learn more](/docs/implementation/client)

---

#### Server-Side Implementation
\
On the server side, you'll need to implement an OPDX-compatible API that serves profile data based on an email address. This involves exposing the data through HTTP endpoints, supporting authentication (if necessary), and respecting privacy settings.\
\
[→ Learn more](/docs/implementation/server)