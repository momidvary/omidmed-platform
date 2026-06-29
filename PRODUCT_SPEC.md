# OmidMed Platform - Product Specification

## 1. Product Vision

OmidMed Platform is the digital operating system for physiotherapy clinics.

It starts as a smart B2B ordering platform for physiotherapy consumables, but it is designed to gradually become a complete clinic management and AI assistant platform.

The first business advantage is that OmidMed already has real clinic customers, real products, real purchase history, and real operational pain points.

The platform must not be built as a simple online shop.

It must be built as a scalable clinic platform where ordering products is the first module.

---

## 2. Main Website and Application Structure

### Main Website

Domain:

omidmed.com

Current system:

WordPress

Purpose:

- Brand introduction
- Public product information
- SEO content
- Marketing
- Trust building
- Link to clinic panel

Rule:

The WordPress website must not be changed by the SaaS application.

---

### SaaS Application

Domain:

app.omidmed.com

Purpose:

- Clinic login
- Product ordering
- Custom package builder
- Logo upload
- Product preview
- Invoice
- Order tracking
- Future clinic management modules

---

## 3. Product Positioning

OmidMed Platform is not only an e-commerce system.

It is a specialized SaaS platform for physiotherapy clinics.

The MVP focuses on:

- Ordering products
- Customizing clinic packs
- Uploading clinic logo
- Previewing printed products
- Tracking orders

Future versions will add:

- Clinic CRM
- Patient management
- Financial management
- Insurance management
- AI physiotherapy assistant
- Treatment planning
- Exercise prescription
- SOAP notes
- Inventory management

---

## 4. Target Users

### 4.1 Clinic Owner

Usually owns or manages a physiotherapy clinic.

Needs:

- Fast ordering
- Clear pricing
- Product customization
- Invoice access
- Order tracking
- Purchase history
- Simple mobile-friendly interface

Pain points:

- Ordering through phone or WhatsApp is slow
- Product details are forgotten
- Logo files get lost
- Prices change
- Reordering is manual

---

### 4.2 Clinic Staff

May order products on behalf of the clinic.

Needs:

- Easy product selection
- Simple repeat order
- No complicated software
- Fast confirmation

---

### 4.3 OmidMed Admin

Factory owner or internal staff.

Needs:

- Manage products
- Manage prices
- See orders
- Approve artwork
- Track production
- Track payments
- Manage clinics

---

### 4.4 Future User: Physiotherapist

Will use future clinical modules.

Future needs:

- Patient records
- Exercise plans
- Treatment notes
- AI assistant
- SOAP note generation
- Insurance and finance support

---

## 5. MVP Scope

The MVP must include only the following:

### Clinic Side

- Register / login
- Clinic profile
- Product catalog
- Custom order builder
- Bag color selection
- Sheet color selection
- Pad model selection
- Quantity selection
- Logo upload
- Product preview
- Price calculation
- Submit order
- View invoice
- Track order status
- View order history

### Admin Side

- Login
- Admin dashboard
- Manage clinics
- Manage products
- Manage product variants
- Manage colors
- Manage pricing
- View orders
- Approve orders
- Review uploaded logo
- Update production status
- Record payments manually
- View invoices

---

## 6. Out of Scope for MVP

Do not build these in MVP:

- AI treatment assistant
- Patient management
- Insurance management
- Accounting system
- Inventory system
- Online payment gateway
- Mobile app
- Advanced CRM
- Exercise prescription
- SOAP notes

These must be documented as future modules only.

---

## 7. Core MVP Modules

### 7.1 Authentication

Users must login securely.

Roles:

- Super Admin
- Clinic Owner
- Clinic Staff

Rules:

- Clinic users only see their own clinic data.
- Admin can see all data.
- Passwords must never be stored manually.
- Use Supabase Auth.

---

### 7.2 Clinic Dashboard

After login, clinic user sees:

- New order button
- Recent orders
- Order statuses
- Invoices
- Announcements
- Quick reorder option in future

Dashboard must be simple, Persian, RTL, and mobile-friendly.

---

### 7.3 Product Catalog

Products include:

- Physiotherapy pads
- Disposable sheets
- Clinic bags
- Complete physiotherapy packs
- Other consumables

Each product can have:

- Name
- Category
- Description
- Image
- Base price
- Variants
- Colors
- Size
- Stock status
- Active/inactive status

---

### 7.4 Custom Order Builder

The order builder is the heart of MVP.

Clinic selects:

- Product type
- Product model
- Bag color
- Sheet color
- Pad model
- Quantity
- Logo printing option
- Notes

The system calculates price live.

The order flow must be maximum 3 steps:

1. Choose products
2. Customize
3. Review and submit

---

### 7.5 Logo Upload

Clinic can upload logo files.

