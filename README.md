# StarterKit101

**Full-stack client intake, project management, and service-delivery platform**

StarterKit101 is a production-oriented web platform designed to support a service business from first contact through client onboarding and project delivery. The system combines a public marketing experience with internal workflow tools and a client-facing portal.

> The complete production source is maintained separately. This showcase documents the architecture, product decisions, engineering scope, and selected non-sensitive implementation details without exposing proprietary components.

## What the Project Solves

Service businesses often manage lead intake, staff workflows, client onboarding, files, communication, and project status across disconnected tools. StarterKit101 was designed to consolidate that experience into one coordinated platform.

The platform supports three distinct user experiences:

- **Public experience** — service discovery, marketing pages, and inquiry intake
- **Internal operations** — staff-facing inquiry and client workflow management
- **Client portal** — authenticated access to project information and shared files

## Engineering Scope

The project demonstrates work across:

- Frontend application architecture
- Responsive UI engineering
- Authentication and role-aware experiences
- Database-backed workflow design
- File storage and client access patterns
- Serverless / edge-function integrations
- Transactional email workflows
- Multi-application monorepo organization
- Production deployment configuration

## Technology Stack

| Area | Technology |
| --- | --- |
| Frontend | React 18, Vite 5 |
| Styling | Tailwind CSS |
| Routing | React Router |
| Backend platform | Supabase |
| Data | PostgreSQL |
| Authentication | Supabase Auth |
| File storage | Supabase Storage |
| Server-side workflows | Supabase Edge Functions |
| Email | Resend |
| Scheduling integration | Cal.com |
| Package management | pnpm workspaces |
| Deployment | Render |

## Architecture Overview

```text
                    ┌─────────────────────┐
                    │   Public Website    │
                    │  Marketing / Intake │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Backend Services  │
                    │ Auth / Data / Files │
                    └───────┬─────┬───────┘
                            │     │
                 ┌──────────┘     └──────────┐
                 ▼                           ▼
       ┌──────────────────┐        ┌──────────────────┐
       │ Staff Dashboard  │        │  Client Portal   │
       │ Ops + Workflows  │        │ Projects + Files │
       └──────────────────┘        └──────────────────┘
```

The production implementation uses separate frontend applications sharing a common backend platform. This separation allows the public, staff, and client experiences to evolve independently while relying on the same core data and authentication layer.

## Key Features

### Public Experience

- Responsive service-oriented landing experience
- Multiple service pages
- Lead / inquiry intake
- Theme support
- Rich visual presentation and interactive media
- Scheduling integration

### Internal Operations

- Authenticated staff experience
- Inquiry search and filtering
- Status-oriented workflow management
- Responsive desktop/mobile presentation
- Staff notes and client-management workflows
- Data export capability

### Client Experience

- Authenticated client portal
- Onboarding flow
- Project overview and status visibility
- Secure file-management experience
- Account/session management

### Workflow Automation

The production platform includes server-side workflow automation for activities such as client onboarding, notifications, and email-based interactions. Detailed implementation and security-sensitive logic are intentionally excluded from this public showcase.

## Product and Engineering Decisions

### Monorepo Organization

The project is organized as a multi-application workspace so the marketing site, internal dashboard, and client portal can be developed and deployed as separate surfaces while remaining part of one product ecosystem.

### Role-Aware Product Design

Different interfaces are provided for public users, staff, and clients instead of forcing all users through a single generalized application shell.

### Managed Backend Services

A managed backend stack was selected to accelerate development of authentication, relational data, file storage, and server-side workflows while keeping the frontend applications independently deployable.

### Responsive Operations UI

The staff workflow experience was designed for both desktop and smaller screens so inquiry and client operations are usable outside of a traditional office setup.

## My Contributions

I designed and developed the platform architecture and product experience across the public website, internal operations workflow, and client-facing portal.

My work includes:

- Product architecture and technical planning
- Frontend application development
- Responsive interface design
- Authentication and user-flow implementation
- Backend service integration
- Workflow and data-model design
- Client onboarding flows
- File-management integration
- Deployment and production configuration
- Iterative feature development and debugging

## Development Status

**Active development / production-oriented project**

The platform has moved beyond a static prototype and includes working multi-user application flows, backend integrations, authenticated experiences, and deployed frontend surfaces. Additional workflow refinement, testing, observability, and product expansion remain ongoing.

## Selected Engineering Highlights

- Multi-app React architecture managed through pnpm workspaces
- Separation of public, internal, and authenticated client experiences
- Role-aware application flows
- Database-backed inquiry and client workflows
- Authenticated file-management system
- Server-side onboarding and notification workflows
- Responsive internal operations UI
- Deployment of independent frontend surfaces

## Security and Source-Code Disclosure

The production codebase contains proprietary product logic and security-sensitive backend implementation and is **not included in this portfolio repository**.

This showcase intentionally excludes:

- API keys and credentials
- Environment files
- Database credentials
- Service-role credentials
- Internal database schema details
- Production backend functions
- Private URLs and administrative endpoints
- Client/customer data
- Proprietary workflow logic

Selected sanitized implementation samples may be added later where they provide useful evidence of engineering ability without exposing production internals.

## Live Product

Public-facing product experience: https://starterkit101.com

Access to internal staff and client-only surfaces is intentionally restricted.

## Known Limitations / Next Steps

Current engineering priorities include:

- Expanded automated testing
- Additional operational observability
- Continued accessibility review
- Further workflow automation
- Shared component-library maturation
- Continued security hardening

## Why This Repository Is a Showcase

This repository is intended for recruiters, engineering managers, collaborators, and technical reviewers who want to understand the scope and architecture of the project without requiring public disclosure of the full proprietary application.

For deeper technical evaluation, additional sanitized code samples or controlled private-code review can be provided when appropriate.
