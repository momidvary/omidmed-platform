# OmidMed Platform - Business Flow

## Product Definition

OmidMed Platform is a SaaS platform for physiotherapy clinics.

The first MVP is an online ordering system for OmidMed products.

Future modules include clinic management, finance, patients, insurance, and AI physiotherapy assistant.

---

## Main Website

omidmed.com

Purpose:
- Brand introduction
- Product information
- Marketing
- Link to clinic panel

The WordPress website must not be modified by this application.

---

## Application

app.omidmed.com

Purpose:
- Clinic login
- Product ordering
- Custom package building
- Logo upload
- Product preview
- Invoice and order tracking

---

## User Roles

### 1. Super Admin

OmidMed factory owner/admin.

Can:
- Manage clinics
- Manage products
- Manage prices
- Manage orders
- Approve uploaded logos
- Update production status
- View invoices
- View payments

### 2. Clinic User

Physiotherapy clinic customer.

Can:
- Register/login
- View products
- Build custom order
- Upload logo
- See preview
- Submit order
- View invoice
- Track order status

---

## Clinic Order Flow

1. Clinic enters app.omidmed.com
2. Clinic logs in or registers
3. Clinic sees dashboard
4. Clinic chooses product type:
   - Physiotherapy pad
   - Disposable sheet
   - Clinic bag
   - Complete clinic pack
5. Clinic selects options:
   - Pad model
   - Bag color
   - Sheet color
   - Quantity
   - Logo printing option
6. Clinic uploads logo
7. System shows product preview
8. Clinic reviews price
9. Clinic submits order
10. System creates order
11. System creates invoice
12. Clinic tracks order status

---

## AI Product Preview Flow

1. Clinic uploads logo
2. Clinic selects bag color
3. Clinic selects print position
4. System creates a preview mockup
5. Clinic confirms preview
6. Admin reviews artwork before production

MVP note:
The first version can use a simple mockup generator.
Real AI image generation can be added later.

---

## Admin Production Flow

1. Admin receives new order
2. Admin reviews clinic details
3. Admin reviews logo/artwork
4. Admin confirms price
5. Admin changes status to Approved
6. Order enters production
7. Admin updates production status:
   - Submitted
   - Under Review
   - Approved
   - In Production
   - Ready To Ship
   - Shipped
   - Delivered
   - Cancelled
8. Clinic sees updated status in dashboard

---

## Payment Flow

MVP:
- Manual payment tracking
- Admin records payment manually

Future:
- Online payment gateway
- Partial payments
- Outstanding balance
- Credit limit per clinic

---

## Holo Data Flow

Existing customer data exists in Holo accounting software.

Migration flow:

Holo
↓
Excel / CSV Export
↓
Data cleaning
↓
Import script
↓
Supabase database

Important:
- Do not connect directly to Holo in MVP.
- Import clinics by phone number.
- Prevent duplicate clinics.
- Keep purchase history for future CRM.

---

## Future Modules

Do not implement now.

Future modules:
- Clinic CRM
- Patient management
- Insurance management
- Clinic finance
- Inventory management
- AI physiotherapy assistant
- SOAP note generator
- Exercise prescription
- Treatment plan generator
- Patient progress dashboard

---

## MVP Boundary

The MVP must only include:

- Clinic account
- Product catalog
- Custom ordering
- Logo upload
- Product preview
- Invoice
- Order tracking
- Admin order management

Everything else is future roadmap.