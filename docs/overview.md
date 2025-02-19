# OPDX Protocol Overview

OPDX is designed with privacy and interoperability in mind, allowing users to control the visibility of their profile data while enabling a broad ecosystem of services to access it securely.

## Use Cases

- **Avatar & Profile Retrieval**: Services can display user avatars or other profile information associated with an email address (similar to how Gravatar works).
- **Cross-Service Identity**: OPDX can be used to centralize profile information across different services, allowing seamless integration without needing to re-enter personal details.

## Quick Start Guide

If you're a **developer** looking to integrate OPDX into your application, there are two main areas to focus on:

### 1. **Client-Side Implementation**  
   The client-side is responsible for fetching and displaying profile data from an OPDX-compatible API (hosted by the email provider or service). You’ll typically use the user's email address (hashed for privacy) to make the request and display the profile information in your app.

   **Getting Started**:  
   - [Client-Side Integration](spec/client-side.md)  
     Learn how to retrieve user profile data and handle the response using OPDX endpoints.

### 2. **Server-Side Implementation**  
   On the server side, you'll need to implement an OPDX-compatible API that serves profile data based on an email address. This involves exposing the data through HTTP endpoints, supporting authentication (if necessary), and respecting privacy settings.

   **Getting Started**:  
   - [Server-Side Integration](spec/server-side.md)  
     Learn how to implement the OPDX API, including setting up endpoints, security measures, and privacy controls.

## Protocol Flow

### 1. **Client Request**
   - The client queries the OPDX DNS delegation record to find the base URL for the ODPX-compatible service
   - The client queries the OPDX-compatible service using a hashed version of the email address (to protect user privacy).
   - The server responds with the associated profile data, including optional fields like name, avatar URL, and additional metadata.

### 2. **Data Structure**
   - The response follows a standardized JSON format, with required and optional fields for profile data.
   - You can extend this format with custom fields, as long as they follow the OPDX guidelines.

   **Documentation**:  
   - [OPDX Profile Data Format](spec/profile-format.md)

### 3. **Security & Privacy**
   - Data access is controlled by CORS policies and, when necessary, authentication mechanisms like API keys or OAuth tokens.
   - Users can configure the visibility of their data through the API, with clear mechanisms for opting in or out.

   **Documentation**:  
   - [Security Considerations](spec/security.md)  
   - [Privacy Settings & Authentication](spec/authentication.md)

## Getting Help

If you have any questions or need further assistance, you can reach out through our community forums or contribute to the documentation.

- **GitHub Discussions**: [Discuss on GitHub](https://github.com/opdxorg/spec/discussions)
- **Contributing**: [How to Contribute](contributing.md)

We hope you’re excited to start implementing OPDX and join the growing ecosystem of interoperable services!
