## Exploratory Testing Report
<br>


## 1. Introduction

This document summarizes the results of exploratory testing performed on the VSHOP ERP system.  
Exploratory testing was conducted to gain an understanding of the system’s current behavior, workflows, limitations, and risks in the absence of formal requirements documentation.

The findings documented in this report are based on exploratory testing sessions derived from inferred user workflows and real system usage.
<br>
---
<br>

## 2. Scope of Exploratory Testing

Exploratory testing was performed based on user roles and system modules.
<br>

### 2.1. Roles Covered
- Accountant
- Buyer
- Company Owner
- HR Manager
- Product Manager
- Seller
- Technician
- Warehouse Manager
<br>

### 2.2 Modules Covered
- V-Shop
- Shop
- Portal
- Admin Panel
<br>
---
<br>

## 3. Testing Approach

Exploratory testing was conducted using session-based testing techniques.

- Sessions were derived from inferred user stories based on real workflows.
- Testing focused on understanding system behavior rather than validation against predefined requirements.
- Observations were recorded during testing sessions and documented separately in exploratory notes and session sheets.
- No formal defect reporting was performed during exploratory testing.
<br>
---
<br>

## 4. Key Observations

### 4.1. System Age, Architecture & Technical Debt

- The system was created approximately 20 years ago and has undergone only minimal functional updates.
- The architecture is outdated and not aligned with modern ERP standards.
- The system remains operational and supports daily business processes, but relies heavily on manual workflows and external tools.

**Impact**: High technical debt; Limited scalability; Difficult maintenance; High risk of regression during changes; Difficult onboarding of new employees.
<br>


### 4.2. Lack of Automation & Process Optimization

- Many business processes rely on manual work:
    - Supplier orders
    - Order status updates
    - Marketplace reconciliation
    - Credit application
    - RMA status updates
    - Low-stock monitoring
- External tools (Microsoft Teams, email, marketplaces, courier services) are used as core workflow components.

**Impact**: Increased operational cost; High human-error risk; Low process transparency; Slow business operations; Difficult auditing and compliance.
<br>

### 4.3. Usability & User Experience

- The interface is not user-friendly.
- Navigation is complex and unintuitive.
- Many actions require deep system knowledge.
- Critical workflows require memorization of URLs and system logic.
- Reports open in new browser tabs and require browser-native actions for export.

**Impact**: High onboarding time for new employees; Increased training costs; High risk of operational mistakes; Low user confidence; Low productivity.
<br>

### 4.4. Security & Access Control Weaknesses

- Weak authentication mechanisms:
- No enforced password complexity
- No password expiration policies
- No MFA
- No automated alerts for failed login attempts.
- Security monitoring requires manual log review.
- Logs are difficult to navigate (no calendar filters, pagination only).
- No centralized security dashboard.

**Impact**: High risk of unauthorized access; High risk of data leakage; No real-time threat detection; Weak compliance posture (GDPR, ISO, SOC2, etc.)
<br>

### 4.5. Data Traceability & Auditability Gaps

- Many workflows lack system-level traceability:
    - Supplier orders
    - External service tracking
    - Marketplace reconciliation
    - Communication history
    - Internal chat logs
- Communication history is fragmented across multiple platforms.

**Impact**: Difficult incident investigation; No end-to-end business traceability; Weak audit readiness; Difficult financial and legal verification.
<br>

### 4.6. Reporting & Business Intelligence Limitations

- Reporting is fragmented and inconsistent.
- No centralized BI dashboard.
- Many reports are available only at entity level (per product, per order).
- No aggregated analytics for:
    - Product performance
    - Customer behavior
    - Supplier efficiency
    - RMA trends
- Reports rely on browser-native export.

**Impact**: No real-time business insights; Limited forecasting capability; Manual data aggregation required.
<br>

### 4.7. Integration Architecture Limitations

- Marketplace integrations exist but are rule-based and fragile.
- Supplier integrations require manual Excel imports.
- Some suppliers block synchronization.
- Courier and service tracking is external.
- Communication relies on external collaboration platforms.

**Impact**: High integration maintenance cost; Fragile data pipelines; Limited automation.
<br>

### 4.8. Performance & Stability Risks

- Bulk operations (price import, supplier catalog import) cause UI unresponsiveness.
- Users must open parallel browser sessions to continue working.
- No background processing or job queue mechanism is visible.

**Impact**: High risk of operational downtime; Poor user experience; High risk of data corruption during imports; Scalability limitations.
<br>

### 4.9. Compliance & Legal Risk

- The system does not provide built-in HR documentation management.
- Employment agreements, insurance records, and HR documentation are stored externally.
- Working hours, vacations, and sick leaves are not tracked within the system.
(In Greece, working hours are recorded and tracked via a separate government-mandated system, which VisionStudio uses.)
- System chat messages are not retained and no chat history is stored.
- Customer communication is not archived within the system and is stored across external channels (email, marketplaces, Google Business, etc.).

**Impact**: 
Legal and regulatory compliance is ensured through external systems and procedures.
HR audit requirements are covered by external HR documentation storage.
Labor law compliance is maintained via the official Greek working-hours tracking system.
However, the lack of internal communication archiving and customer communication history results in:
- limited internal traceability
- reduced auditability of business communications
- fragmented customer interaction records
