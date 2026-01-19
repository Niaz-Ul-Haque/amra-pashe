# Amra Pashe — JIRA Tickets for MVP

**Project:** Amra Pashe  
**Version:** MVP v1.0  
**Created:** 2026-01-19  

---

## Epic 1: Project Setup & Infrastructure

### AP-001: Initialize Next.js Project with TypeScript
**Type:** Task  
**Priority:** Highest  
**Story Points:** 2  
**Description:**  
- Create new Next.js 14+ project with TypeScript
- Configure ESLint and Prettier
- Set up folder structure (components, pages, lib, hooks, types, utils)
- Initialize Git repository
- Create .gitignore with appropriate exclusions
- Set up environment variables structure (.env.local, .env.example)

**Acceptance Criteria:**
- [ ] Next.js app runs locally with `npm run dev`
- [ ] TypeScript strict mode enabled
- [ ] ESLint and Prettier configured and working
- [ ] Folder structure matches team conventions

---

### AP-002: Configure Tailwind CSS and UI Framework
**Type:** Task  
**Priority:** Highest  
**Story Points:** 2  
**Description:**  
- Install and configure Tailwind CSS
- Set up custom theme colors (brand colors)
- Configure responsive breakpoints for mobile-first design
- Install and configure shadcn/ui or similar component library
- Set up global styles and CSS variables

**Acceptance Criteria:**
- [ ] Tailwind CSS working with custom theme
- [ ] Component library installed and configured
- [ ] Global styles applied
- [ ] Mobile-first responsive utilities working

---

### AP-003: Set Up Database (PostgreSQL + Prisma)
**Type:** Task  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
- Set up PostgreSQL database (local + cloud provider)
- Install and configure Prisma ORM
- Create initial database schema based on data model
- Set up database migrations workflow
- Configure connection pooling for production

**Acceptance Criteria:**
- [ ] Database running locally
- [ ] Prisma configured with initial schema
- [ ] Migrations working
- [ ] Database seeding script created

---

### AP-004: Define Core Data Models (Prisma Schema)
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
Create Prisma schema for all MVP entities:
- User (phone, email, bloodGroup, location, role, verificationStatus)
- VerificationProfile (documents, verificationMethod, validUntil)
- Alert (type, bloodGroup, units, hospital, area, neededBy, status, publisherId)
- AlertUpdate (alertId, changes, timestamp)
- Response (alertId, userId, status, timestamp)
- ChatThread (alertId, participants)
- ChatMessage (threadId, senderId, content, timestamp)
- Report (reporterId, targetType, targetId, reason, status)
- AuditLog (userId, action, targetType, targetId, metadata, timestamp)

**Acceptance Criteria:**
- [ ] All entities defined in Prisma schema
- [ ] Relationships properly configured
- [ ] Indexes added for query performance
- [ ] Enums defined for status fields

---

### AP-005: Set Up Authentication Infrastructure (NextAuth.js)
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
- Install and configure NextAuth.js
- Set up phone number OTP authentication
- Configure session management
- Set up JWT tokens with appropriate expiry
- Create auth middleware for protected routes
- Implement 2FA infrastructure for verified publishers

**Acceptance Criteria:**
- [ ] Phone OTP login working
- [ ] Sessions persisted correctly
- [ ] Protected routes working
- [ ] 2FA flow ready for verified publishers

---

### AP-006: Set Up SMS Provider Integration
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Research and select SMS provider for Bangladesh (e.g., SSL Wireless, Infobip)
- Create SMS service abstraction layer
- Implement OTP sending functionality
- Implement alert notification sending
- Set up SMS templates
- Configure rate limiting and cost tracking

**Acceptance Criteria:**
- [ ] SMS provider integrated
- [ ] OTP messages sending successfully
- [ ] Alert notifications working
- [ ] Rate limiting in place

---

### AP-007: Configure Google Maps Integration
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Set up Google Maps API keys
- Create map component wrapper
- Implement location picker component
- Set up geocoding service for address lookup
- Configure thana/ward boundary data for Dhaka

**Acceptance Criteria:**
- [ ] Maps displaying correctly
- [ ] Location picker working
- [ ] Geocoding working
- [ ] Thana data available

---

### AP-008: Set Up Push Notification Infrastructure (Firebase)
**Type:** Task  
**Priority:** Medium  
**Story Points:** 3  
**Description:**  
- Set up Firebase project
- Configure Firebase Cloud Messaging (FCM)
- Create push notification service
- Set up service worker for web push
- Create notification permission request flow

**Acceptance Criteria:**
- [ ] Firebase configured
- [ ] Web push notifications working
- [ ] Service worker registered
- [ ] Permission flow implemented

