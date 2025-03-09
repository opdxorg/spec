---
title: Introduction
nav_order: 2
last_modified_date: 09.03.2025
---

## What is OPDX?

OPDX (Open Profile Data Exchange) is a decentralized protocol for retrieving public profile data (such as avatars) associated with an email address. The protocol allows email providers and self-hosted instances to expose profile data in a standardized way, without relying on a centralized service, like Gravatar.

## Features

🔓 Open & decentralized\
🤫 Privacy-focused\
🌎 Compatible with multiple providers

## Design Principles

- Open & Decentralized – Anyone can build and host an OPDX-compatible instance. Which server, framework or language to use is completly in the hands of developers, as long as the instance complies with the OPDX specification.
- Privacy-Conscious – No authentication required. Rate-limiting and caching are optional, but should be considered.
- DNS-Based Discovery – Clients discover OPDX servers using a simple TXT record. There is no need for a central instance or directory of instances.
- Minimal & Lightweight – The protocol mandates simple REST API requests and responses using a standardized JSON format.