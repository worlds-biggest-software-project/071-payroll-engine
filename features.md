# Payroll Engine — Feature & Functionality Survey

> Candidate #71 · Researched: 2026-05-02

## Solutions Analysed

| Tool | Type | Licence / Model | URL |
|------|------|-----------------|-----|
| Gusto | Commercial SaaS | Proprietary / per-employee | https://gusto.com |
| ADP Workforce Now / RUN | Commercial SaaS | Proprietary / custom | https://www.adp.com |
| Paychex Flex | Commercial SaaS | Proprietary / per-employee | https://www.paychex.com |
| Rippling | Commercial SaaS | Proprietary / modular per-employee | https://www.rippling.com |
| Deel | Commercial SaaS | Proprietary / per-employee/EOR | https://www.deel.com |
| OnPay | Commercial SaaS | Proprietary / per-employee | https://onpay.com |
| Symmetry Tax Engine | Commercial API | Proprietary / enterprise API licence | https://www.symmetry.com |
| Vertex Payroll Tax | Commercial API | Proprietary / enterprise API licence | https://www.vertexinc.com |
| Payrun.io | Commercial SaaS | Proprietary / SaaS | https://payrun.io |
| OrangeHRM | Open Source | GPL v2 | https://www.orangehrm.com |

## Feature Analysis by Solution

### Gusto

**Core features**
- Full-service payroll for all 50 US states with automated federal, state, and local tax filing
- Multiple pay schedule support (weekly, bi-weekly, semi-monthly, monthly)
- ACH direct deposit with same-day and two-day deposit options
- W-2 and 1099 preparation and electronic filing
- Benefits administration: health insurance, dental, vision, FSA, HSA, and 401(k) integration
- PTO and time-off tracking integrated with payroll
- Contractor payments (domestic and international) with 1099-NEC filing
- Automated new-hire state reporting
- Employee self-service portal and mobile app

**Differentiating features**
- Best-in-class UX for small business payroll — consistently rated most user-friendly among all SMB payroll providers
- Transparent per-employee-per-month pricing with no hidden fees; most straightforward pricing model in market
- Same-day direct deposit available on all US-paid plans
- AI-driven compliance alerts: predictive notifications for new state registration requirements, tax rate changes, and new payroll legislation affecting the employer
- Gusto Wallet: employee financial wellness app with earned wage access, savings goals, and spending account

**UX patterns**
- Streamlined payroll run wizard: confirm hours, add one-time items, review, submit — typically under five minutes
- Employee self-onboarding with digital I-9, W-4, and direct deposit setup
- Mobile app for employees (pay stubs, W-2s, time-off requests) and employers (approve payroll, view reports)
- In-app compliance coaching alerts when payroll actions may trigger tax obligations

**Integration points**
- Native integrations with QuickBooks, Xero, FreshBooks, and major accounting platforms
- HRIS integrations: BambooHR, Rippling, and others via API
- 401(k) providers: Guideline, Human Interest, and others
- Time-tracking integrations: TSheets (QuickBooks Time), When I Work, Homebase
- REST API for custom integrations

**Known gaps**
- Not suited for companies with complex multi-entity structures or international employees beyond US/Canada
- Garnishment processing and complex deduction ordering require manual workarounds
- Limited payroll tax engine depth for local jurisdictions (e.g., Pennsylvania local Earned Income Tax complexity)
- No built-in global payroll; international contractors supported but not full EOR/employer-of-record

**Licence / IP notes**
- Fully proprietary SaaS (Gusto Inc.)

---

### ADP Workforce Now / RUN

**Core features**
- Full-service payroll for all 50 US states and Canada with tax filing and garnishment processing
- Multi-state payroll with automated nexus management and state registration support
- Garnishment management with court-ordered deduction prioritisation and disbursement
- Certified payroll for government contractors (Davis-Bacon compliance)
- Union payroll with collective bargaining agreement deduction rules
- W-2, W-2c, 1099, and ACA reporting
- General ledger integration with mapping to chart of accounts
- Advanced analytics and workforce insights dashboards
- ADP DataCloud: workforce benchmarking against ADP's database of 30+ million US workers

**Differentiating features**
- Unmatched compliance depth: ADP processes payroll for approximately 1 in 6 US workers; regulatory compliance is the core institutional capability
- ADP DataCloud benchmarking: unique access to anonymised workforce data from the broadest employer base enables compensation and retention benchmarking unavailable from any competitor
- ADP TotalSource PEO: professional employer organisation option for companies wanting to outsource HR, benefits, and payroll administration entirely
- Certified payroll and prevailing wage compliance for government and public works contractors