---

### AP-009: Set Up File Upload Service (Images)
**Type:** Task  
**Priority:** Medium  
**Story Points:** 3  
**Description:**  
- Set up cloud storage (S3/Cloudinary/Firebase Storage)
- Create file upload API endpoints
- Implement image compression/optimization
- Set up secure URL generation
- Create upload component

**Acceptance Criteria:**
- [ ] File uploads working
- [ ] Images optimized before storage
- [ ] Secure URLs generated
- [ ] Upload component ready

---

### AP-010: Configure CI/CD Pipeline
**Type:** Task  
**Priority:** Medium  
**Story Points:** 3  
**Description:**  
- Set up GitHub Actions for CI
- Configure automated testing on PR
- Set up staging deployment (Vercel/Railway)
- Set up production deployment
- Configure environment secrets

**Acceptance Criteria:**
- [ ] CI runs on every PR
- [ ] Staging auto-deploys on main merge
- [ ] Production deployment configured
- [ ] All secrets configured

---

## Epic 2: Shared UI Components

### AP-011: Create Design System Foundation
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Define typography scale
- Define color palette and semantic colors
- Define spacing scale
- Create design tokens
- Document component usage guidelines

**Acceptance Criteria:**
- [ ] Typography system defined
- [ ] Colors documented
- [ ] Spacing consistent
- [ ] Design tokens created

---

### AP-012: Create Core Layout Components
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Create responsive AppShell/Layout component
- Create Header component with navigation
- Create Footer component
- Create mobile bottom navigation
- Create responsive sidebar (for admin)

**Acceptance Criteria:**
- [ ] Layout works on mobile and desktop
- [ ] Navigation accessible
- [ ] Footer displays correctly
- [ ] Mobile navigation working

---

### AP-013: Create Form Input Components
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- TextInput with validation states
- PhoneInput with country code (Bangladesh default)
- Select/Dropdown component
- DateTimePicker component
- Checkbox and Radio components
- Form error display component
- Form wrapper with validation (react-hook-form + zod)

**Acceptance Criteria:**
- [ ] All inputs styled consistently
- [ ] Validation states visible
- [ ] Phone input handles BD numbers
- [ ] DateTime picker mobile-friendly

---

### AP-014: Create Button and Action Components
**Type:** Task  
**Priority:** High  
**Story Points:** 2  
**Description:**  
- Button component (primary, secondary, danger, ghost variants)
- IconButton component
- Loading button state
- ButtonGroup component
- FAB (Floating Action Button) for mobile

**Acceptance Criteria:**
- [ ] All variants implemented
- [ ] Loading states working
- [ ] Touch targets appropriate for mobile
- [ ] Accessibility attributes present

---

### AP-015: Create Feedback Components
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Toast/Notification component
- Alert/Banner component
- Modal/Dialog component
- Confirmation dialog
- Loading spinner and skeleton loaders
- Empty state component
- Error boundary component

**Acceptance Criteria:**
- [ ] Toast notifications working
- [ ] Modals accessible (focus trap, escape key)
- [ ] Loading states consistent
- [ ] Error boundaries catching errors

---

### AP-016: Create Card and List Components
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Base Card component
- AlertCard component (for feed display)
- UserCard component
- List component with virtualization for long lists
- ListItem component

**Acceptance Criteria:**
- [ ] Cards responsive
- [ ] AlertCard shows key info at glance
- [ ] Lists performant with many items

---

### AP-017: Create Badge and Status Components
**Type:** Task  
**Priority:** Medium  
**Story Points:** 2  
**Description:**  
- Badge component (for blood groups, status)
- Status indicator (online/offline, verified)
- Verification badge component
- Urgency indicator component
- Tag component

**Acceptance Criteria:**
- [ ] Blood group badges colored appropriately
- [ ] Verification badge visible
- [ ] Status indicators clear

---

### AP-018: Create Location Components
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- LocationPicker component (map + manual entry)
- AddressDisplay component
- AreaSelector component (thana/ward dropdown)
- NearbyIndicator component
- Map embed component

**Acceptance Criteria:**
- [ ] Location picker supports GPS + manual
- [ ] Thana selector has Dhaka areas
- [ ] Map displays correctly on mobile

---

### AP-019: Create Avatar and Profile Components
**Type:** Task  
**Priority:** Medium  
**Story Points:** 2  
**Description:**  
- Avatar component with fallback
- UserProfileCard component
- VerifiedPublisherBadge component
- ProfileHeader component

**Acceptance Criteria:**
- [ ] Avatars display with fallback
- [ ] Profile cards show key info
- [ ] Verified status visible

---

## Epic 3: Authentication & User Management

