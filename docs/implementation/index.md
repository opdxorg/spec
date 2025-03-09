---
title: Implementation
nav_order: 3
last_modified_date: 09.03.2025
---

## Implementation

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