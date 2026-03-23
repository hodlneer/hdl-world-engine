# HDL Backend Integration Plan

## Purpose

This document defines how the HDL backend (`hdl-node-backend-api`) evolves to support the HDL canon.

HDL.fun is the end-user platform.  
Hodlneer represents the badge identity layer and should not dictate product nomenclature.

## Core Backend Principles

The backend must enforce these tenets across all modules:

- Handle = primary identifier for users.
- Wallet = authentication, ownership and routing layer, abstracted from the user experience.
- Proof = credibility system (badges) that reflects a user's history and status rather than wealth.
- API = a simple interface that hides protocol complexity while preserving safety and determinism.

## 1. Identity System (Handle)

### Requirements

- Every user must have a unique handle.
- Handles are case-insensitive and URL-safe.
- Handles must be indexed for fast lookup.

### Responsibilities

- Resolve handle -> user across all contexts (authentication, profile, wallet lookups).
- Resolve handle -> wallet(s) to support routing and sending.

### Suggested Endpoints

- `GET /users/:handle` - fetch user profile by handle.
- `GET /wallets/:handle` - fetch all wallets bound to a handle (across supported chains).

## 2. Wallet System

### Philosophy

Wallets should feel invisible but powerful. The backend should handle the complexity of multi-chain support and security while presenting a simple interface to clients.

### Requirements

- Support multiple blockchain networks (EVM, Solana, and extensible for future chains).
- Store a mapping of wallets per handle with metadata (chain, type, verification status).
- Provide a secure way to verify ownership of a wallet without exposing private keys.

### Suggested Endpoints

- `POST /auth/verify-wallet` - initiate and verify wallet signatures for authentication.
- `GET /wallets/:handle` - retrieve wallet bindings for a handle.
- `POST /wallets/send` - send tokens using handle-based routing.

## 3. Routing Engine

### Purpose

Allow users to send value to `@handle` rather than to raw wallet addresses. This decouples the user experience from chain addresses and makes cross-chain routing possible.

### Flow

- Input handle - the sender specifies `@handle` and, optionally, the desired chain and asset.
- Resolve user - the system resolves the handle to the user record.
- Resolve wallet - the system resolves the wallet binding for the specified chain. If multiple wallets exist, apply default preferences or user prompts.
- Execute transaction - the system signs and broadcasts the transaction via the appropriate chain client or wallet SDK.

### Priority

The routing engine must prioritize actions in this order:

- Safety - never compromise on private key or transaction integrity.
- Determinism - ensure that repeated identical requests yield the same result.
- Correctness - choose the correct wallet and network.
- Simplicity - keep the API surface easy for developers and users to understand.

## 4. Proof System (Hodlneer)

### Concept

Proof badges are not about wealth; they document when and how a participant engaged. Early adoption, community participation and on-chain activity matter more than balances. Hodlneer is the brand for this layer.

### Badge Types

- Claimed Identity - user has claimed a handle and verified their wallet.
- Social Proof - endorsements or validations from other handles.
- On-Chain Proof - blockchain data confirming activity (e.g. earliest transaction date).
- OG / Hodlneer Badge - special badge for early adopters or major contributors.

### Data Model

```text
Proof {
  id: string
  userId: string
  type: enum(Claimed, Social, OnChain, OG)
  metadata: json
  verified: boolean
  createdAt: datetime
}
```

### Suggested Endpoints

- `GET /proof-badges` - retrieve definitions of available badge types and requirements.
- `GET /users/:handle/proofs` - get all proofs associated with a handle.
- `POST /users/:handle/proofs` - claim or request verification of a proof.

## 5. Feed System

### Role

The feed is the aggregated timeline of content, activity and identity signals. It should:

- Present posts and reactions from followed handles.
- Attach badge data to handles.
- Surface wallet actions (e.g. tips) where appropriate.

### Suggested Endpoints

- `GET /posts` - fetch the general or personalized feed.
- `GET /users/auth/posts` - fetch a feed scoped to the authenticated user's follows or preferences.

## 6. Migration Rules

- HDL.fun = canonical identity - all official identity flows must resolve to HDL.fun URLs and handles.
- Hodlneer = badge system only - the term "Hodlneer" should not appear in API endpoints or user data models except as a badge brand.
- Legacy references must be phased out - any old references to Hodlneer as the product should be deprecated or aliased for backwards compatibility.

## Final Principle

For every feature, ask:

- identity -> HANDLE
- ownership -> WALLET
- status -> PROOF
- interaction -> FEED

If the answer does not align to these, the backend must adjust to enforce the system.