### AP-020: Create Phone Signup Page
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a new user, I want to sign up using my phone number so I can access the platform.

**Implementation:**
- Phone number input with BD country code
- OTP request flow
- OTP verification screen
- Error handling for invalid numbers
- Rate limiting feedback

**Acceptance Criteria:**
- [ ] User can enter phone number
- [ ] OTP sent via SMS
- [ ] OTP verification works
- [ ] Error messages clear
- [ ] Rate limiting prevents abuse

---

### AP-021: Create User Profile Setup Flow
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a new user, I want to complete my profile so I can receive relevant alerts.

**Implementation:**
- Blood group selection (required)
- Location setup (GPS or manual area selection)
- Optional email addition
- Profile photo upload (optional)
- Terms acceptance checkbox

**Acceptance Criteria:**
- [ ] Blood group selectable
- [ ] Location can be set via GPS or dropdown
- [ ] Email can be added optionally
- [ ] Terms must be accepted to proceed

---

### AP-022: Create Login Flow
**Type:** Story  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
As a returning user, I want to log in using my phone number.

**Implementation:**
- Phone number input
- OTP verification
- Session creation
- Redirect to home/previous page
- "Remember this device" option

**Acceptance Criteria:**
- [ ] Login with OTP works
- [ ] Session persists appropriately
- [ ] Redirect works correctly

---

### AP-023: Create Profile View/Edit Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a user, I want to view and edit my profile information.

**Implementation:**
- Display current profile info
- Edit mode for each field
- Update blood group
- Update location
- Add/verify email
- Change profile photo

**Acceptance Criteria:**
- [ ] Profile displays correctly
- [ ] All fields editable
- [ ] Changes save successfully
- [ ] Validation on all fields

---

### AP-024: Implement Email Verification Flow
**Type:** Task  
**Priority:** Medium  
**Story Points:** 3  
**Description:**  
- Send verification email with link
- Create email verification page
- Update user verification status
- Display verified badge on profile

**Acceptance Criteria:**
- [ ] Verification email sends
- [ ] Link works correctly
- [ ] Status updates in database
- [ ] Badge displays on profile

---

### AP-025: Create Logout and Session Management
**Type:** Task  
**Priority:** High  
**Story Points:** 2  
**Description:**  
- Implement logout functionality
- Clear session on logout
- Handle session expiry gracefully
- Show login prompt when session expires

**Acceptance Criteria:**
- [ ] Logout clears session
- [ ] Expired sessions handled
- [ ] User redirected to login

---

### AP-026: Implement 2FA for Verified Publishers
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- Implement TOTP-based 2FA setup
- Create 2FA enrollment flow
- Create 2FA verification on login
- Create backup codes generation
- Create 2FA disable flow (with security checks)

**Acceptance Criteria:**
- [ ] 2FA can be enabled
- [ ] QR code displayed for authenticator apps
- [ ] Login requires 2FA when enabled
- [ ] Backup codes work

---

### AP-027: Implement Device Binding for Publishers
**Type:** Task  
**Priority:** Medium  
**Story Points:** 4  
**Description:**  
- Track devices per user
- Require approval for new devices
- Send notification on new device login
- Create device management page
- Admin approval for new devices

**Acceptance Criteria:**
- [ ] Devices tracked per user
- [ ] New device triggers approval
- [ ] Users can manage devices
- [ ] Admins can approve devices

---

## Epic 4: Verified Publisher Onboarding

### AP-028: Create Publisher Application Form
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a potential publisher, I want to apply for verified publisher status.

**Implementation:**
- Application form with:
  - Full name
  - Role/affiliation (doctor, hospital staff, NGO, etc.)
  - Organization name
  - ID document upload
  - Photo upload
  - Reference/partner organization (if any)
  - Reason for applying
- Submit for review

**Acceptance Criteria:**
- [ ] Form captures all required info
- [ ] Documents upload successfully
- [ ] Application submits to review queue
- [ ] Confirmation shown to applicant

---

### AP-029: Create Publisher Application Status Page
**Type:** Story  
**Priority:** High  
**Story Points:** 3  
**Description:**  
As an applicant, I want to check the status of my publisher application.

**Implementation:**
- Display application status (pending, approved, rejected)
- Show submitted information
- Display rejection reason if rejected
- Option to reapply after rejection

**Acceptance Criteria:**
- [ ] Status displayed correctly
- [ ] Rejection reason shown
- [ ] Reapply option available

---

### AP-030: Create Verified Publisher Dashboard
**Type:** Story  
**Priority:** High  
**Story Points:** 5  
**Description:**  
As a verified publisher, I want a dashboard to manage my alerts.

