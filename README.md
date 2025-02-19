# OPDX Protocol Specification

> Version 0.1

## Overview
**OPDX (Open Profile Data Exchange)** is a decentralized protocol for retrieving public profile data (such as avatars) associated with an email address. The protocol allows email providers and self-hosted instances to expose profile data in a standardized way, without relying on a centralized service, like Gravatar.

## Design Principles
1. **Open & Decentralized** – Anyone can build and host an OPDX-compatible instance. Which server, framework or language to use is completly in the hands of developers, as long as the instance complies with the OPDX specification.
2. **Privacy-Conscious** – No authentication required. Rate-limiting and caching are optional, but should be considered.
3. **DNS-Based Discovery** – Clients discover OPDX servers using a simple TXT record. There is no need for a central instance or directory of instances.
4. **Minimal & Lightweight** – The protocol mandates simple REST API requests and responses using a standardized JSON format.

## 1. Discovery Mechanism
OPDX identifies users by their email address, using the domain to locate the corresponding OPDX-compatible instance.

To locate the OPDX-compatible instance for a given email (`user@example.com`), clients should extract the domain (including any subdomains) and query the following DNS TXT record for the extracted domain:

```
_opdx.example.com TXT "https://opdx.example.com/api/v1"
```

This record contains the base URL of the OPDX API for the domain.

## 2. API Specification

> [!NOTE]
> You can find the complete OPDX API specification here: [spec.opdx.org/api](https://spec.opdx.org/api)


### **2.1. Request Format**
Clients request profile data by making a GET request to the discovered OPDX endpoint:

```
GET {base_url}/profile/{email_hash}
```

`{email_hash}` is a **SHA256 hash** of the lowercase email address to ensure privacy.

### **2.2. Response Format**
A successful response returns a JSON object:

```json
{
    "version": "1.0",
    "hash": "b4c9a289323b21...",
    "type": "individual",
    "display_name": "John Doe",
    "data": {
        "avatar": {
            "url": "https://opdx.example.com/v1/api/avatar/b4c9a289323b21...",
            "alt_text": "A portrait of John Doe"
        },
        "description": "Just a random person.",
        "website": "https://johndoe.com",
        "phone": "+491234567890",
        "location": "Berlin, Germany",
        "time_zone": "America/New_York",
        "job_title": "Software Engineer",
        "company": "ACME Inc",
        "pronouns": "he/they",
        "languages": ["en"]
    }
}
```

> [!NOTE]
> The distinction between optional and required values can be found in the full OPDX API specification [spec.opdx.org/api](https://spec.opdx.org/api)

If no profile is found, an error is returned:
```json
{
  "detail": "Profile not found"
}
```

## 3. Security & Privacy Considerations
- **Hashing Emails** – Email addresses are hashed to prevent mass enumeration.
- **Rate Limiting** – Servers should implement request limits to prevent abuse.
- **CORS Policy** – Providers may restrict cross-origin requests for security with the exception of all `GET` endpoints to not obstruct the retrieval of information

## 4. Implementation Guide
- **For Email Providers:** Host an OPDX-compatible API and publish the `_opdx` DNS TXT record.
- **For Clients:** Implement DNS lookups and query discovered endpoints.

## 5. Future Enhancements
- Support for additional profile fields.
- Optional authentication for private profile data.
- Federation between OPDX servers for improved redundancy.

## 6. License
The OPDX protocol is open-source under the **MIT License**.
