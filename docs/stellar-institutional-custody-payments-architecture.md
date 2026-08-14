# Balance Institutional Custody and Payments for Stellar — Technical Architecture

## 1. Scope and objective

Balance will add production-grade Stellar support to its institutional custody and payments platform and integrate two approved SCF Integration List building blocks:

1. **Anchor Platform** for standards-based deposit, withdrawal, and cross-border payment interoperability.
2. **Stellar Disbursement Platform (SDP)** for institutional treasury and bulk-payment workflows.

Institutions will be able to create governed Stellar accounts, custody XLM and Stellar-issued assets, manage trustlines, and send or receive Stellar payments through Balance's API and operations console. The funded work covers Stellar account and transaction support, integration adapters for Anchor Platform and SDP, policy controls, reconciliation, monitoring, public documentation, testnet validation, and mainnet launch.

## 2. System context

Balance separates client orchestration from key management and signing:

1. **Balance API and console** — authenticated account creation, asset enablement, transaction initiation, approvals, and reporting.
2. **Policy and workflow engine** — role-based permissions, multi-user approvals, allowlists, transaction limits, and compliance controls.
3. **Stellar integration service** — transaction construction, sequence management, fee estimation, memo validation, trustline operations, submission, and status normalization.
4. **Anchor Platform adapter** — maps Balance clients, assets, custody accounts, and transaction states to applicable SEP-compatible deposit, withdrawal, and cross-border flows.
5. **SDP adapter** — connects SDP treasury and recipient-disbursement workflows to Balance approvals, custody signing, Stellar submission, webhook processing, and reconciliation.
6. **Custody signing layer** — isolated signing under Balance's institutional key-management controls; signing material is never exposed to application services.
7. **Stellar network layer** — redundant Horizon endpoints and Stellar RPC where required, with testnet used before mainnet release.
8. **Indexer and reconciliation layer** — ingests account effects, payments, operations, balances, and ledger status and reconciles them to Balance's internal ledger.
9. **Observability layer** — monitors endpoint health, ledger lag, submission latency, failed operations, sequence conflicts, unexpected asset activity, and reconciliation exceptions.

## 3. Core Stellar flows

### Account provisioning

A client requests a Stellar account through the Balance API. Balance creates the account record, applies the client's policy configuration, and returns the public address. Mainnet activation uses an authorized funding workflow. Account state and minimum-balance requirements are monitored continuously.

### Assets and trustlines

For non-native assets, the client supplies the asset code and issuer. The service validates the issuer, builds a Change Trust operation, routes it through approval and signing, and submits it to Stellar. Trustline state and limits are indexed and exposed through the Balance API.

### Payments

A payment request includes destination, asset, amount, and memo requirements. Balance validates the address, memo, trustline state, available balance, reserve requirements, and client policies. The Stellar adapter obtains the correct sequence number, constructs the envelope, estimates fees, and passes the unsigned payload to the signing layer. The signed envelope is submitted and monitored to ledger inclusion.

## 4. Anchor Platform integration

The Anchor Platform adapter will provide a standards-based boundary between Balance custody accounts and eligible Stellar on/off-ramp and cross-border workflows.

The adapter will:

- Configure supported assets, custody accounts, callbacks, and network settings.
- Map Balance client and transaction records to applicable Anchor Platform fields.
- Implement applicable authentication and customer/transaction information flows.
- Support deposit and withdrawal initiation, quote or transaction references where applicable, asynchronous status changes, and error mapping.
- Validate memos, destinations, assets, trustlines, and transaction state before signing.
- Consume callbacks idempotently and reconcile Anchor Platform status with Stellar ledger state and Balance's internal ledger.
- Preserve Balance approval policies and signing separation throughout the flow.

Completion evidence will include documented sandbox scenarios for successful, pending, rejected, expired, and failed transactions, followed by verifiable mainnet payment flows.

## 5. Stellar Disbursement Platform integration

The SDP adapter will allow institutional clients to initiate governed bulk disbursements while Balance retains custody policy, approval, signing, and reconciliation controls.

The adapter will:

- Map an SDP disbursement and its recipient payments to Balance transaction requests.
- Validate asset, amount, recipient address, memo, trustline, and reserve requirements.
- Route disbursement batches through configurable Balance approval quorums and limits.
- Construct and sign Stellar payments only after authorization.
- Return transaction hashes and normalized lifecycle states to SDP.
- Handle partial failure, retry, cancellation-before-signing, and duplicate-request scenarios.
- Reconcile each recipient payment against Stellar ledger inclusion and the parent disbursement.
- Emit auditable webhooks and exception reports.

Completion evidence will include a testnet multi-recipient disbursement, failure-recovery tests, audit records, and a mainnet pilot.

## 6. Monitoring and threat model

The onchain monitoring plan will cover:

- Horizon/RPC availability and ledger lag
- account sequence conflicts and stale submissions
- duplicate or replayed integration requests
- failed and abnormally delayed operations
- unexpected assets or trustline changes
- memo omissions or mismatches
- Anchor Platform callback authentication and state divergence
- SDP batch/recipient state divergence
- signing-boundary violations and unauthorized approval changes
- custody, network, and internal-ledger reconciliation exceptions

The threat model will examine endpoint compromise, callback spoofing, replay, sequence contention, malicious or malformed recipients, unsupported assets, trustline abuse, compromised application credentials, signing-service isolation, privilege escalation, and operational recovery. Critical findings must be resolved before mainnet launch. A redacted threat model and monitoring plan will be published.

## 7. Reliability and security controls

- Redundant network providers with health-based failover.
- Idempotency keys for API and integration requests.
- Per-account sequence locking.
- Destination, memo, asset, and trustline validation before signing.
- Segregated signing and application services.
- Role-based access, configurable approval quorums, allowlists, and limits.
- Encryption in transit and at rest, immutable audit logging, and operational alerting.
- Automated tests for malformed addresses, unsupported assets, insufficient reserves, missing trustlines, stale sequences, duplicates, callback replay, partial disbursements, and provider failure.
- Mainnet release gated by testnet tests, threat-model review, operational runbooks, and professional user testing.

## 8. Public outputs

Balance will publish Stellar-specific API documentation, Anchor Platform and SDP integration guides, sample requests, error mappings, test fixtures, a reference integration, a redacted threat model, and an onchain monitoring plan. Reusable non-sensitive adapter components will be released publicly where licensing and security constraints permit.

## 9. Delivery

**Milestone 1 — Foundation:** Stellar testnet connectivity, account and transaction model, Anchor Platform adapter foundation, automated tests, and public documentation v1.

**Milestone 2 — Integration:** Complete Anchor Platform flows, SDP multi-recipient disbursements, reconciliation, webhooks, threat model, onchain monitoring, and sandbox UAT.

**Milestone 3 — Mainnet:** Production infrastructure, operational review, public integration documentation, professional user testing, two institutional pilot validations, and mainnet launch of both selected building-block integrations.