**Implementation:**
- Overview of active alerts
- Quick create alert button
- Alert statistics (responses, fulfillment rate)
- Recent responses
- Verification status and expiry date

**Acceptance Criteria:**
- [ ] Dashboard shows key metrics
- [ ] Quick actions accessible
- [ ] Verification status visible

---

## Epic 5: Alert Management

### AP-031: Create Blood Donation Alert Form
**Type:** Story  
**Priority:** Highest  
**Story Points:** 8  
**Description:**  
As a verified publisher, I want to create a blood donation alert.

**Implementation:**
- Blood group selector (A+, A-, B+, B-, AB+, AB-, O+, O-)
- Units needed input
- Hospital/clinic name (from catalog or manual entry)
- Area selector (thana/ward in Dhaka)
- Needed-by datetime picker
- Contact method selection (call/chat)
- Optional proof photo upload
- Preview before publish
- Publish button

**Acceptance Criteria:**
- [ ] All mandatory fields enforced
- [ ] Hospital names searchable
- [ ] Area selection works
- [ ] DateTime picker mobile-friendly
- [ ] Preview shows accurate info
- [ ] Alert publishes successfully

---

### AP-032: Create Medical Supplies Alert Form
**Type:** Story  
**Priority:** Highest  
**Story Points:** 6  
**Description:**  
As a verified publisher, I want to create a medical supplies alert.

**Implementation:**
- Supply type dropdown (from catalog)
- Quantity input
- Hospital/clinic name
- Area selector
- Needed-by datetime picker
- Optional proof photo upload
- Preview and publish

**Acceptance Criteria:**
- [ ] Supply catalog dropdown works
- [ ] All mandatory fields enforced
- [ ] Preview accurate
- [ ] Alert publishes successfully

---

### AP-033: Create Medical Supplies Catalog
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Define list of medical supply types for dropdown
- Create database seed for supply types
- Create admin interface to manage catalog
- Support both English and Bangla names

**Acceptance Criteria:**
- [ ] Catalog seeded with common supplies
- [ ] Dropdown populated correctly
- [ ] Bilingual names supported

---

### AP-034: Create Hospital/Clinic Directory
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Create hospital/clinic database table
- Seed with major Dhaka hospitals
- Create search/autocomplete API
- Allow manual entry with moderation

**Acceptance Criteria:**
- [ ] Major hospitals seeded
- [ ] Search returns relevant results
- [ ] Manual entries queue for review

---

### AP-035: Create Dhaka Area (Thana/Ward) Data
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Compile list of Dhaka thanas and wards
- Create database structure for areas
- Create hierarchical area selector
- Include coordinate bounds for each area

**Acceptance Criteria:**
- [ ] All Dhaka thanas included
- [ ] Area selector works hierarchically
- [ ] Bounds data available for matching

---

### AP-036: Implement Alert Publishing Logic
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
- Create alert publishing API endpoint
- Validate all required fields
- Set default expiry (6 hours)
- Create audit log entry
- Trigger notification fanout

**Acceptance Criteria:**
- [ ] API validates correctly
- [ ] Alert saved to database
- [ ] Expiry set correctly
- [ ] Audit log created
- [ ] Notifications triggered

---

### AP-037: Implement Alert Expiry System
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Create scheduled job for expiry check
- Auto-expire alerts past neededBy time
- Allow manual expiry extension (up to 7 days)
- Notify publisher before expiry

**Acceptance Criteria:**
- [ ] Expired alerts marked automatically
- [ ] Extension works correctly
- [ ] Publisher notified before expiry

---

### AP-038: Create Alert Edit Functionality
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a publisher, I want to edit my published alerts.

**Implementation:**
- Edit form pre-populated with current data
- Track changes in AlertUpdate table
- Show edit history on alert detail
- Notify responders of significant changes

**Acceptance Criteria:**
- [ ] Edit form works correctly
- [ ] Changes tracked in history
- [ ] History visible on alert
- [ ] Responders notified of changes

---

### AP-039: Create Alert Fulfillment Flow
**Type:** Story  
**Priority:** High  
**Story Points:** 5  
**Description:**  
As a publisher, I want to mark an alert as fulfilled.

**Implementation:**
- "Mark Fulfilled" button on alert
- Select which responder fulfilled
- Request confirmation from responder
- Update alert status
- Create audit log entry
- Send thank you notification

**Acceptance Criteria:**
- [ ] Publisher can mark fulfilled
- [ ] Responder selected
- [ ] Status updates correctly
- [ ] Notifications sent

---

### AP-040: Create Alert Detail Page (Public View)
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a user, I want to view details of an alert.

