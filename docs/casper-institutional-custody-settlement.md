# Balance Institutional Casper Custody and Settlement Integration

**Applicant:** Balance (Paradiso Ventures Inc. and affiliates)  
**Contact:** Dustin Plett — dustin@balance.ca  
**Website:** https://balance.ca/  
**LinkedIn:** https://www.linkedin.com/in/dustinplett/  
**Telegram:** @cryptokroeger  
**Requested grant:** US$50,000  
**Delivery period:** 14 weeks  
**Architecture layer:** Infrastructure  
**Segment:** DeFi

## Project summary

Balance proposes to add production-grade Casper custody and transaction support to its institutional digital-asset platform. The integration will enable regulated and enterprise clients to securely hold CSPR, create policy-controlled Casper transactions, monitor confirmations, reconcile balances and activity, and export auditable records through Balance's existing institutional workflows and API. The project will include architecture and threat modelling, transaction construction and signing support, policy and approval controls, monitoring and reconciliation, automated testing, operational runbooks, and public integration documentation. By lowering the operational and compliance barriers to Casper adoption, the project is intended to make Casper more accessible to institutional allocators, fintechs, asset issuers, and ecosystem businesses.

## Problem and opportunity

Institutional users need more than wallet connectivity. They require segregation of duties, configurable approvals, transaction policies, audit trails, reconciliation, monitoring, incident procedures, and reliable API access. A native Casper integration within Balance would give institutions a controlled operating environment for holding and transacting CSPR and, over time, Casper-based assets.

For Casper, this creates infrastructure that can support institutional participation, treasury operations, exchange and fintech integrations, tokenized-asset initiatives, and stablecoin or settlement use cases. The integration is designed as reusable institutional infrastructure rather than a one-off wallet implementation.

## Technical scope

The project will deliver:

1. Casper network architecture, asset model, transaction lifecycle, node-provider, and threat-model documentation.
2. CSPR asset support within Balance's custody platform and API.
3. Transaction construction, validation, signing, broadcast, and confirmation monitoring.
4. Configurable policy controls, approval workflows, allowlists, limits, and audit events.
5. Balance and transaction reconciliation, failure handling, and operational monitoring.
6. Automated unit, integration, and testnet tests.
7. Client-facing API documentation, operational runbooks, and launch-readiness materials.

Balance will use Casper's supported node and SDK interfaces and will validate the implementation on testnet before production readiness. Security controls will follow Balance's existing institutional custody architecture, including separation of authorization and signing responsibilities, least-privilege access, comprehensive logging, and controlled release procedures.

## Milestones and budget

### Milestone 1 — Architecture and test foundation

**Timeline:** Weeks 1–3  
**Budget:** US$12,500

- Finalize Casper integration architecture and threat model.
- Define transaction, balance, confirmation, and failure-state schemas.
- Establish testnet connectivity and automated test fixtures.
- Document security, policy, reconciliation, and operational requirements.

### Milestone 2 — Custody and transaction integration

**Timeline:** Weeks 4–10  
**Budget:** US$25,000

- Add CSPR asset and account support.
- Implement transaction construction, validation, signing, broadcast, and confirmation monitoring.
- Integrate approval policies, allowlists, transaction limits, audit events, and reconciliation.
- Deliver automated unit and testnet integration coverage.

### Milestone 3 — Hardening, documentation, and launch readiness

**Timeline:** Weeks 11–14  
**Budget:** US$12,500

- Complete security and operational hardening.
- Publish integration documentation and client implementation guidance.
- Deliver monitoring, incident, and recovery runbooks.
- Incorporate institutional design-partner feedback and complete a readiness report.

## Expected impact

- Expand institutional access to CSPR through a custody platform built for regulated and enterprise workflows.
- Reduce the time and technical effort required for fintechs, funds, issuers, and other organizations to support Casper.
- Support additional on-chain transactions and TVL as institutional clients hold and transact CSPR and Casper-based assets.
- Create a foundation for future Casper settlement, tokenized-asset, staking, and stablecoin workflows.
- Provide reusable documentation and operational patterns for institutional Casper adoption.

## Sustainability

Following grant-funded delivery, Balance will maintain the integration as part of its supported product infrastructure, subject to client demand and production-readiness review. Balance's business model is based on institutional custody, platform, and transaction-related fees, giving the company an ongoing commercial incentive to operate and support successful network integrations after grant completion.

## Team

Balance is led by George Bordianu, co-founder and CEO, a second-time founder with an MSc in Computer Science from McGill University and prior experience as Director of Engineering at 500px. The management team includes senior leaders in engineering, product, finance, sales, compliance, risk, and institutional digital assets. Balance operates through Canadian and U.S. entities, including Balance Trust Company, an Alberta special-purpose trust company.