**UX patterns**
- Role-separated interfaces for payroll administrator and HR manager
- Payroll run approval workflow with checklist-based verification steps
- Compliance dashboard showing upcoming filing deadlines, rate changes, and regulatory alerts

**Integration points**
- 300+ pre-built integrations with ERP (SAP, Oracle, NetSuite), HRIS, benefits, and time-tracking systems
- ADP Marketplace with 600+ third-party app connectors
- REST API for custom integrations and data sync

**Known gaps**
- UX is significantly older and more complex than Gusto, Rippling, or OnPay; frequently cited as the primary complaint
- Opaque pricing with tendency to upsell modules; true all-in cost difficult to predict
- Implementation and onboarding can take weeks; less self-service friendly
- Global payroll offering (ADP Global Payroll) requires separate contracting and significant implementation effort

**Licence / IP notes**
- Fully proprietary (ADP Inc., NASDAQ: ADP, ~$100B market cap)
- Holds numerous process patents in payroll tax calculation and employer compliance but these are defensive; no relevant OSS project risk identified

---

### Rippling

**Core features**
- Unified payroll, HR, IT, and Finance platform with a single employee record across all modules
- Global payroll and EOR in 160+ countries
- Automated multi-state and multi-country payroll tax filing
- Equity/RSU payroll tax handling: supplemental withholding calculations, sell-to-cover coordination
- 1099 contractor management with annual filing
- Custom workflow automation with Rippling Automations (trigger-based rules for payroll-adjacent events)
- Global PEO and EOR services for hiring without a local entity
- Benefits administration integrated with payroll deductions

**Differentiating features**
- Platform unification: HRIS, payroll, IT provisioning, and expense management on one employee record — onboarding and offboarding actions automatically update payroll, IT access, and benefits simultaneously
- Fastest US state expansion: detecting a new-hire event in a new state and automatically initiating tax registration without employer action
- Global payroll and EOR in 160+ countries is the broadest international coverage of any all-in-one HCM/payroll platform
- RSU and equity payroll tax calculation natively embedded; specifically useful for tech company employees with material equity compensation

**UX patterns**
- Single-platform navigation across HR, IT, and Finance with consistent design language
- Automation builder with conditional logic for payroll-adjacent workflows (e.g., auto-enrol in benefits when headcount type changes)
- Employee self-service: benefit elections, equity grant acceptance, expense submissions in one app

**Integration points**
- 500+ native integrations across HR, finance, IT, and productivity tools
- REST API with extensive documentation
- Pre-built connectors for Carta, Brex, Ramp, and major expense/equity platforms

**Known gaps**
- Modular pricing adds up; full platform with all modules is one of the most expensive per-employee solutions
- Implementation complexity increases significantly for large international deployments
- Global payroll accuracy varies by country; some markets rely on local payroll partners rather than a native engine

**Licence / IP notes**
- Fully proprietary (Rippling Inc.; Series F at $13.5B valuation, 2024)

---

### Deel

**Core features**
- Global payroll in 150+ countries with local entity compliance
- Employer of Record (EOR) services for hiring without a local legal entity
- Contractor management and payment in 150+ currencies
- Compliance-as-a-service: Deel handles local employment contracts, benefits, statutory filings
- IP Assignment and NDAs generated automatically per local law
- Equity and ESOP administration for global employees
- Immigration support module (visa sponsorship workflows)

**Differentiating features**
- Largest country coverage for EOR and global payroll of any dedicated platform
- Compliance documentation automation: employment contracts, IP agreements, and onboarding documents generated to local legal standards automatically
- Deel HR: free HRIS layer included with payroll/EOR contracts; bundled approach reduces cost vs. separate HRIS + global payroll vendors
- Real-time compliance updates: local payroll rules updated automatically as regulations change in each covered country

**UX patterns**
- Country-selector-first interface: compliance requirements and contract terms surface based on selected country
- Employee self-service for document signing, expense submission, and payment tracking
- Employer dashboard showing global headcount, compliance status, and upcoming payroll dates by country

**Integration points**
- Native integrations with major HRIS platforms (BambooHR, Workday, Rippling)
- Accounting integrations: QuickBooks, Xero, NetSuite
- REST API with webhooks for event-driven integrations
- Carta integration for equity grant and cap table sync

