# FlowTrack Design Guidelines

## Design Approach

**Selected Framework:** Material Design principles adapted for productivity, with Linear-inspired typography and spacing for efficient workflows.

**Rationale:** FlowTrack is a utility-focused productivity tool requiring mobile-first optimization, clear status visualizations, and fast data entry. Material Design provides excellent mobile patterns and visual feedback systems while Linear's minimalist approach ensures efficiency.

**Core Principles:**
- Touch-first interaction (minimum 44px tap targets)
- Instantaneous visual feedback for all actions
- Information density balanced with breathing room
- Clear workflow visualization through status indicators

---

## Typography

**Font Family:** Inter (via Google Fonts CDN)
- Primary: Inter for all UI text
- Fallback: system-ui, -apple-system, sans-serif

**Type Scale:**
- **Headings (H1):** text-2xl (24px), font-semibold, tracking-tight
- **Headings (H2):** text-xl (20px), font-semibold
- **Headings (H3):** text-lg (18px), font-medium
- **Body Large:** text-base (16px), font-normal - for primary content, form labels
- **Body:** text-sm (14px), font-normal - for secondary text, descriptions
- **Caption/Meta:** text-xs (12px), font-normal - for timestamps, helper text
- **Buttons:** text-sm (14px), font-medium, uppercase tracking

**Mobile Optimization:** All font sizes are optimized for readability on small screens. No reduction needed for mobile viewports.

---

## Layout System

**Spacing Primitives:** Use Tailwind units of **2, 4, 6, 8, 12, 16**
- Micro spacing (2, 4): Between related elements, icon-text gaps
- Component spacing (6, 8): Card padding, form field gaps
- Section spacing (12, 16): Page margins, section breaks

**Grid System:**
- Mobile (base): Single column, full-width with px-4 container padding
- Tablet (md:): Two columns where appropriate (customer cards, stats)
- Desktop (lg:): Maximum 3 columns for dashboard widgets

**Container Constraints:**
- Max width: max-w-7xl for dashboard layouts
- Forms: max-w-md centered for focused data entry
- Lists: Full width for scannable order/customer lists

**Touch Targets:**
- Minimum: h-12 (48px) for all interactive elements
- Buttons: h-12 on mobile, h-10 on desktop
- Form inputs: h-14 (56px) for comfortable thumb typing
- List items: min-h-16 for tap accuracy

---

## Component Library

### Navigation
**Mobile Bottom Navigation** (fixed bottom bar)
- 4 primary tabs: Dashboard, Orders, Customers, More
- Icons + labels, h-16, active state with indicator
- Always visible, persistent across views

**Header Bar**
- h-14, fixed top, shows current page title
- Left: Back button (when nested)
- Right: Action buttons (Add Order, Export, Settings)

### Forms (Critical Component)
**Layout:** Vertical stack, full-width fields, generous spacing (gap-6)

**Text Inputs:**
- Height: h-14, rounded-lg, border-2
- Label: text-sm, font-medium, mb-2
- Padding: px-4
- Focus state: border width increase, subtle glow

**Select Dropdowns:**
- Native select styled, h-14, matches text input styling
- Large chevron icon for touch accuracy

**Submit Buttons:**
- Full-width on mobile (w-full)
- h-12, rounded-lg, font-medium
- Loading spinner replaces text during submission

**Validation:**
- Inline error messages below fields (text-sm)
- Error state: border treatment, clear messaging

### Order Cards
**Layout:** Vertical card with clear information hierarchy
- Border: border-l-4 for status indication (width only, no color ref)
- Padding: p-4
- Min-height: min-h-24
- Gap between elements: gap-2

**Content Structure:**
- Row 1: Customer name (text-base, font-semibold) + Amount (text-lg, font-bold, right-aligned)
- Row 2: Phone + Channel badge (text-sm)
- Row 3: Items preview (text-sm, truncate)
- Row 4: Status badge + Payment badge + Date (text-xs)

**Status Badges:**
- Pill shape: px-3, py-1, rounded-full, text-xs, font-medium
- Clear labeling (NEW, IN PROGRESS, COMPLETED, PAID)

### Dashboard Cards
**Stat Cards:**
- Square aspect on mobile, rectangular on desktop
- Padding: p-6
- Border: border-2, rounded-xl
- Layout: Icon top, Value (text-3xl, font-bold), Label (text-sm)

**Recent Orders List:**
- Simplified card layout, h-20 per item
- Swipeable on mobile for quick actions

### Customer List
**List Items:**
- Height: h-20, border-b
- Left: Avatar circle (h-12, w-12) with initials
- Center: Name (text-base, font-medium) + Phone (text-sm)
- Right: Order count badge + chevron

**Search Bar:**
- Sticky top position below header
- h-12, rounded-full, icon-left design

### Pending Payments View
**Layout:** Sortable list with prominent amounts
- Amount displayed largest (text-xl, font-bold)
- Days overdue indicator (badge, attention-grabbing)
- Tap to expand for payment options

### Export Buttons
- Secondary button style: outlined, not filled
- Icon + label: "Export Orders" / "Export Customers"
- Positioned in page header or settings

### Empty States
**Structure:**
- Centered vertically in viewport
- Icon (h-20, w-20), Heading (text-lg), Subtext (text-sm), CTA button
- Friendly, encouraging messaging

### Loading States
- Skeleton screens for lists (shimmer effect)
- Spinner for buttons (size-4, inline)
- Full-page loader for initial data fetch

---

## Interaction Patterns

**Primary Actions:**
- Floating Action Button (FAB): Bottom-right, h-14, w-14, rounded-full
- Used for "Add Order" on Orders view
- Clear icon, elevated shadow

**Status Workflow:**
- Horizontal stepper visualization for order stages
- Tap to change status with confirmation modal

**Drag & Drop (Optional Desktop Enhancement):**
- Kanban board for order status management
- Not required for mobile MVP

**Pull-to-Refresh:**
- Standard mobile pattern for data updates

---

## Images

**No hero images required** - This is a utility application, not a marketing site.

**Avatar Placeholders:**
- Customer initials in circular containers
- Use for customer list items

**Empty State Illustrations:**
- Simple line icons (via Heroicons) for empty states
- No complex illustrations needed

**Icons:**
- Use **Heroicons** (outline style) via CDN
- Size: h-5, w-5 for inline, h-6, w-6 for prominent

---

## Accessibility

- Minimum touch target: 44x44px
- Form labels always visible (no placeholder-only inputs)
- Focus indicators on all interactive elements
- Sufficient contrast for outdoor mobile use
- Screen reader labels for icon-only buttons
- Error messages announced to assistive tech

---

## Animation Strategy

**Minimal Animation:**
- Page transitions: Simple slide (200ms)
- Status changes: Subtle fade + scale (150ms)
- Button press: Scale down (100ms)
- Loading: Smooth spinner rotation
- **No scroll-triggered animations**
- **No decorative animations**

Speed and clarity take priority over visual flair.