**Implementation:**
- Display alert type and details
- Show blood group/supply type prominently
- Display hospital name and coarse area
- Show needed-by time with countdown
- Display publisher profile (clickable)
- Show "I can help" CTA
- Show response count

**Acceptance Criteria:**
- [ ] All info displays correctly
- [ ] Publisher profile clickable
- [ ] CTA prominent
- [ ] Mobile-optimized layout

---

### AP-041: Create Publisher Profile Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a user, I want to view a publisher's profile and history.

**Implementation:**
- Display publisher name and affiliation
- Show verification badge and date
- List previous alerts with outcomes
- Show fulfillment rate
- Display response statistics

**Acceptance Criteria:**
- [ ] Profile displays correctly
- [ ] Previous alerts visible
- [ ] Statistics accurate
- [ ] Verification visible

---

## Epic 6: Alert Feed & Discovery

### AP-042: Create Alert Feed API
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
- Create API endpoint for fetching alerts
- Implement nearby filtering (by thana or radius)
- Implement blood group filtering
- Implement alert type filtering
- Implement pagination
- Sort by urgency/recency

**Acceptance Criteria:**
- [ ] API returns filtered alerts
- [ ] Nearby filtering works
- [ ] Pagination works
- [ ] Sorting correct

---

### AP-043: Create Alert Feed Page
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a user, I want to browse nearby alerts.

**Implementation:**
- List of AlertCards
- Filter controls (blood group, type)
- Location indicator
- Pull-to-refresh on mobile
- Infinite scroll pagination
- Empty state when no alerts

**Acceptance Criteria:**
- [ ] Feed displays alerts
- [ ] Filters work correctly
- [ ] Pagination works
- [ ] Mobile experience smooth

---

### AP-044: Implement Nearby Matching Algorithm
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
- Define "nearby" as same thana (MVP)
- Create function to match users to alerts by location
- Fallback to adjacent thanas if few matches
- Support future radius-based matching

**Acceptance Criteria:**
- [ ] Same-thana matching works
- [ ] Adjacent thana fallback works
- [ ] Performance acceptable

---

### AP-045: Create Real-time Alert Updates
**Type:** Task  
**Priority:** Medium  
**Story Points:** 4  
**Description:**  
- Implement WebSocket or SSE for real-time updates
- Push new alerts to feed without refresh
- Update alert status in real-time
- Show "new alerts available" indicator

**Acceptance Criteria:**
- [ ] New alerts appear without refresh
- [ ] Status updates reflect in real-time
- [ ] Works on slow connections

---

## Epic 7: Response Flow

### AP-046: Create "I Can Help" Flow
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As a user, I want to respond to an alert and offer help.

**Implementation:**
- "I can help" button on alert
- Confirmation dialog explaining next steps
- Create Response record
- Reveal contact details after confirmation
- Show case chat access
- Notify publisher of new response

**Acceptance Criteria:**
- [ ] Button triggers flow
- [ ] Confirmation required
- [ ] Contact revealed after confirm
- [ ] Chat access granted
- [ ] Publisher notified

---

### AP-047: Create Contact Reveal Component
**Type:** Task  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
- Display contact info only after "I can help"
- Show phone number with click-to-call
- Show exact address if provided
- Include WhatsApp deep link option

**Acceptance Criteria:**
- [ ] Contact hidden until confirmation
- [ ] Click-to-call works
- [ ] WhatsApp link works
- [ ] Address displays correctly

---

### AP-048: Create Case Chat System
**Type:** Story  
**Priority:** High  
**Story Points:** 8  
**Description:**  
As a responder or publisher, I want to communicate in a case chat.

**Implementation:**
- Create chat thread when first responder joins
- Allow multiple responders in same chat
- Real-time message delivery
- Show participant list
- Allow publisher to remove participants
- Basic text messaging only (MVP)
- Message history persistent

**Acceptance Criteria:**
- [ ] Chat thread created correctly
- [ ] Messages send/receive in real-time
- [ ] Multiple participants work
- [ ] Publisher can remove users
- [ ] History persisted

---

### AP-049: Create Chat Message Component
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Message bubble component (sent/received)
- Timestamp display
- Sender identification
- Read receipts (optional for MVP)
- Message loading states

**Acceptance Criteria:**
- [ ] Messages display correctly
- [ ] Timestamps accurate
- [ ] Sender identified
- [ ] Loading states smooth

---

### AP-050: Create Response Tracking Dashboard
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a publisher, I want to see all responses to my alerts.

**Implementation:**
- List of responders per alert
- Response timestamps
- Responder profiles (if verified)
- Mark specific responder as fulfiller
- Contact responders directly

