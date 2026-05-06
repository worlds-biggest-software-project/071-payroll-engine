# Standards & API Reference

> Project: Payroll Engine · Generated: 2026-05-06

## Industry Standards & Specifications

### ISO Standards

**ISO 20022 — Financial Services Messaging Standard**
- URL: https://www.iso20022.org/iso-20022-message-definitions
- The global XML-based messaging standard for financial transactions. The `pain.001` (Customer Credit Transfer Initiation) message type is the standard for initiating batch payroll credit transfers. The `pacs` (Payments Clearing and Settlement) message family governs inter-bank settlement of those transfers. Directly relevant to global payroll payment disbursement and any payroll platform targeting international payments or the FedNow / SEPA instant payment rails. The SEPA compliance deadline for structured ISO 20022 address data is November 2026.

**ISO 27001 — Information Security Management Systems**
- URL: https://www.iso.org/standard/27001
- Provides the framework for managing information security risks. Payroll platforms process highly sensitive personal financial data (bank account numbers, SSNs/TINs, compensation records) and are a primary target for fraud; ISO 27001 certification is expected by enterprise buyers and maps well to SOC 2 Type II controls.

### NACHA / ACH Standards

**NACHA Operating Rules — ACH Network Standards**
- URL: https://achdevguide.nacha.org/ach-file-details
- Developer Guide: https://achdevguide.nacha.org/
- The governing standard for Automated Clearing House direct deposit in the United States. The ACH file is a fixed-width 94-character ASCII format with a nested envelope: File Header → Batch Header → Entry Detail records → Batch Control → File Control. The Standard Entry Class (SEC) code for payroll direct deposit is `PPD` (Prearranged Payment and Deposit). Any US payroll engine generating ACH files for direct deposit must produce NACHA-compliant files. Nacha's Operating Rules and Guidelines are the authoritative specification; the ACH Developer Guide at `achdevguide.nacha.org` is the primary developer reference.

### US Federal Tax & Regulatory Standards

**IRS Publication 15 (Circular E) — Employer's Tax Guide**
- URL: https://www.irs.gov/publications/p15
- The primary IRS publication governing US federal income tax withholding, FICA (Social Security and Medicare) tax rates, FUTA liability, supplemental wage withholding rates, and reporting obligations. All US payroll calculation engines must implement the withholding tables and rules published here, which are updated annually. The 2026 version reflects current tax brackets, FICA wage bases, and supplemental rates.

**IRS Modernized e-File (MeF) — 94x XML Schema and Business Rules**
- URL: https://www.irs.gov/e-file-providers/modernized-e-file-mef-schemas-and-business-rules
- Program Overview: https://www.irs.gov/e-file-providers/modernized-e-file-mef-program-overview
- The IRS MeF system is the mandated electronic filing infrastructure for employer payroll tax returns (Forms 941, 940, 944) and information returns. Tax Year 2026 / Processing Year 2026 schemas use WSDL version R10.9 for the A2A (Application-to-Application) interface. Payroll platforms that file on behalf of employers require IRS e-file provider authorization and must conform to MeF XML schemas and business rules. The IRS provides an A2A MeF SDK Toolkit for developers.

**SSA EFW2 / EFW2C — Electronic W-2 Filing Specification**
- URL: https://www.ssa.gov/employer/EFW2&EFW2C.htm
- Specification PDF: https://www.ssa.gov/employer/efw/23efw2.pdf
- The Social Security Administration's specification for electronic W-2 wage data submissions. EFW2 is a fixed-length record format (not XML) with record types RE (Employer), RW (Employee Wage), RO (Employee Optional), RS (State Wage), and RT (Total). Payroll platforms that file W-2s on behalf of employers must generate EFW2-compliant files for submission to SSA Business Services Online (BSO). The 2026 filing deadline for employee copies and SSA Copy A was February 2, 2026.

**FLSA (Fair Labor Standards Act) — Overtime Calculation Specification**
- URL: https://www.dol.gov/agencies/whd/fact-sheets/23-flsa-overtime-pay
- DOL FLSA Overtime Calculator Advisor: https://webapps.dol.gov/elaws/otcalculator.htm
- Federal law governing minimum wage, overtime pay, and employee classification. The payroll calculation requirement is that overtime is paid at 1.5× the employee's "regular rate of pay" for all hours worked beyond 40 in a workweek. The regular rate is computed by dividing total workweek remuneration (minus statutory exclusions) by hours worked. A workweek is a fixed recurring 168-hour (7 consecutive 24-hour) period. Payroll engines must implement FLSA overtime correctly across multiple concurrent pay rates, bonuses, and shift differentials. IRS 2026 guidance also introduces a new deduction for qualified overtime compensation.

### W3C & IETF Standards

