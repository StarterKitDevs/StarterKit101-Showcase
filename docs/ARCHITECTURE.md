# Architecture Case Study

## System Shape

StarterKit101 is structured as a multi-surface web product rather than a single-page marketing site. The product separates public acquisition, internal operations, and authenticated client experiences while using a shared backend-services layer.

```text
Public Application
  ├─ Marketing / service discovery
  ├─ Inquiry intake
  └─ Scheduling entry points
            │
            ▼
Shared Backend Services
  ├─ Authentication
  ├─ Relational data
  ├─ File storage
  └─ Server-side workflows
       │              │
       ▼              ▼
Staff Application   Client Application
  ├─ Inquiries        ├─ Onboarding
  ├─ Workflow state   ├─ Project status
  ├─ Client records   └─ Files
  └─ Operations
```

## Frontend Architecture

The production project uses React-based frontend applications built with Vite and managed through a pnpm workspace. Separating the major product surfaces provides clearer boundaries between acquisition, operations, and client-facing functionality.

This approach supports:

- Independent UI evolution
- Clearer role boundaries
- Smaller conceptual application surfaces
- Independent deployment where appropriate
- Shared product conventions without forcing all users into one interface

## Backend Architecture

Supabase provides managed backend capabilities for the production system, including authentication, PostgreSQL-backed data, file storage, and server-side functions.

Security-sensitive details such as production policies, schema internals, privileged credentials, and proprietary workflow implementation are deliberately omitted from this public case study.

## Workflow Architecture

A typical product workflow can move through the following lifecycle:

```text
Visitor
  ↓
Inquiry
  ↓
Internal Review
  ↓
Client Onboarding
  ↓
Authenticated Client Access
  ↓
Project / File / Status Workflow
```

The value of the architecture is not simply the individual screens; it is the coordination of multiple user roles around one service-delivery lifecycle.

## Integration Layer

The system uses external services where specialized infrastructure is preferable to rebuilding commodity capabilities. Examples include transactional email and scheduling integrations.

Integration credentials, webhook secrets, private endpoints, and implementation-specific business rules are not published here.

## Deployment

The application surfaces are designed to be deployable independently. Production deployment configuration exists in the private source repository. This public case study intentionally documents the deployment model without reproducing sensitive configuration.

## Engineering Tradeoffs

### Managed backend vs. custom API server

Using managed authentication, database, storage, and serverless capabilities reduced infrastructure overhead and allowed more development effort to focus on product workflows. The tradeoff is tighter coupling to the backend platform, which is managed by maintaining clean application boundaries and avoiding unnecessary leakage of backend-specific details throughout the UI.

### Multiple applications vs. one role-switched application

Separate applications increase deployment and workspace complexity, but provide stronger separation between public acquisition, internal operations, and client-facing workflows. For this product, the separation is useful because the audiences and interaction models are substantially different.

### Public portfolio vs. production source

The production system is proprietary. This repository therefore documents architecture, product decisions, and engineering scope without publishing the implementation that creates the product's commercial or security-sensitive value.
