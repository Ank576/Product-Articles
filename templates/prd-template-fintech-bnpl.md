# 💳 Fintech PRD Template - BNPL

## Overview

This PRD template is designed for building financial technology features within BNPL (Buy Now Pay Later) platforms. Use this template when developing features related to credit management, lending, risk assessment, compliance, and financial operations.

---

## 1. Executive Summary

### Feature Purpose
- **Description**: [Core financial feature objective]
- **Business Model**: [Revenue model: Interest / Interchange / Subscription / Hybrid]
- **Regulatory Scope**: [PSD2 / GDPR / FCRA / SCRA / Local regulations]
- **Target Markets**: [Countries/regions for compliance]
- **Timeline**: [Launch target date]

### Key Business Metrics
- [ ] Target APR/Interest Rate: [X%]
- [ ] Target Customer LTV: [X months]
- [ ] Default Rate Target: <[X%]
- [ ] Profitability Timeline: [X months]

---

## 2. Financial Product Design

### 2.1 Product Architecture

| Component | Details |
|-----------|----------|
| **Product Type** | Installment / Credit Line / Subscription |
| **Loan Amount Range** | $[min] - $[max] per transaction |
| **Tenor Options** | [Weekly / Biweekly / Monthly] |
| **Installment Count** | [2, 3, 4, 6, 12, 24] installments |
| **Interest Model** | [APR % / Flat / 0% promotional] |
| **Late Payment Fee** | [Fixed $X / % of amount] |
| **Credit Limit** | [Dynamic / Fixed by tier] |

### 2.2 Credit Products

#### Product Variants
1. **Entry-Level BNPL** (Ages 18-25, Low credit)
   - Max amount: $[X]
   - Default tenor: 3 installments
   - APR: [Y%]

2. **Mid-Tier Credit Line** (Ages 26-40, Established credit)
   - Max amount: $[X]
   - Default tenor: 6 installments
   - APR: [Y%]

3. **Premium Credit Line** (Ages 40+, High credit)
   - Max amount: $[X]
   - Default tenor: 12 installments
   - APR: [Y%]

---

## 3. Credit Risk & Underwriting

### 3.1 Credit Scoring Model

**Risk Score Range**: 0-1000 (Higher = Lower Risk)

| Score | Risk Level | Decision | Limit |
|-------|-----------|----------|-------|
| 750-1000 | Very Low Risk | Auto-approve | $[X] |
| 650-749 | Low Risk | Auto-approve | $[X] |
| 550-649 | Medium Risk | Manual review | $[X] |
| 400-549 | High Risk | Decline/Offer lower | $[X] |
| <400 | Very High Risk | Decline | $0 |

### 3.2 Underwriting Factors

**Primary Factors (40% weight)**
- Credit history score
- Payment history (last 12 months)
- Debt-to-income ratio
- Account age average

**Secondary Factors (30% weight)**
- Income verification
- Employment stability
- Bank account activity
- Device/behavioral signals

**Tertiary Factors (30% weight)**
- Merchant category
- Transaction frequency
- Device fingerprint
- Geographic location

### 3.3 Real-Time Verification

**Data Sources**:
- Credit bureaus: [Equifax / Experian / TransUnion]
- Bank account verification: Plaid / Yodlee
- Income verification: Verificd / Pinwheel
- Fraud detection: Kount / Sift Science

---

## 4. Regulatory & Compliance

### 4.1 Regulatory Requirements

| Regulation | Requirement | Implementation |
|------------|-------------|----------------|
| **FCRA** | Credit inquiry disclosure | Pre-check popup |
| **TILA** | APR/Cost transparency | Checkout disclosure |
| **ECOA** | Non-discrimination | Audit scoring model quarterly |
| **FDCPA** | Fair debt collection | Compliant dunning sequence |
| **KYC/AML** | Customer verification | Document upload + facial recognition |
| **GDPR/CCPA** | Data privacy | Encryption + retention policy |

