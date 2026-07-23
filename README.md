# DCP — Domain Communication Protocol

> A foundational communication layer for the next generation of the Internet.

---

DCP is an open protocol specification for trusted, structured communication between internet domains.

The internet has evolved through a series of foundational standards:

| Protocol | What it connected |
|----------|------------------|
| DNS | Names to locations |
| HTTP | Clients to resources |
| SMTP | Mail systems |
| APIs | Software systems |

Modern digital communication still lacks a universal layer designed for **direct interaction between domains, services, and intelligent systems**. DCP explores that missing layer.

---

## The Problem

Today, most digital interactions still depend on:

- Unstructured messages
- Manual processing
- Disconnected systems
- Repeated verification
- Human interpretation

A typical flow today looks like this:

```
Customer → Email → Support Team → Internal System → Response
```

The same process repeats thousands or millions of times. Many of these interactions are predictable and structured — but the internet has no universal way to express them.

---

## The DCP Model

A domain publishes its communication capabilities at a well-known endpoint:

```
https://example.com/.well-known/dcp
```

This document describes what the domain supports:

```json
{
  "protocol": "DCP/1.0",
  "domain": "example.com",
  "capabilities": [
    "requests",
    "documents",
    "verification",
    "transactions"
  ],
  "authentication": [
    "identity",
    "signature"
  ]
}
```

A communicating system can **discover** what another domain supports before initiating any interaction.

---

## Structured Communication

**Traditional communication:**
```
"Hello, I need information about my account."
```

**DCP communication:**
```json
{
  "type": "account.request",
  "intent": "retrieve_information",
  "identity": "verified_identity",
  "authorization": {
    "scope": ["account.read"]
  }
}
```

The receiving system can determine exactly:
- **who** sent the request
- **what** is being requested
- **what permissions** exist
- **what action** should occur

---

## Communication Flow

```
┌─────────────┐
│   Domain A  │
└──────┬──────┘
       │  1. Discover capability
       ▼
┌─────────────┐
│   Domain B  │
└──────┬──────┘
       │  2. Authenticate identity
       ▼
┌─────────────────────┐
│  Exchange structured │
│      messages        │
└──────┬──────────────┘
       │  3. Response or Action
       ▼
┌─────────────┐
│   Result    │
└─────────────┘
```

---

## Identity and Trust

DCP defines three distinct identity types:

| Identity | Description | Example |
|----------|-------------|---------|
| **Domain Identity** | Organizations and services | `company.example` |
| **User Identity** | People or delegated entities | `user.identity` |
| **Agent Identity** | Autonomous systems acting with permission | `agent.identity` |

All communication carries clear identity, authorization, and accountability.

---

## Designed for the Agentic Internet

The internet is moving from:

```
Humans using software
```

towards:

```
Humans directing intelligent systems
```

AI agents should not communicate by pretending to be humans writing messages. They require native capabilities:

- Identity
- Permissions
- Structured communication
- Verification
- Negotiation
- Predictable responses

DCP provides a foundation for this future.

---

## Architecture

DCP follows a layered approach and focuses only on the **communication layer**:

```
┌────────────────────────────────┐
│        Application Layer       │
│  Business logic · UI · AI      │
├────────────────────────────────┤
│       Communication Layer      │  ← DCP
│  Messages · Requests ·         │
│  Responses · Capabilities      │
├────────────────────────────────┤
│         Identity Layer         │
│  Domains · Users · Agents ·    │
│  Authorization                 │
├────────────────────────────────┤
│         Transport Layer        │
│  Internet protocols            │
└────────────────────────────────┘
```

---

## Design Principles

**Simple** — A protocol should remain understandable for decades.

**Open** — No company or platform should control the standard.

**Stable** — The foundation should not depend on temporary technology trends.

**Interoperable** — Different systems should communicate regardless of implementation.

**Secure** — Identity and authorization are fundamental, not optional additions.

---

## What DCP Is

- A protocol specification
- A communication standard
- An interoperability layer
- An open foundation for future systems

DCP defines: domain discovery, message structure, identity exchange, authentication, authorization, and request/response patterns.

## What DCP Is Not

- An application or product
- A social network
- An email replacement
- A proprietary platform
- A framework or programming language

Implementations are free to use any technology while following the protocol specification.

---

## Roadmap

- [x] **Phase 1 — Specification** — Define protocol structure, discovery mechanism, message format, identity model, and security model
- [ ] **Phase 2 — Reference Examples** — Example domain manifests, messages, and communication scenarios
- [ ] **Phase 3 — Reference Implementations** — Minimal implementations demonstrating discovery, communication, validation, and interoperability
- [ ] **Phase 4 — Ecosystem Development** — Enable adoption across organizations, applications, services, and intelligent systems

---

## Why Now

The web connected information. APIs connected applications. The growth of automation, distributed services, and AI agents creates the need for a common communication foundation — one designed for systems talking to systems, not humans writing to humans.

```
Information
     │
Applications
     │
Services
     │
Agents
     │
Trusted Autonomous Communication
```

---

## Contributing

Contributions are welcome from people interested in:

- Internet architecture
- Distributed systems
- Security and digital identity
- Protocol design
- AI systems and future web standards

The foundation of the next internet should be open.

---

## Project Status

DCP is an open research and specification project. The goal is to explore and define a possible future communication standard for the internet.

> This specification is intentionally written in the style of IETF/W3C standards projects. It avoids implementation details and remains independent of current technology cycles.

---

*DCP — Open. Structured. Trusted.*