**Known gaps**
- EOR pricing ($599/employee/month) is prohibitively expensive for large teams; not viable as a permanent global payroll solution for scale
- Global payroll (non-EOR) still relies on local payroll partners in many markets; accuracy depends on partner quality
- US domestic payroll is a secondary focus; less feature-depth than Gusto or ADP for US-only employers

**Licence / IP notes**
- Fully proprietary (Deel Inc.; $12B valuation at Series D, 2022)

---

### Symmetry Tax Engine

**Core features**
- API-based payroll tax calculation for 7,000+ US taxing jurisdictions (federal, all 50 states, and local)
- Gross-to-net calculation with all mandatory and voluntary deductions
- Supplemental wage withholding calculation (flat rate, aggregate, and annualised methods)
- Garnishment calculation and ordering rules per jurisdiction
- Retroactive pay and off-cycle adjustment calculation
- W-2 and 1099 data preparation
- Tax table updates pushed via API as rules and rates change

**Differentiating features**
- Designed as an embedded engine for ISVs and HCM platform builders; not an end-user product
- Broadest US jurisdiction coverage of any payroll tax API (7,000+ jurisdictions including Pennsylvania local EIT, Ohio RITA/RITA, and other complex local tax regimes)
- Tax table maintenance is a continuous service: Symmetry employs a dedicated tax research team that monitors and updates rules for all jurisdictions as they change

**UX patterns**
- No user interface; purely API-driven
- Well-documented REST API with calculation request/response schema
- Test environment with expected calculation outputs for validation

**Integration points**
- REST API consumption; integrates into any payroll engine that calls the calculation endpoint
- Supports all common payroll calculation architectures

**Known gaps**
- US-only coverage; no international payroll tax calculation
- Not a complete payroll solution; employers still need a platform layer for pay runs, employee management, and filing
- Expensive for ISVs at scale; $100K+ enterprise API licences create cost pressure

**Licence / IP notes**
- Fully proprietary (Symmetry Software, now owned by Paylocity)
- Tax table data and calculation rules: no copyright on underlying tax law, but Symmetry's compiled tables and update cadence are proprietary

---

### OrangeHRM

**Core features**
- HRIS with employee records, leave management, and time and attendance tracking
- Basic payroll module for pay grade configuration and salary tracking
- Recruitment, performance management, and training modules
- Self-service portal for employees and managers

**Differentiating features**
- GPL v2 open-source core enables full self-hosting with no licence cost
- Modular architecture allows organisations to deploy only needed modules

**UX patterns**
- Traditional HRIS interface; functional but dated compared to modern HCM platforms
- Module-based navigation with role-separated employee and admin views

**Integration points**
- REST API for integration with accounting and payroll systems
- LDAP authentication support

**Known gaps**
- Payroll module is rudimentary: pay grade tracking and basic salary management only; no tax calculation, no filing, no direct deposit
- No jurisdiction-specific payroll tax compliance; not a functional payroll engine for any jurisdiction
- Requires significant customisation to serve as a real payroll platform

**Licence / IP notes**
- GPL v2: copyleft; commercial use permitted but derivative works must be GPL
- No patent concerns for payroll-relevant functionality

---

## Cross-Cutting Feature Themes

### Table-Stakes Features
- Gross-to-net payroll calculation with all mandatory deductions (federal income tax, FICA, state income tax, state-specific taxes like SDI and SUI)
- Direct deposit via ACH (NACHA-compliant) with same-day and two-day options
- Support for multiple pay schedules simultaneously (weekly, bi-weekly, semi-monthly, monthly)
- W-2 and 1099-NEC annual reporting with electronic filing to IRS and SSA EFW2 format
- All 50-state tax filing: employer and employee withholding, unemployment insurance (FUTA/SUTA), and new-hire reporting
- Voluntary deduction management: retirement contributions (401k limits: $23,500 employee / $70,000 combined in 2026), FSA, HSA, garnishments
- Employee self-service portal for pay stub access, W-2 download, and direct deposit management
- Off-cycle payroll runs for corrections, bonuses, and termination pay
- Payroll journal entry output for accounting system integration
- Multi-state payroll support with nexus management

