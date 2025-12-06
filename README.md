# 📘 **FlowTrack – Simple Order & Customer Tracking App**

FlowTrack is a fast, mobile-first web application built for WhatsApp & Instagram–driven small businesses.
It helps owners track orders, customers, payments, workflow stages, and exports — all in just a few taps.

---

## 🚀 **Features**

### ✔ Order Management
- Add orders in under **10 seconds**
- Order workflow: New → In Progress → Completed → Paid
- Track payment status, mode, and date
- Prevent invalid transitions (e.g., "Paid" without payment info)

### ✔ Customer Management
- Auto-create customer profiles when logging orders
- View customer history, total orders, lifetime value
- Notes for special customer information
- Pending payment aggregation

### ✔ Dashboard
- Weekly revenue & order KPIs
- Top customers (last 30 days)
- Recent orders
- Pending payments summary
- Optimized for **mobile-first usage**

### ✔ Pending Payments View
- Sort by highest amount or oldest overdue
- Quick access to follow-up items

### ✔ Data Export
- Export Orders → CSV
- Export Customers → CSV
- Excel-friendly formatting

### ✔ Authentication
- Email + Password login
- Secure sessions (Express + PostgreSQL store)

---

## 🛠️ **Tech Stack**

### Frontend
- React 18
- Wouter (routing)
- React Hook Form + Zod
- Radix UI components
- TanStack Query
- TailwindCSS + Animations
- Recharts (analytics)

### Backend
- Node.js + Express
- PostgreSQL
- Drizzle ORM
- Passport Local authentication
- Express-session + connect-pg-simple

### Tooling
- Vite
- TypeScript
- PostCSS + Autoprefixer
- TSX development runtime

---

## 📂 **Project Structure**

    client/src/        → React app (UI, components, pages)
    server/            → Express backend (routes, controllers)
    shared/            → Zod schemas, shared types & utilities
    drizzle/           → ORM configs, migrations
    public/            → Static assets

---

## ⚙️ **Available Scripts**

    npm run dev        → Start development server (Express + React)
    npm run build      → Build production server bundle
    npm start          → Run production build
    npm run check      → TypeScript type-check
    npm run db:push    → Apply Drizzle migrations

---

## 📦 **Installation**

Clone the repository:

    git clone https://github.com/srijitsrajput-glitch/FlowTrack
    cd FlowTrack

Install dependencies:

    npm install

Create a `.env` file and add:

    DATABASE_URL=postgres://user:password@host:port/db
    SESSION_SECRET=your_secret_key
    NODE_ENV=development

---

## ▶️ **Run in Development**

    npm run dev

Runs Express backend + Vite frontend in unified dev environment.

---

## 🚀 **Build & Run in Production**

    npm run build
    npm start

---

## 🗄️ **Database & Migrations (Drizzle ORM)**

Apply schema changes:

    npm run db:push

---

## 🎨 **Design System**

FlowTrack UI is built with:
- Mobile-first layouts
- Large touch targets (44–56px)
- Clean spacing + hierarchy
- Inter font
- Radix UI components
- Tailwind styling
- Clear status indicators
- Bottom navigation on mobile

---

## 📚 **Core User Flows**

### 1. Add New Order
- Enter name, phone, channel, items, amount
- Auto-create customer if not found
- Order starts as **New**

### 2. Update Workflow Status
- Move through defined statuses
- Prevent invalid transitions
- Payment info required to mark as **Paid**

### 3. View Customer Details
- Customer profile
- Total orders, total paid, outstanding
- Notes + order history

### 4. Pending Payments
- Overdue sorting
- Prioritized follow-ups

### 5. Dashboard Analytics
- Weekly metrics
- Top customers
- Pending payment summary
- Optional 7-day order graph

### 6. Export to CSV
- Clean formatting
- Compatible with Excel and Google Sheets

---

## 🧪 **Acceptance Criteria**
- Order creation in <15 seconds
- Status transitions fully enforced
- Customer history aggregates correctly
- CSV exports accurate
- Loads in <2 seconds on 4G
- Runs smoothly on low-end Android devices

---

## 🛣️ **Roadmap**
- Drag-and-drop Kanban board
- Real-time updates via WebSockets
- Customer merge tool
- Frequently ordered item templates
- Multi-user support
- WhatsApp Business API integration (if permissible)

---

## 📝 **License**
MIT License.
