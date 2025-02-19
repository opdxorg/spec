# OPDX Specification

Welcome to the **Open Profile Data Exchange (OPDX)** protocol specification!

## What is OPDX?
**OPDX (Open Profile Data Exchange)** is a decentralized protocol for retrieving public profile data (such as avatars) associated with an email address. The protocol allows email providers and self-hosted instances to expose profile data in a standardized way, without relying on a centralized service, like Gravatar.

## Design Principles
1. **Open & Decentralized** – Anyone can build and host an OPDX-compatible instance. Which server, framework or language to use is completly in the hands of developers, as long as the instance complies with the OPDX specification.
2. **Privacy-Conscious** – No authentication required. Rate-limiting and caching are optional, but should be considered.
3. **DNS-Based Discovery** – Clients discover OPDX servers using a simple TXT record. There is no need for a central instance or directory of instances.
4. **Minimal & Lightweight** – The protocol mandates simple REST API requests and responses using a standardized JSON format.

## Features
- 🔓 Open & decentralized
- 🤫 Privacy-focused
- 🌎 Compatible with multiple providers

[Get Started →](overview.md)
