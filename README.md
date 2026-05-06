# Payroll Engine

> Part of the [worlds-biggest-software-project](https://github.com/worlds-biggest-software-project) initiative.
>
> An AI-native, open-source payroll calculation engine with continuously updated multi-jurisdiction tax compliance.

Payroll Engine is a gross-to-net payroll calculation core for US federal, state, and local jurisdictions, designed for embedding in HR/ERP platforms or running as a standalone payroll system. It targets small and mid-market employers, platform builders, and ISVs who today must either pay $100K+ for proprietary tax APIs (Symmetry, Vertex) or stitch together expensive SaaS suites (Gusto, ADP, Rippling).

---

## Why Payroll Engine?

- **No viable open-source payroll engine exists.** OrangeHRM and similar OSS HRIS tools have only rudimentary pay-grade tracking — no tax calculation, no filing, no direct deposit — leaving the largest gap in OSS business software.
- **Incumbent SaaS pricing scales painfully.** Gusto Plus runs ~$8,160/year for 50 employees, Rippling reaches $12K–$21K, and Deel EOR hits $599/employee/month — costs that compound as headcount grows.
- **Tax-API licensing is gated to enterprise budgets.** Symmetry and Vertex charge ISVs $100K+ for embedded tax calculation, blocking smaller platform builders from entering the market.
- **Mid-market companies (50–500 employees) are underserved** by both SMB tools and enterprise suites; ADP's UX is widely cited as the primary complaint, and pricing is opaque.
- **Tax-rule maintenance lags.** Maintaining 7,000+ US jurisdictions plus international regimes is the blocker that has prevented OSS payroll from existing — a problem AI-driven monitoring can finally make tractable.

---

## Key Features

### Core Payroll Calculation

- Gross-to-net engine implementing IRS Circular E withholding, FICA, FUTA, and state income tax / SUI / SDI rules
- Supplemental wage withholding (flat-rate, aggregate, and annualised methods)
- Multiple simultaneous pay schedules (weekly, bi-weekly, semi-monthly, monthly)
- Off-cycle and correction payroll runs for bonuses, terminations, and retroactive pay
- Voluntary deductions: 401(k), FSA, HSA, health insurance premiums, and court-ordered garnishments with jurisdiction-specific ordering

### Compliance & Filing

- All 50-state employer and employee withholding, FUTA/SUTA, and new-hire reporting
- W-2, 1099-NEC, and quarterly 941/940 data generation in IRS- and SSA EFW2-compliant formats
- NACHA-compliant ACH direct deposit with two-day settlement; same-day ACH as an upgrade path
- Garnishment calculation and disbursement with court-order priority sequencing
- Version-controlled tax-table history for auditability in regulated industries

### Platform & Integration

- REST API for embedding the calculation core in HRIS, ERP, and accounting platforms
- General ledger journal export mapped to a configurable chart of accounts
- Employee self-service: pay stubs, W-2s, W-4 management, and direct deposit setup
- Multi-entity payroll with consolidated reporting across legal entities
- Hosted tax-table update subscription so self-hosted deployments stay current without rebuilding compliance research

---

## AI-Native Advantage

An LLM-driven monitoring layer ingests state and local legislative sources, classifies applicable rule changes, and validates updates against historical test cases before publishing — closing the multi-week lag that current providers experience. ML anomaly detection learns historical payroll patterns and flags statistical outliers (potential ghost employees, inflated hours, rate changes) before payment runs execute. AI-assisted FLSA exempt/non-exempt classification analyses job descriptions, duties, and compensation to recommend a classification with a documented, defensible rationale. Predictive state-registration detects first-hire-in-new-state events and initiates the registration workflow automatically.

---

## Tech Stack & Deployment

The project is intended to ship as an open-source calculation core with a REST API, deployable self-hosted or as a managed service. A hosted tax-table update subscription — analogous to how geodata services operate — funds the continuous compliance research while keeping the calculation engine itself permissively licensed. Standards alignment includes IRS Publication 15 (Circular E), SSA EFW2 wage reporting, NACHA ACH for direct deposit, FLSA overtime classification, and ISO 20022 for international payroll messaging. GDPR and CCPA controls are required for handling employee payroll data.

---

## Market Context

The global payroll software market is ~$8.35B in 2026, projected to reach $13.73B by 2035 at 5.7% CAGR (Business Research Insights), with the cloud-based segment growing faster at 9.6% CAGR to $28.2B by 2033. Primary buyers span small business owners (1–50 employees) seeking transparent SMB pricing, HR directors at mid-market companies (50–500 employees) needing multi-state compliance, global people-operations leaders, and ISVs embedding payroll-tax calculation into their own platforms. Incumbent annual spend ranges from ~$3,500 (ADP RUN, 50 employees) to ~$359K (Deel EOR, 50 employees).

---

## Project Status

> This project is in the **research and specification phase**.  
> Contributions, feedback, and domain expertise are welcome.

---

## Contributing

We welcome contributions from developers, domain experts, and potential users.
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Important:** All contributions must be your own original work or clearly attributed
open-source material with a compatible licence. Copyright infringement and licence
violations will not be tolerated and will result in immediate removal of the offending
contribution. If you are unsure whether a piece of code, text, or other material is
safe to contribute, open an issue and ask before submitting.

---

## Licence

Licence to be determined. See [discussion](#) for context.