**RFC 7519 — JSON Web Token (JWT)**
- URL: https://datatracker.ietf.org/doc/html/rfc7519
- The standard for compact, URL-safe token-based claims representation. Used pervasively as the bearer token format in OAuth 2.0 / OpenID Connect flows, which are the dominant authentication patterns across all major payroll APIs (Gusto, ADP, Rippling, Paychex, Deel). A payroll API must issue and validate JWTs.

**RFC 6749 — OAuth 2.0 Authorization Framework**
- URL: https://datatracker.ietf.org/doc/html/rfc6749
- The foundational authorization framework governing how third-party applications obtain scoped access to payroll data on behalf of employers and employees. All major payroll APIs implement OAuth 2.0 authorization code flow for partner integrations.

**RFC 6750 — OAuth 2.0 Bearer Token Usage**
- URL: https://datatracker.ietf.org/doc/html/rfc6750
- Specifies how bearer tokens (JWTs) are transmitted in HTTP requests to OAuth 2.0-protected payroll API endpoints using the `Authorization: Bearer <token>` header.

**OpenID Connect Core 1.0**
- URL: https://openid.net/specs/openid-connect-core-1_0.html
- The identity layer on top of OAuth 2.0, enabling authenticated user identity assertions. Used by payroll platforms for employee single sign-on and partner application identity federation.

**RFC 7231 — HTTP/1.1 Semantics**
- URL: https://datatracker.ietf.org/doc/html/rfc7231
- Defines the HTTP methods (GET, POST, PUT, PATCH, DELETE), status codes, and media types that form the foundation of all REST payroll APIs.

### Data Model & API Specifications

**OpenAPI Specification 3.1 (OAS 3.1)**
- URL: https://spec.openapis.org/oas/v3.2.0.html
- The de facto standard for REST API description. Symmetry publishes a complete OpenAPI spec for its Tax Engine API. Best-practice payroll APIs should publish an OAS 3.1 spec to enable code generation, automated testing, and MCP server integration for AI agent consumption.

**HR Open Standards — Payroll Data Model (v4.x)**
- URL: https://www.hropenstandards.org/standards
- Downloads: https://www.hropenstandards.org/standards-downloads
- The HR Open Standards Consortium (formerly HR-XML, founded 1999) publishes a free JSON Schema and XSD data model for HR and payroll interoperability. The payroll specification covers worker setup in payroll systems including payment details, deductions, garnishments, and taxes, with localisations for the US, Canada, and the Netherlands. Version 4.5 is current as of 2026. The schema is available under a permissive licence for open source implementation.

**JSON Schema Draft 2020-12**
- URL: https://json-schema.org/specification
- Used as the validation schema format for payroll API request and response bodies, and for the HR Open Standards data model. A payroll calculation API should publish JSON Schema definitions for all its input/output objects to enable runtime validation and documentation generation.

### Security & Compliance Standards

**SOC 2 Type II — Service Organization Control**
- URL: https://www.aicpa.org/intl/soc/soc2.html
- The primary trust certification expected by enterprise payroll software buyers. SOC 2 Type II assesses the operational effectiveness of controls around security, availability, processing integrity, confidentiality, and privacy over a minimum 6-month period. Any payroll SaaS platform targeting mid-market or enterprise customers should pursue SOC 2 Type II attestation.

**GDPR (EU) 2016/679 — General Data Protection Regulation**
- URL: https://gdpr.eu/what-is-gdpr/
- Payroll data (names, addresses, bank details, tax identifiers, salary records) is personal data under GDPR. Any payroll platform processing data for employees located in the EU must have a valid legal basis for processing (typically contractual obligation), implement data minimisation and purpose limitation, support subject access requests and right to erasure, and report breaches to supervisory authorities within 72 hours. International transfers of EU employee payroll data require Standard Contractual Clauses (SCCs) or equivalent safeguards.

**CCPA / CPRA — California Consumer Privacy Act / Rights Act**
- URL: https://oag.ca.gov/privacy/ccpa
- California's privacy law applies to payroll platforms processing personal data of California employees. Requires disclosure of data collection practices, supports deletion requests, and prohibits selling personal information. The CPRA amendments (effective 2023) extend obligations to sensitive employment data including payroll records.

**NIST Cybersecurity Framework (CSF) 2.0**
- URL: https://www.nist.gov/cyberframework
- The NIST CSF provides a risk-based framework for managing cybersecurity risk. SOC 2 controls map directly to NIST CSF functions (Identify, Protect, Detect, Respond, Recover), and many enterprise procurement teams require NIST alignment for payroll software handling sensitive financial data.

**PCI DSS v4.0.1 — Payment Card Industry Data Security Standard**
- URL: https://www.pcisecuritystandards.org/
- Applies to payroll platforms that process employer funding via credit/debit card or that offer earned wage access (EWA) with card-based disbursement. All PCI DSS v4.0.1 requirements became mandatory on March 31, 2025; 2026 is the first full assessment cycle under the complete v4.0.1 rule set.

