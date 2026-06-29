# OmidMed Platform - Claude Instructions

## Project Identity

OmidMed Platform is a long-term SaaS platform for physiotherapy clinics.

The first MVP module is a B2B ordering system for OmidMed physiotherapy consumables.

Main website:
omidmed.com

Application:
app.omidmed.com

The main website is WordPress and must not be modified by this project.

## Business Context

OmidMed produces and sells physiotherapy consumables, including:

- Physiotherapy pads
- Disposable patient sheets
- Clinic bags
- Custom clinic hygiene packs
- Other physiotherapy consumables

Clinics must be able to order customized products online.

## MVP Scope

The MVP must include:

- Clinic login
- Clinic dashboard
- Product catalog
- Custom order builder
- Bag color selection
- Sheet color selection
- Pad model selection
- Logo upload
- AI-assisted product preview
- Order submission
- Invoice generation
- Order tracking
- Admin panel for OmidMed factory

## Important AI Preview Feature

Clinics should upload their logo and choose product options.

The system should show a realistic preview of the logo on the selected bag color.

This is called: AI Product Preview.

For MVP, this can start as a simulated preview or mockup generator.
Later it can become a real AI image generation feature.

## Future Roadmap

Future modules may include:

- Clinic CRM
- Patient management
- Clinic financial management
- Insurance management
- Inventory management
- AI physiotherapy assistant
- Treatment planning
- SOAP notes
- Exercise prescription
- Patient progress tracking

Do not implement future modules in MVP unless explicitly requested.

## Technical Direction

Use:

- Next.js for frontend
- TypeScript everywhere
- Tailwind CSS
- ShadCN UI
- Supabase PostgreSQL
- Supabase Auth
- Supabase Storage
- Docker where needed
- GitHub for version control

## Architecture Rules

- Build incrementally.
- Do not generate the full project at once.
- Do not modify unrelated files.
- Do not delete existing files without confirmation.
- Always keep the project production-ready.
- Every feature must be documented.
- Persian RTL support is required.
- Mobile-first UI is required.
- The system must be designed for future expansion.

## Security Rules

- Never commit secrets.
- Never store passwords manually.
- Use environment variables for keys.
- Use role-based access control.
- Separate clinic data by clinic account.
- Admin and clinic users must have different permissions.

## Current Phase

Phase 1:
Project foundation and MVP ordering system.

Do not build AI assistant, CRM, accounting, patient management, or insurance modules yet.

## Working Style

When asked to work on this project:

1. Understand the current phase.
2. Make the smallest safe change.
3. Explain what changed.
4. Update documentation if needed.
5. Wait for the next instruction.