**Acceptance Criteria:**
- [ ] Responses listed correctly
- [ ] Timestamps visible
- [ ] Can mark fulfiller
- [ ] Can contact responders

---

### AP-051: Implement Outcome Tracking
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Track fulfilled/unfulfilled status
- Track responder count per alert
- Track time to first response
- Track which responder fulfilled
- Store metrics for analytics

**Acceptance Criteria:**
- [ ] All metrics tracked
- [ ] Data accurate
- [ ] Available for analytics queries

---

## Epic 8: Notifications

### AP-052: Create Notification Preferences Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a user, I want to control my notification preferences.

**Implementation:**
- Toggle SMS notifications
- Toggle push notifications
- Set blood group filter for notifications
- Set quiet hours preference
- Save preferences

**Acceptance Criteria:**
- [ ] Toggles work correctly
- [ ] Filters saved
- [ ] Quiet hours respected
- [ ] Changes persist

---

### AP-053: Implement SMS Alert Notifications
**Type:** Task  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
- Create notification fanout system
- Match alerts to nearby users
- Send SMS to matched users
- Implement per-user daily cap
- Track SMS costs
- Handle delivery failures

**Acceptance Criteria:**
- [ ] SMS sent to nearby users
- [ ] Caps respected
- [ ] Costs tracked
- [ ] Failures logged

---

### AP-054: Implement Push Notifications
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Send push for new nearby alerts
- Send push for chat messages
- Send push for response updates
- Handle notification clicks (deep linking)

**Acceptance Criteria:**
- [ ] Push notifications work
- [ ] Deep linking works
- [ ] Content accurate

---

### AP-055: Create WhatsApp Share Functionality
**Type:** Task  
**Priority:** Medium  
**Story Points:** 2  
**Description:**  
- Create shareable alert link
- Generate WhatsApp share deep link
- Create share button on alert detail
- Track shares for analytics

**Acceptance Criteria:**
- [ ] Share link generates
- [ ] WhatsApp opens with message
- [ ] Shares tracked

---

## Epic 9: Admin Panel

### AP-056: Create Admin Layout and Navigation
**Type:** Task  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
- Create admin-specific layout
- Sidebar navigation
- Dashboard overview page
- Protected routes (admin only)
- Responsive for desktop/tablet

**Acceptance Criteria:**
- [ ] Layout functional
- [ ] Navigation works
- [ ] Routes protected
- [ ] Desktop/tablet friendly

---

### AP-057: Create Publisher Verification Queue
**Type:** Story  
**Priority:** Highest  
**Story Points:** 5  
**Description:**  
As an admin, I want to review publisher applications.

**Implementation:**
- List of pending applications
- Application detail view
- View uploaded documents
- Approve/Reject actions
- Add rejection reason
- Send notification on decision

**Acceptance Criteria:**
- [ ] Queue displays pending apps
- [ ] Documents viewable
- [ ] Approve/reject works
- [ ] Notification sent

---

### AP-058: Create Publisher Management Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As an admin, I want to manage verified publishers.

**Implementation:**
- List all verified publishers
- View publisher details
- Revoke publisher status
- View publisher's alerts
- Edit verification expiry
- Add notes to profile

**Acceptance Criteria:**
- [ ] Publishers listed
- [ ] Revocation works
- [ ] Expiry editable
- [ ] Notes saved

---

### AP-059: Create User Management Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As an admin, I want to view and manage users.

**Implementation:**
- Search/filter users
- View user details
- View user's responses
- Suspend/unsuspend users
- View verification status

**Acceptance Criteria:**
- [ ] Search works
- [ ] Details viewable
- [ ] Suspension works

---

### AP-060: Create Alert Moderation Page
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As an admin, I want to moderate alerts.

**Implementation:**
- List all alerts with filters
- View alert details
- Remove/hide alerts
- View edit history
- Add admin notes

**Acceptance Criteria:**
- [ ] Alerts listed
- [ ] Removal works
- [ ] History viewable
- [ ] Notes saved

---

### AP-061: Create Report Management Page
**Type:** Story  
**Priority:** High  
**Story Points:** 5  
**Description:**  
As an admin, I want to handle user reports.

**Implementation:**
- List pending reports
- View report details
- View reported content
- Take action (warn/restrict/ban)
- Close report with resolution
- Send notification to reporter

**Acceptance Criteria:**
- [ ] Reports listed
- [ ] Actions work correctly
- [ ] Notifications sent

---

### AP-062: Implement Enforcement Actions
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Implement warning system
- Implement account restriction
- Implement account ban
- Create enforcement history
- Send notifications for actions

**Acceptance Criteria:**
- [ ] Warn action works
- [ ] Restrict limits functionality
- [ ] Ban prevents access
- [ ] History tracked