### FedNow & Real-Time Payment Standards

**FedNow Service — Instant Payroll Disbursement**
- URL: https://www.frbservices.org/financial-services/fednow/what-is-iso-20022-why-does-it-matter
- ISO 20022 Messages Overview: https://explore.fednow.org/resources/readiness-guide-iso-20022.pdf
- The Federal Reserve's instant payment rail (launched 2023) uses ISO 20022 message standards. FedNow enables same-day or faster payroll disbursements and is the infrastructure layer for earned wage access (EWA) products. Payroll engines targeting EWA or same-hour payroll must integrate with FedNow or RTP (The Clearing House) rails, both of which use ISO 20022.

---

## Similar Products — Developer Documentation & APIs

### Symmetry Tax Engine (by Paylocity)

- **Description:** The leading US payroll tax calculation API, covering 7,000+ federal, state, and local jurisdictions. Accepts a JSON request with employee address, filing status, pay frequency, and gross pay; returns precise withholding amounts across all applicable jurisdictions in ~3.32 ms average response time.
- **API Documentation:** https://docs.symmetry.com/reference/api-welcome
- **Developer Hub:** https://docs.symmetry.com/
- **Tax Logic API:** https://docs.symmetry.com/docs/ste-stl-tax-logic-api
- **Swagger / OpenAPI:** https://docs.symmetry.com/docs/ste-swagger-documentation
- **Webhooks (tax table updates):** https://www.symmetry.com/webhooks-by-symmetry
- **Standards:** REST / JSON; OpenAPI 3.x spec published; on-premise SDK also available
- **Authentication:** Enterprise API key / licence agreement; not publicly accessible

### Gusto Embedded Payroll

- **Description:** Gusto's white-label embedded payroll product allows third-party platforms to offer full-service US payroll (all 50 states, tax filing, W-2s, direct deposit) within their own applications. Targeted at software platforms (ISVs, HRIS providers) building payroll into their product.
- **API Documentation:** https://docs.gusto.com/embedded-payroll/docs/introduction
- **Developer Portal:** https://dev.gusto.com/
- **Webhooks:** https://docs.gusto.com/embedded-payroll/docs/webhooks
- **SDKs:** JavaScript / TypeScript, Python, Ruby (via community and official libraries)
- **Standards:** REST / JSON; OAuth 2.0 authorization code flow; tokens expire every 2 hours
- **Authentication:** OAuth 2.0; client_id / client_secret issued via developer portal registration

### ADP Workforce Now / RUN Powered by ADP

- **Description:** ADP's payroll and HCM platform APIs enable bidirectional integration for payroll input, payroll output, employee records, and workforce analytics. ADP DataCloud provides workforce benchmarking data via API.
- **Developer Portal:** https://developers.adp.com/
- **API Explorer:** https://developers.adp.com/apis/api-explorer
- **Payroll Output API Guide:** https://developers.adp.com/articles/guides/payroll-output-api-guide-for-adp-link
- **OData API Introduction:** https://developers.adp.com/articles/general/introduction-to-adp-api-open-data-protocol-odata
- **SDKs:** Java, .NET (via ADP API Central; must be purchased separately)
- **Standards:** REST / JSON; OData v4 supported for workforce analytics; OpenAPI/Swagger specs available via developer portal
- **Authentication:** OAuth 2.0; mutual TLS (mTLS) required for production; API access requires purchasing ADP API Central

### Rippling Platform API

- **Description:** Rippling's unified platform API exposes employee, payroll, benefits, IT, and expense data through a single REST interface, with a single employee record propagating changes across all modules.
- **Developer Portal:** https://developer.rippling.com/
- **API Reference:** https://developer.rippling.com/documentation/rest-api/reference/rippling-platform-api
- **API Reference (alt):** https://developer.rippling.com/docs/rippling-api/a310f900b0f84-api-reference
- **SDKs:** No official SDK; REST/JSON API consumed directly
- **Standards:** REST / JSON; camelCase field naming convention; OAuth 2.0 authorization code flow; API key auth available for server-to-server use
- **Authentication:** OAuth 2.0 (preferred); API key; partner application registration and approval required

### Deel Developer Platform

- **Description:** Deel's REST API covers global payroll, EOR, contractor management, compliance, and equity administration across 150+ countries. Includes an Adjustments API for syncing expenses, bonuses, and allowances directly into global payroll runs.
- **Developer Platform / Webhooks:** https://developer.deel.com/api/webhooks/introduction
- **API Documentation:** https://www.deel.com/hr-platform/api/
- **Open API Solutions:** https://www.deel.com/solutions/open-api/
- **SDKs:** REST/JSON consumed directly; sandbox environment available via Deel platform
- **Standards:** REST / JSON; webhook events for contract updates and payment status
- **Authentication:** OAuth 2.0; API tokens generated in Developer Center for production

