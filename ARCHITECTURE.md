# OmidMed Platform - Architecture Blueprint

## 1. Architecture Goal

OmidMed Platform must be built as a long-term SaaS platform for physiotherapy clinics.

The first module is product ordering, but the core architecture must support future modules such as clinic CRM, patient management, finance, insurance, inventory, and AI physiotherapy assistant.

The system must not be designed as a simple online shop.

It must be designed as a modular clinic operating platform.

---

## 2. System Structure

Main website:

omidmed.com

Current technology:

WordPress

Purpose:

- Marketing
- SEO
- Product introduction
- Brand trust
- Link to SaaS panel

Application:

app.omidmed.com

Purpose:

- Clinic dashboard
- Product ordering
- Logo upload
- Product preview
- Order tracking
- Admin management

Rule:

The WordPress website and SaaS application must stay separate.

---

## 3. Core Architecture Domains

The platform is divided into these domains:

### 3.1 Identity Domain

Responsible for:

- Authentication
- User accounts
- Roles
- Permissions
- Admin users
- Clinic users

Main roles:

- Super Admin
- Clinic Owner
- Clinic Staff

---

### 3.2 Clinic Domain

Responsible for:

- Clinic profile
- Clinic users
- Clinic logo
- Clinic address
- Clinic contact information
- Clinic purchase history

Important rule:

Clinic is the center of the system.

Most future modules will connect to clinic.

---

### 3.3 Commerce Domain

Responsible for:

- Products
- Product categories
- Product variants
- Colors
- Pricing
- Orders
- Order items
- Discounts
- Invoices

The MVP mainly belongs to this domain.

---

### 3.4 Production Domain

Responsible for:

- Order approval
- Logo/artwork review
- Production status
- Packaging status
- Shipping status

Production statuses:

- Submitted
- Under Review
- Approved
- In Production
- Ready To Ship
- Shipped
- Delivered
- Cancelled

---

### 3.5 Finance Domain

Responsible for:

- Invoice status
- Manual payment tracking
- Payment history
- Outstanding balance

MVP rule:

Online payment gateway is not required in MVP.

---

### 3.6 Media Domain

Responsible for:

- Logo uploads
- Product images
- Invoice PDFs
- Preview images
- Artwork files

Storage:

Use Supabase Storage.

---

### 3.7 AI Domain

Responsible for:

- AI Product Preview in MVP
- Future AI physiotherapy assistant
- Future SOAP note generation
- Future treatment assistant

MVP AI rule:

AI Product Preview can start as a smart mockup generator.

Real AI image generation is future.

---

### 3.8 Notification Domain

Responsible for future:

- SMS
- Email
- WhatsApp/Bale notifications
- Order status updates

MVP rule:

Notification system can be prepared but not fully implemented.

---

### 3.9 Analytics Domain

Responsible for future:

- Sales reports
- Clinic activity
- Product demand
- Reorder predictions
- Revenue dashboard

---

## 4. Multi-Tenant Architecture

The system must be multi-tenant.

Each clinic is a tenant.

Rules:

- Every clinic user belongs to one clinic.
- Clinic users can only see their own clinic data.
- Super Admin can see all clinics.
- Important tables must include clinic_id when related to clinic data.
- Future patient, finance, treatment, and AI modules must also be clinic-scoped.

This prevents data mixing between clinics.

---

## 5. Recommended Technology Stack

Frontend:

- Next.js
- React
- TypeScript
- Tailwind CSS
- ShadCN UI

Backend:

MVP preferred approach:

- Next.js API routes or server actions for simple MVP

Future scalable approach:

- NestJS backend service if complexity increases

Database:

- Supabase PostgreSQL

Authentication:

- Supabase Auth

Storage:

- Supabase Storage

Version control:

- GitHub

Deployment:

- Vercel for frontend/app
- Supabase for database/auth/storage
- Docker for local development and future server deployment

---

## 6. Important Architecture Decision

For MVP, avoid unnecessary complexity.

Do not build separate microservices.

Do not build complex backend before the product flow is validated.

Start with a modular monolith.

Recommended MVP architecture:

- One Next.js application
- Supabase as backend service
- PostgreSQL database
- Supabase Auth
- Supabase Storage

This is faster, simpler, and enough for the first version.

Future migration to NestJS is possible if needed.

---

## 7. Folder Architecture

Recommended project structure:

apps/
  web/

packages/
  ui/
  types/
  config/

database/
  migrations/
  seed/
  imports/

docs/

prompts/

skills/

scripts/

assets/

design/

---

## 8. Data Ownership Rules

Clinic-owned data:

- Clinic profile
- Clinic users
- Orders
- Uploaded logos
- Invoices
- Payments
- Future patients
- Future treatment records

Admin-owned data:

- Product catalog
- Product categories
- Product pricing
- Production statuses
- Global settings

Shared data:

- Product list
- Public product images
- Available colors
- Available variants

---

## 9. Security Rules

- Never store passwords manually.
- Use Supabase Auth.
- Never commit API keys.
- Use environment variables.
- Enable Row Level Security in Supabase.
- Use clinic_id for tenant isolation.
- Admin access must be role-protected.
- Uploaded files must be connected to clinic_id.
- Order changes must be logged.

---

## 10. MVP Architecture Boundary

MVP includes:

- Authentication
- Clinic profile
- Product catalog
- Custom order builder
- Logo upload
- Product preview
- Order management
- Invoice generation
- Admin order management

MVP does not include:

- Patient management
- AI treatment assistant
- Insurance
- Accounting
- Inventory
- Online payment
- Mobile app

---

## 11. Future Expansion Rule

Every new module must follow the same domain structure.

Before adding any future module, define:

- Domain
- Data ownership
- Roles
- Database tables
- API boundaries
- UI pages
- Security rules

No future module should be added directly without architecture review.

---

## 12. Key Architecture Principle

Clinic is the center of the platform.

Orders, patients, finance, AI, treatments, and reports must be connected to the clinic.

This allows OmidMed Platform to grow from an ordering system into a full physiotherapy clinic operating system.