### 4.2 Compliance Checklist
- [ ] Legal review completed
- [ ] Regulatory jurisdiction confirmed
- [ ] Privacy impact assessment (PIA) signed off
- [ ] Terms & conditions drafted
- [ ] Disclosure documents ready
- [ ] Audit trail logging enabled
- [ ] Customer support playbook ready
- [ ] Dispute resolution process documented

---

## 5. Fraud & Risk Management

### 5.1 Fraud Prevention Layers

**Layer 1: Preventive Controls**
- Device fingerprinting
- Email/phone verification
- Address matching (AVS)
- Velocity checking (X transactions in Y hours)

**Layer 2: Real-Time Decisioning**
- Behavioral analytics
- Network analysis
- Machine learning scoring
- 3D Secure authentication

**Layer 3: Post-Transaction Monitoring**
- Chargebacks monitoring
- Account takeover alerts
- Unusual activity flags
- Pattern analysis

### 5.2 Risk Metrics Dashboard

**Key Metrics to Track**:
- Fraud rate: [Target <X%]
- Chargeback rate: [Target <X%]
- Default rate: [Target <X%]
- Approval rate: [Target >X%]
- False positive rate: [Target <X%]

---

## 6. Customer Lifecycle

### 6.1 Onboarding Flow

```
1. Registration → 2. KYC Verification → 3. Credit Check → 4. Offer Generated → 5. Acceptance
```

**Timeline**: Target completion in <5 minutes

### 6.2 Account States

| State | Condition | Action |
|-------|-----------|--------|
| **Active** | In good standing | Normal activity |
| **Delinquent** | 15+ days late | Send reminder |
| **Default** | 30+ days late | Collections outreach |
| **Charged-off** | 120+ days late | Write-off account |
| **Paid** | All installments complete | Close account |

### 6.3 Collections Strategy

**Day 1-14**: Soft reminder
- Email notification
- SMS notification
- In-app notification

**Day 15-30**: Escalated reminder
- Phone call
- Push notification
- Late fee applied

**Day 31-60**: Collections outreach
- Legal letter
- Collections agency engagement
- Credit bureau reporting

---

## 7. Interest & Fee Structure

### 7.1 Interest Calculation

**Formula**:
```
Monthly Interest = Principal × (APR / 12) × (Days in Period / 30)
Total Interest = Sum of all monthly interests
```

**Example**:
- Principal: $1,000
- APR: 15%
- Tenor: 3 months
- Monthly Interest: ~$12.50
- Total Interest: ~$37.50
- Customer pays: $1,037.50 total

### 7.2 Fee Schedule

| Fee Type | Amount | Trigger |
|----------|--------|----------|
| **Late Fee** | $[X] or [X%] | 1+ day late |
| **NSF Fee** | $[X] | Failed payment |
| **Setup Fee** | $[X] or [X%] | Loan origination |
| **Early Payoff** | None | Incentivize early payment |
| **Returned Check** | $[X] | Failed ACH |

---

## 8. Payment & Settlement

### 8.1 Payment Methods
- [ ] ACH (Automated Clearing House)
- [ ] Credit/Debit Card
- [ ] Bank transfer
- [ ] Mobile wallet (Apple Pay, Google Pay)
- [ ] Automatic recurring payments

### 8.2 Settlement Timeline

| Party | Settlement Timing |
|-------|-------------------|
| **Merchant** | T+0 or T+1 depending on plan |
| **Payment Processor** | T+2 to acquiring bank |
| **Customer** | Due date as per agreement |

### 8.3 Reconciliation
- Daily payment file validation
- Weekly settlement reports
- Monthly vendor reconciliation
- Quarterly audit reviews

---

## 9. Financial Reporting

### 9.1 Key Metrics