### Paychex Developer Program

- **Description:** Paychex's REST API provides programmatic access to payroll processing, employee records, benefits, and time tracking for US-based employers. Sandbox environment available for development and testing.
- **Developer Portal:** https://developer.paychex.com/
- **API Documentation:** https://developer.paychex.com/documentation
- **Resources:** https://developer.paychex.com/resources/overview
- **SDKs:** Not specified; REST/JSON API
- **Standards:** REST / JSON; OpenAPI specification available via developer portal
- **Authentication:** OAuth 2.0 with Paychex client access credentials

### Workday Payroll REST API

- **Description:** Workday provides both SOAP and REST APIs covering HR, payroll, compensation, time tracking, and recruiting. REST API is the preferred modern integration path; SOAP APIs provide broader legacy coverage. Scheduled batch integration (nightly payroll feeds) is the dominant pattern for payroll data exchange.
- **REST API Guide:** https://www.reco.ai/hub/workday-rest-api-integration-security
- **SOAP API Tutorial:** https://www.apideck.com/blog/a-comprehensive-tutorial-on-setting-up-and-using-the-workday-api
- **Integration Reference:** https://assistnow.com/blog/workday-rest-api-guide
- **SDKs:** No official public SDK; integration via Workday Studio or REST API directly
- **Standards:** REST / JSON (preferred); SOAP / XML (legacy); OAuth 2.0
- **Authentication:** OAuth 2.0; Workday Integration System User (ISU) credentials required; bi-annual Workday release cycle requires ongoing API version management

### Finch — Unified HRIS & Payroll API

- **Description:** Finch provides a single unified REST API that abstracts over 200+ HRIS and payroll systems (ADP, Gusto, Rippling, Paychex, Workday, etc.), enabling third-party applications to read employment and payroll data from any connected provider through one standardised schema. SDKs available in JavaScript, Python, Java, Kotlin, and Go.
- **API Documentation:** https://developer.tryfinch.com/
- **Unified API Overview:** https://www.tryfinch.com/finch-api
- **Glossary:** https://developer.tryfinch.com/how-finch-works/unified-employment-api-glossary
- **SDKs:** JavaScript, Python, Java, Kotlin, Go (official)
- **Standards:** REST / JSON; unified data model across all integrated payroll providers
- **Authentication:** OAuth 2.0 (Finch Connect); long-lived access tokens; server-to-server only (access tokens must not be exposed client-side)

### Merge — Unified HRIS & Payroll API

- **Description:** Merge provides a unified API spanning 250+ HRIS and payroll integrations across 8 categories. Payroll-specific endpoints include payroll runs, pay statements, employees, benefits, bank info, and time off. Supports standardised pay statement data and programmatic write-back to payroll systems for managing contributions and deductions.
- **HRIS API Reference:** https://docs.merge.dev/hris/
- **Unified API Overview:** https://docs.merge.dev/merge-unified/hris/overview
- **Main Docs:** https://docs.merge.dev/
- **SDKs:** JavaScript/TypeScript, Python, Java, Go, Ruby, .NET (official)
- **Standards:** REST / JSON; token-based authentication with `Authorization: Bearer <token>` header; rate limits per Linked Account
- **Authentication:** Account token + API key pair; OAuth 2.0 used for end-user authorization (Merge Link)

---

## Notes

**Tax Table Data vs. Calculation Logic:**
The principal unresolved gap for an open-source payroll engine is not the calculation API itself (which can be standardised using OpenAPI 3.1 and the HR Open Standards payroll schema) but the tax table data layer. Symmetry's and Vertex's competitive moats are their proprietary compiled tax tables and the research staff maintaining them — not patentable or copyrightable logic. A viable OSS strategy must pair the open-source calculation core with a sustainable funding mechanism for continuous tax rule updates (e.g., a hosted subscription service similar to how timezone databases operate under IANA).

**Emerging: MCP Server for Payroll Calculation:**
Symmetry notes in its 2026 documentation that it publishes a complete OpenAPI spec that AI agent frameworks can consume directly, explicitly positioning the tax engine as an MCP-compatible tool server for agentic payroll workflows. An open-source payroll engine should design its API with MCP server compatibility from the outset, enabling AI agents to call payroll calculation endpoints as tools.

**ACH Same-Day and FedNow Coexistence:**
As of 2026, US payroll direct deposit can be delivered via traditional ACH (NACHA, T+1 or T+2 settlement), Same-Day ACH (NACHA, same business day), or FedNow instant rails (seconds, 24×7×365). A modern payroll engine should expose a payment rail selector that abstracts the underlying ACH vs. FedNow file format differences, allowing employers to choose disbursement speed without changing their payroll workflow.
