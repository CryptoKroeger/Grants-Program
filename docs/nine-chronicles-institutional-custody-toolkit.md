# Balance Institutional NCG Custody and Open-Source Wallet/API Toolkit

## Applicant

Balance, led for this application by Dustin Plett (`dustin@balance.ca`).

## Project goal

Balance will develop an open-source toolkit and institutional implementation specification for secure Nine Chronicles Gold (NCG) wallet, transaction, monitoring, and reconciliation workflows. The work directly addresses the Nine Chronicles Software Grant Program wishlist item for an NCG wallet integration and supplements it with reusable API examples, automated tests, operational guidance, and institutional control patterns.

The grant-funded output will be published under the Apache 2.0 license. Balance may separately evaluate integration into its proprietary regulated custody platform, but grant funds will support the reusable ecosystem toolkit described here.

## Motivation and ecosystem value

Nine Chronicles has a distinctive player-owned economy, but professional organizations, ecosystem partners, treasury operators, and service providers need stronger operational tooling to manage NCG securely. A reusable integration toolkit can shorten implementation time, reduce transaction-handling mistakes, improve monitoring and reconciliation, and make NCG support more accessible to wallet developers and institutional infrastructure providers.

Balance has operated institutional digital-asset custody infrastructure since 2017. Its platform supports offline and warm custody, policy-controlled wallets and transactions, monitoring, reconciliation, compliance workflows, settlement, APIs, and webhooks. Balance publicly reports more than $2.5 billion in assets under custody, more than one million on-chain transactions, and more than three million wallets created.

## Software specification

The project will deliver:

1. An NCG integration and threat-model specification covering wallet lifecycle, address validation, transaction construction, signing boundaries, fee handling, confirmation policy, error recovery, and reconciliation.
2. A reference API/RPC client and example service for common NCG wallet and transaction operations.
3. Policy-control examples for transaction initiation, approval separation, destination controls, and operational limits.
4. Monitoring and reconciliation components covering transaction state, confirmations, balances, exceptions, and retry-safe processing.
5. Automated fixtures and tests for normal and failure-path transaction lifecycles.
6. Developer documentation, deployment guidance, and institutional operating runbooks.
7. A testnet demonstration and final production-readiness report.

## Roadmap, milestones, and budget

### Milestone 1 - Architecture, security model, and test framework

- Timing: September 1-30, 2026
- Budget: 5,000 NCG
- Deliverables:
  - Technical requirements and architecture
  - NCG wallet and transaction lifecycle mapping
  - Threat model and control specification
  - API/RPC interface definitions
  - Automated test plan and initial fixtures
  - Public repository and Apache 2.0 licensing

### Milestone 2 - Open-source implementation and testnet validation

- Timing: October 1-31, 2026
- Budget: 10,000 NCG
- Deliverables:
  - Reference NCG API/RPC client and example service
  - Wallet, transaction, monitoring, and reconciliation modules
  - Policy-control examples
  - Testnet deployment and automated lifecycle tests
  - Integration documentation and sample workflows

### Milestone 3 - Hardening, documentation, and ecosystem handoff

- Timing: November 1-30, 2026
- Budget: 5,000 NCG
- Deliverables:
  - Security and failure-mode review
  - Expanded automated tests and operational runbooks
  - Final developer documentation and examples
  - Demonstration for Planetarium and ecosystem stakeholders
  - Production-readiness assessment and future-maintenance plan

## Total request

20,000 NCG. Balance will contribute management, institutional product expertise, compliance review, and internal infrastructure beyond the grant request. The grant is not intended to cover all project costs.

## Success measures

- Public Apache 2.0 repository containing the complete toolkit
- Successful testnet wallet and transaction lifecycle demonstration
- At least 50 automated successful and failure-path lifecycle tests
- Reconciliation output matching observed network state across the test suite
- Published developer documentation and institutional operating guidance
- At least two technical feedback sessions with Planetarium or ecosystem developers
- A documented production-readiness decision and maintenance plan

## Completion date

November 30, 2026.

## Team

- Dustin Plett - Project Lead and Chief Sales Officer
- George Bordianu - Co-founder and Chief Executive Officer
- Vladimir Li - Chief Technology Officer
- Nuno Silva - Chief Product Officer
- Olivier Jodoin - Chief Financial Officer
- Alessandro Tocco - Chief Compliance and Risk Officer

## References

- Balance: https://balance.ca/
- Balance Custody API: https://balance-1.gitbook.io/balance-custody-api
- Grant working repository: https://github.com/CryptoKroeger/Grants-Program