---

### AP-063: Create Audit Log Viewer
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As an admin, I want to view system audit logs.

**Implementation:**
- Searchable audit log list
- Filter by action type, user, date
- View log details
- Export logs (CSV)

**Acceptance Criteria:**
- [ ] Logs searchable
- [ ] Filters work
- [ ] Details viewable
- [ ] Export works

---

### AP-064: Create Admin Dashboard with Metrics
**Type:** Story  
**Priority:** Medium  
**Story Points:** 5  
**Description:**  
As an admin, I want to see platform metrics.

**Implementation:**
- Total alerts created (by day/week/month)
- Fulfillment rate
- Median time to first response
- Active publishers count
- Active users count
- Pending items counts

**Acceptance Criteria:**
- [ ] Metrics accurate
- [ ] Charts display correctly
- [ ] Time filters work

---

## Epic 10: Safety & Abuse Prevention

### AP-065: Create Report Flow
**Type:** Story  
**Priority:** High  
**Story Points:** 4  
**Description:**  
As a user, I want to report suspicious activity.

**Implementation:**
- Report button on alerts and profiles
- Report reason selection
- Optional additional details
- Submit to moderation queue
- Confirmation to user

**Acceptance Criteria:**
- [ ] Report button accessible
- [ ] Reasons selectable
- [ ] Report submitted
- [ ] Confirmation shown

---

### AP-066: Implement Rate Limiting
**Type:** Task  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
- Rate limit OTP requests
- Rate limit alert creation per publisher
- Rate limit API requests
- Show appropriate error messages
- Log rate limit violations

**Acceptance Criteria:**
- [ ] OTP limited (e.g., 3/10min)
- [ ] Alerts limited (e.g., 5/hour)
- [ ] API limited per IP/user
- [ ] Errors clear

---

### AP-067: Implement Content Validation
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Validate dropdown selections against catalog
- Validate location data
- Validate datetime ranges
- Sanitize any text inputs
- Reject invalid submissions

**Acceptance Criteria:**
- [ ] All validations working
- [ ] Invalid data rejected
- [ ] Error messages helpful

---

### AP-068: Add Terms of Service and Privacy Policy Pages
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Create Terms of Service page
- Create Privacy Policy page
- Include disclaimer about identity verification
- Include "not emergency services" notice
- Require acceptance during signup

**Acceptance Criteria:**
- [ ] Pages accessible
- [ ] Content complete
- [ ] Acceptance tracked

---

## Epic 11: Performance & Accessibility

### AP-069: Optimize for Slow Connections
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- Implement code splitting
- Optimize images (WebP, lazy loading)
- Minimize JavaScript bundle
- Add loading skeletons
- Implement offline-capable features
- Test on 2G/3G connections

**Acceptance Criteria:**
- [ ] Page loads under 3s on 3G
- [ ] Images optimized
- [ ] Bundle under 200KB initial
- [ ] Skeleton loaders present

---

### AP-070: Implement Progressive Web App (PWA)
**Type:** Task  
**Priority:** Medium  
**Story Points:** 4  
**Description:**  
- Add PWA manifest
- Configure service worker
- Enable add-to-home-screen
- Cache essential assets
- Handle offline gracefully

**Acceptance Criteria:**
- [ ] PWA installable
- [ ] Offline shows cached content
- [ ] Push notifications work

---

### AP-071: Accessibility Audit and Fixes
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Run accessibility audit (Lighthouse, axe)
- Fix color contrast issues
- Add ARIA labels
- Ensure keyboard navigation
- Test with screen reader

**Acceptance Criteria:**
- [ ] Lighthouse accessibility > 90
- [ ] Keyboard navigation works
- [ ] Screen reader compatible

---

### AP-072: Add Bangla Language Support
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- Set up i18n framework (next-intl or similar)
- Create Bangla translation file
- Translate all UI strings
- Support Bangla input
- Language switcher component

**Acceptance Criteria:**
- [ ] Bangla translations complete
- [ ] Switcher works
- [ ] Bangla renders correctly

---

## Epic 12: Testing

### AP-073: Set Up Testing Infrastructure
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Configure Jest for unit tests
- Configure React Testing Library
- Configure Playwright for E2E tests
- Set up test database
- Add test scripts to package.json

**Acceptance Criteria:**
- [ ] Unit tests run
- [ ] E2E tests run
- [ ] CI runs tests

---

### AP-074: Write Unit Tests for Core Logic
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- Test nearby matching algorithm
- Test alert validation logic
- Test notification targeting
- Test auth flows
- Aim for 70%+ coverage on core logic