### Differentiating Features
- AI-powered compliance monitoring: proactive alerts for new-hire state registration obligations, tax rate changes, and emerging legislative requirements
- Garnishment ordering and disbursement automation with court-order parsing and priority sequencing
- RSU/equity payroll tax calculation: supplemental withholding for vest events, sell-to-cover tax settlement coordination
- Global payroll and EOR coverage for internationally distributed workforces
- Platform unification: single employee record propagating payroll changes to HRIS, IT provisioning, and benefits simultaneously (Rippling model)
- Earned Wage Access (EWA): employees access accrued wages before pay date without employer credit exposure
- AI-driven anomaly detection on payroll runs: flagging statistical outliers before payment execution
- Predictive state registration: detecting first-hire-in-new-state events and initiating registration workflows automatically

### Underserved Areas / Opportunities
- No viable open-source payroll calculation engine covering even US federal and state taxes — the single largest gap in OSS business software
- OSS gross-to-net calculation core with API-accessible tax tables (funded via hosted table update subscription) would enable platform builders to avoid $100K+ Symmetry/Vertex licences
- AI-powered exempt/non-exempt FLSA classification assistance with documented defensibility for audit
- Transparent, auditable payroll calculation with version-controlled tax table history (critical for regulated industries and government contractors)
- Mid-market companies (50–500 employees) are underserved by both SMB tools (Gusto) and enterprise tools (ADP Workforce Now) — a well-designed OSS platform with hosted managed services could fill this gap

### AI-Augmentation Candidates
- Automated multi-jurisdiction tax rule monitoring: LLMs ingesting state and local legislative sources, classifying applicable rule changes, and validating against test cases before pushing updates
- Payroll anomaly detection: ML models learning historical payroll patterns and flagging statistically unusual entries (potential fraud, input errors) before payment execution
- Exempt/non-exempt FLSA classification: LLM analysis of job descriptions, duties, and compensation to recommend classification with documented rationale
- Proactive state compliance: detecting new-hire events in new jurisdictions and automatically initiating registration workflows
- Natural-language payroll Q&A: employees asking "Why is my net pay different this period?" and receiving a plain-English explanation of the calculation changes

---

## Legal & IP Summary

The payroll calculation domain is governed by public law (IRS publications, state statutes, and court orders for garnishments) that carries no copyright or patent restrictions. Building a gross-to-net calculation engine implementing IRS Circular E withholding tables, FICA rules, state income tax formulas, and FLSA overtime calculations is legally unencumbered at the algorithmic level. Symmetry's and Vertex's proprietary assets are their compiled tax table databases and the research services maintaining them — not the underlying calculation logic. OrangeHRM is GPL v2, which would require derivative works to also be GPL and is therefore not an appropriate base for a commercial open-source project with a permissive-licence hosted tier. ADP holds defensive patents related to payroll processing workflows, but none have been asserted against new entrants and none cover the fundamental calculation approaches an OSS engine would use. No patent-encumbered techniques were identified for standard payroll tax calculation, direct deposit processing, or garnishment ordering logic.

---

## Recommended Feature Scope

**Must-have (MVP)**:
- Gross-to-net payroll calculation engine with US federal, state, and local (FICA, FIT, FUTA, SIT, SUI, SDI) tax support
- Direct deposit via NACHA ACH with two-day settlement; same-day ACH as optional upgrade
- Multiple pay schedule support (weekly, bi-weekly, semi-monthly, monthly) simultaneously
- W-2, 1099-NEC, and quarterly 941/940 filing data generation (employer-filed or service-filed)
- Employee self-service portal: pay stubs, W-2s, direct deposit setup, W-4 management
- Voluntary deductions: 401(k), FSA, HSA, health insurance premiums, and court-ordered garnishments
- Off-cycle and correction payroll runs
- GL journal entry export mapped to configurable chart of accounts
- REST API for integration with HRIS and accounting platforms

**Should-have (v1.1)**:
- All 50-state tax filing automation with employer registration workflow support for new states
- AI-powered anomaly detection on payroll runs before payment execution
- RSU/equity vest payroll tax calculation with supplemental withholding method selection
- Proactive state registration workflow: first-hire-in-new-state detection and registration initiation
- Multi-entity payroll with consolidated reporting across legal entities

**Nice-to-have (backlog)**:
- Global payroll coverage (Canada as first market; UK/EU as second phase)
- Earned Wage Access (EWA) with employer-funded or third-party-funded settlement
- AI-assisted exempt/non-exempt FLSA classification with documented rationale export
- Certified payroll reports for Davis-Bacon government contractor compliance
- Predictive AI compliance alerts for upcoming regulatory changes by state and jurisdiction