**Profitability Metrics**
- Revenue: [Interest + Fees - Costs]
- Cost of funds: [Borrowing rate if financed]
- Loss rate: [Charge-offs / Total portfolio]
- ROI: [Net profit / Total investment]

**Portfolio Health**
- Total AUM: [Assets under management]
- Weighted average APR: [X%]
- Average loan term: [X days]
- Customer concentration: [Top 10 merchants <X%]

### 9.2 Reporting Cadence
- Daily dashboard: Active loans, payments, defaults
- Weekly report: Risk metrics, collections
- Monthly: P&L, portfolio analysis
- Quarterly: Regulatory reports, board reporting

---

## 10. Technology Infrastructure

### 10.1 Core Systems

| System | Purpose | Provider |
|--------|---------|----------|
| **Loan Origination System (LOS)** | Application & approval | [Custom / Vendor] |
| **Core Banking/Lending** | Account mgmt & settlement | [CoreConnect / Fiserv / Custom] |
| **Servicing Platform** | Payment collection & accounts | [Blend / Black Knight / Custom] |
| **Business Intelligence** | Reporting & analytics | [Tableau / Power BI / Looker] |
| **Fraud Engine** | Risk detection | [Sift Science / Kount] |

### 10.2 Data Architecture
- Real-time transaction database
- Data warehouse for analytics
- Event streaming (Kafka/Kinesis)
- Audit log storage (immutable)

---

## 11. Customer Experience

### 11.1 User Journeys

**Positive Path**:
Browse → Add to cart → Checkout → Check eligibility → Approve → Sign → Pay → Complete

**Edge Cases**:
- Declined applicant: Offer alternatives
- Pending review: Clear communication + timeline
- Payment issues: Multiple retry options + support

### 11.2 Communication Strategy

| Touchpoint | Channel | Frequency |
|------------|---------|----------|
| Application Status | Email, SMS, In-app | Immediate |
| Due Date Reminder | Email, SMS, Push | 3 days before |
| Missed Payment Alert | Email, Phone, SMS | 1 day after |
| Account Statements | Email, In-app | Monthly |

---

## 12. Success Metrics

✅ **Launch Metrics**
- [ ] 1000+ customers in first month
- [ ] 70%+ approval rate
- [ ] <5% default rate
- [ ] >90% payment success rate
- [ ] >4.5/5 NPS score

✅ **Growth Metrics**
- [ ] Month-over-month loan volume growth >20%
- [ ] Customer retention rate >85%
- [ ] Repeat purchase rate >60%
- [ ] Average loan value >$[X]

---

## 13. Risk Management Plan

### Risk Register

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| **Economic Downturn** | High | Medium | Conservative credit model |
| **Regulatory Change** | High | Low | Legal monitoring + agile compliance |
| **Fraud Ring** | Medium | Medium | Multi-layer fraud detection |
| **System Outage** | High | Low | Redundant infrastructure + DRP |
| **Data Breach** | High | Low | Encryption + SOC 2 compliance |

---

## 14. Go-to-Market Plan

### Phase 1: Soft Launch (Weeks 1-2)
- Close beta with [X] merchants
- 100 manual approvals/day
- Daily risk monitoring

### Phase 2: Pilot (Weeks 3-6)
- [X] merchants live
- 1000 approvals/day
- Weekly risk reviews

### Phase 3: Scale (Week 7+)
- All merchants eligible
- 10,000+ approvals/day
- Continuous monitoring

---

## 15. Appendix: Compliance Documents

### Templates & Checklists
- [ ] Disclosure statement (TILA)
- [ ] Privacy policy (GDPR/CCPA)
- [ ] Terms & conditions
- [ ] Collections playbook
- [ ] Customer dispute form
- [ ] Regulatory approval letter

---

## Approval & Sign-off

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Chief Product Officer | | | |
| Chief Risk Officer | | | |
| Chief Compliance Officer | | | |
| Chief Financial Officer | | | |
| General Counsel | | | |