Allowed formats:

- PNG
- JPG
- SVG
- PDF

Future optional formats:

- AI
- EPS

Rules:

- Store files in Supabase Storage.
- Keep original uploaded file.
- Show preview.
- Admin must review before production.

---

### 7.6 AI Product Preview

This is a key differentiator.

Goal:

When clinic uploads logo and selects bag color, the system shows how the logo may look on the selected bag.

MVP version:

- Use mockup-based preview.
- Place uploaded logo on bag template.
- Allow basic position preview.
- Show selected bag color.

Future version:

- AI-generated realistic preview.
- Multiple angles.
- Print quality warning.
- Logo contrast recommendation.
- Suggested best bag color based on logo.

Important:

This feature is called AI Product Preview, but MVP can start with smart mockup generation.

---

### 7.7 Order Management

Order statuses:

- Draft
- Submitted
- Under Review
- Approved
- In Production
- Ready To Ship
- Shipped
- Delivered
- Cancelled

Clinic can see status.

Admin can change status.

Every status change must be logged.

---

### 7.8 Invoice System

MVP invoice:

- Invoice number
- Clinic name
- Order items
- Quantity
- Unit price
- Total price
- Discount
- Final amount
- Payment status

Payment status:

- Unpaid
- Partially Paid
- Paid

MVP payment is manual.

Online payment is future.

---

## 8. Holo Data Migration

OmidMed has existing customer and purchase data in Holo accounting software.

MVP migration strategy:

Holo → Excel/CSV → Cleaning → Import Script → Supabase

Data to import:

- Clinic name
- Phone number
- City
- Address
- Purchase history
- Products purchased
- Order amount
- Last purchase date

Rules:

- Do not connect directly to Holo in MVP.
- Phone number should be the main duplicate detection field.
- Preserve purchase history for future CRM.
- Allow manual correction after import.

---

## 9. Design Principles

The product must feel:

- Professional
- Medical
- Simple
- Trustworthy
- Fast
- Mobile-friendly

UI requirements:

- Persian first
- RTL first
- English-ready
- Clean dashboard
- Minimal steps
- Large buttons
- Clear pricing
- No confusing technical terms

---

## 10. Architecture Principles

The system must be designed as a long-term platform.

Rules:

- Modular architecture
- Multi-tenant clinic-based data
- Role-based access control
- API-first design
- TypeScript everywhere
- PostgreSQL database
- Supabase Auth
- Supabase Storage
- Scalable for future AI modules

---

## 11. Future Platform Modules

Future modules must be designed but not implemented in MVP.

### Phase 2

- Better admin dashboard
- Production management
- Manual payment tracking
- Customer segmentation
- Repeat order reminders

### Phase 3

- Clinic CRM
- Purchase prediction
- Automatic reorder suggestions
- SMS reminders

### Phase 4

- Patient management
- Treatment sessions
- Exercise library
- SOAP notes

### Phase 5

- AI physiotherapy assistant
- Diagnosis support
- Treatment plan assistant
- Insurance documentation support
- Clinic management AI copilot

---

## 12. Success Criteria for MVP

MVP is successful when:

- A clinic can login
- A clinic can create an order
- A clinic can upload logo
- A clinic can preview logo on bag
- A clinic can submit order
- Admin can see order
- Admin can approve order
- Admin can update production status
- Clinic can track status
- Invoice is generated

---

## 13. Product Catalog Engine

OmidMed Platform must not be designed only for clinic hygiene packs.

The platform must support all current and future physiotherapy products.

Examples:

- Hygiene packs
- Physiotherapy pads
- Disposable sheets
- Spunbond bags
- Gel
- Cables
- Electrodes
- Needles
- Mechanotherapy consumables
- Devices
- Other physiotherapy supplies

### Product Structure

Every product can have:

- Category
- Brand
- Model
- Variant
- Size
- Color
- Material
- Unit
- Minimum order quantity
- Base price
- Images
- Stock status
- Active/inactive status
- Custom options
- Attachments
- Notes

### Example: Spunbond Bag

Category: Bag  
Material: Spunbond  
Size: 30×40  
Handle Type:
- Punch handle
- Handle bag
- D-cut handle

Color:
- Black
- Navy
- Burgundy
- Coffee
- Cream
- White
- Custom colors

Printing:
- No print
- One-color silk print
- Two-color print
- Logo print

### Example: Physiotherapy Pad

Category: Pad  
Variant:
- Spanish pad
- Chinese pad
- French pad

Size:
- 6×8
- Other sizes

Options:
- Single-side leather
- Double-side leather

### Important Rule

The system must support adding new products without changing the core code.

Admins should be able to add new categories, products, variants, colors, and options from the admin panel.

The product catalog must be flexible enough to support at least 3000 products in the future.