**Acceptance Criteria:**
- [ ] Core logic tested
- [ ] Coverage target met
- [ ] Tests pass in CI

---

### AP-075: Write E2E Tests for Critical Paths
**Type:** Task  
**Priority:** High  
**Story Points:** 5  
**Description:**  
- Test signup flow
- Test alert creation flow
- Test response flow
- Test admin verification flow
- Test on mobile viewport

**Acceptance Criteria:**
- [ ] Critical paths covered
- [ ] Tests pass reliably
- [ ] Mobile tests included

---

## Epic 13: Documentation & Deployment

### AP-076: Create API Documentation
**Type:** Task  
**Priority:** Medium  
**Story Points:** 3  
**Description:**  
- Document all API endpoints
- Include request/response examples
- Document authentication requirements
- Set up Swagger/OpenAPI

**Acceptance Criteria:**
- [ ] All endpoints documented
- [ ] Examples included
- [ ] Swagger UI accessible

---

### AP-077: Create Developer Setup Guide
**Type:** Task  
**Priority:** Medium  
**Story Points:** 2  
**Description:**  
- Document local setup steps
- Document environment variables
- Document database setup
- Document common issues

**Acceptance Criteria:**
- [ ] README complete
- [ ] New dev can set up in 30 min

---

### AP-078: Create Operations Runbook
**Type:** Task  
**Priority:** High  
**Story Points:** 4  
**Description:**  
- Document verification checklist
- Document moderation procedures
- Document incident response
- Document escalation paths
- Document SLAs

**Acceptance Criteria:**
- [ ] All procedures documented
- [ ] Team trained on runbook

---

### AP-079: Deploy to Staging Environment
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Deploy application to staging
- Configure staging database
- Configure staging SMS provider (sandbox)
- Configure staging FCM
- Verify all features work

**Acceptance Criteria:**
- [ ] Staging accessible
- [ ] All features functional
- [ ] Data isolated from production

---

### AP-080: Deploy to Production
**Type:** Task  
**Priority:** Highest  
**Story Points:** 3  
**Description:**  
- Deploy application to production
- Configure production database with backups
- Configure production SMS
- Configure production FCM
- Set up monitoring and alerts
- Verify critical paths

**Acceptance Criteria:**
- [ ] Production live
- [ ] Backups configured
- [ ] Monitoring active
- [ ] Critical paths verified

---

### AP-081: Set Up Monitoring and Alerting
**Type:** Task  
**Priority:** High  
**Story Points:** 3  
**Description:**  
- Set up error tracking (Sentry)
- Set up uptime monitoring
- Set up performance monitoring
- Configure alerts for critical errors
- Set up SMS cost monitoring

**Acceptance Criteria:**
- [ ] Errors tracked
- [ ] Uptime monitored
- [ ] Alerts configured

---

## Summary

| Epic | Tickets | Story Points |
|------|---------|--------------|
| 1. Project Setup & Infrastructure | 10 | 30 |
| 2. Shared UI Components | 9 | 27 |
| 3. Authentication & User Management | 8 | 32 |
| 4. Verified Publisher Onboarding | 3 | 13 |
| 5. Alert Management | 11 | 52 |
| 6. Alert Feed & Discovery | 4 | 19 |
| 7. Response Flow | 6 | 27 |
| 8. Notifications | 4 | 15 |
| 9. Admin Panel | 9 | 38 |
| 10. Safety & Abuse Prevention | 4 | 13 |
| 11. Performance & Accessibility | 4 | 18 |
| 12. Testing | 3 | 13 |
| 13. Documentation & Deployment | 6 | 18 |
| **Total** | **81** | **315** |

---

## Recommended Sprint Breakdown

### Sprint 1 (Setup)
- AP-001 through AP-010 (Infrastructure)

### Sprint 2 (UI Components)
- AP-011 through AP-019 (All shared components)

### Sprint 3 (Auth & Users)
- AP-020 through AP-027 (Auth flows)

### Sprint 4 (Alerts Core)
- AP-031 through AP-039 (Alert creation and management)

### Sprint 5 (Feed & Response)
- AP-042 through AP-051 (Discovery and response flow)

### Sprint 6 (Publishers & Notifications)
- AP-028 through AP-030, AP-052 through AP-055 (Publisher onboarding and notifications)

### Sprint 7 (Admin Panel)
- AP-056 through AP-064 (Complete admin panel)

### Sprint 8 (Polish & Safety)
- AP-065 through AP-072 (Safety, performance, accessibility)

### Sprint 9 (Testing & Launch)
- AP-073 through AP-081 (Testing, docs, deployment)

---

*Document generated based on PRD v0.1 dated 2026-01-04*
