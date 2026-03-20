# HDL World — Routing Engine (Canonical)

## Purpose

The Routing Engine defines how HDL resolves a user's handle into the correct wallet, chain, and execution path.

It is the system that makes this promise real:

> **Your Handle — Your Wallet**

The user should not need to know:

- which wallet holds the asset
- which blockchain the asset belongs to
- which route is required to deliver it
- whether a bridge, swap, or chain-specific action is involved

They only need to know the recipient's **HDL handle**.

HDL resolves the rest.

## Related Documents

Parent world docs:
- `_WORLD_OVERVIEW.md`
- `RULES.md`

Shared dependencies:
- `../shared/WALLET_MODEL.md`
- `../shared/ENGINE_PIPELINE.md`

Sibling implementation docs:
- `IDENTITY_ANCHOR.md`
- `WORLD_TOPOLOGY.md`
- `PROOF_ENGINE.md`

---

## Core Principle

> Handles are for humans.  
> Routing is for the engine.

The Routing Engine exists to dissolve crypto friction.

It turns:

- addresses
- chains
- wallet fragmentation
- bridge complexity
- token confusion

into a single human-readable interaction model.

---

## Mission

To make sending value as simple as:

```text
Send BTC to @grandma
Send ETH to @uncle_ray
Send USDC to @lex
```

without requiring the sender to understand:

- wallet topology
- chain selection
- address format
- protocol-level execution paths

---

## The Problem It Solves

Traditional crypto requires users to know:

- the exact destination address
- the correct chain
- whether a token is native or wrapped
- whether an asset needs bridging first
- whether the recipient even supports that asset

This creates:

- user fear
- failed transfers
- lost funds
- onboarding friction
- permanent distrust

The Routing Engine eliminates that burden.

---

## Core Concept

An HDL handle is not merely a username.

It is a **routing identity**.

That identity resolves into:

- a wallet graph
- asset compatibility rules
- preferred destination wallets
- chain-specific delivery logic
- privacy and permission settings

---

## Routing Model

```ts
type RoutingIntent = {
  senderHandle: string
  recipientHandle: string
  assetSymbol: string
  amount: string
  sourceChain?: string
  destinationPreference?: string
}
```

The engine transforms that intent into an execution plan.

---

## Routing Layers

### 1. Identity Resolution Layer

Resolve the HDL handle into a recipient identity.

Input:
- `@handle`

Output:
- user record
- linked wallets
- routing permissions
- supported chains
- asset preferences

This layer answers:

> Who is the recipient?

---

### 2. Wallet Graph Layer

Each user may have multiple wallets across multiple chains.

Example:

```ts
type WalletGraph = {
  handle: string
  wallets: Array<{
    chain: string
    address: string
    type: "embedded" | "external" | "custodial" | "smart"
    accepts: string[]
    priority: number
  }>
}
```

This layer answers:

> What wallets exist for this user?

---

### 3. Asset Classification Layer

Determine what kind of asset is being sent.

Examples:

- BTC
- ETH
- XRP
- SOL
- USDC
- wrapped assets
- future HDL-native assets

This layer answers:

> What is this asset, really?

It must identify:

- native asset
- token standard
- home chain
- equivalent representations
- whether chain mismatch exists

---

### 4. Destination Selection Layer

Select the most appropriate destination wallet for the asset.

Selection rules may consider:

- native chain compatibility
- explicit recipient preference
- safest path
- least conversion required
- lowest trust assumption
- best UX outcome

This layer answers:

> Where should this asset actually land?

---

### 5. Execution Planning Layer

Build the route required to complete delivery.

Possible route types:

- direct send
- same-chain token transfer
- smart wallet handoff
- chain abstraction execution
- bridge + deliver
- swap + deliver
- fallback reject

This layer answers:

> What must happen to complete the transfer safely?

---

### 6. Confirmation / Explainability Layer

Before execution, the engine should be able to explain:

- what asset is being sent
- what wallet it will land in
- what chain it will use
- whether any bridge or conversion is involved
- estimated fee exposure
- whether the route is direct or abstracted

This layer answers:

> Can the system explain the route truthfully?

---

## Routing Priorities

The engine should prioritize in this order:

1. **Safety**
2. **Determinism**
3. **Asset correctness**
4. **Recipient compatibility**
5. **User simplicity**
6. **Cost optimization**
7. **Speed**

Never reverse this order.

A cheap route that is ambiguous is worse than a slightly more expensive route that is correct.

---

## Preferred Routing Behaviors

### Direct Native Delivery

Best-case scenario.

Example:
- Sender sends BTC
- Recipient has BTC-compatible wallet
- Asset lands directly

No bridging. No conversion. No ambiguity.

---

### Handle-Based Resolution

The sender should never need to paste an address if the recipient has a valid HDL handle.

This is the defining UX behavior of the platform.

---

### Recipient Preference Resolution

Some users may explicitly choose:

- preferred wallet per asset
- preferred wallet per chain
- preferred default routing behavior

Example:
- BTC always to cold wallet
- ETH always to embedded HDL wallet
- Stablecoins always to Base wallet

The engine should respect these preferences where safe.

---

### Chain-Aware Routing

The engine must know that:

- BTC does not belong in an EVM wallet unless intentionally wrapped
- native ETH and ERC-20 assets are not interchangeable by default
- XRP, SOL, and BTC each require chain-specific handling
- asset symbol alone is not enough to determine route

This is non-negotiable.

---

## Routing Outcomes

Every request must resolve into one of the following:

### 1. Direct Success Path
Safe, deterministic, asset-compatible.

### 2. Abstracted Success Path
Requires internal orchestration (bridge, swap, chain abstraction) but can be completed safely.

### 3. User Confirmation Required
The route is possible, but not trivial enough to execute silently.

### 4. Rejected Path
Unsafe, ambiguous, unsupported, or conflicts with recipient rules.

---

## Silent vs Explicit Routing

### Silent Routing Allowed When:
- direct compatible path exists
- no asset conversion required
- no ambiguity exists
- sender intent is obvious
- recipient has valid configured wallet

### Explicit Confirmation Required When:
- bridge is required
- swap is required
- wrapped/native ambiguity exists
- destination wallet differs from user expectation
- route introduces material fees or trust assumptions

---

## Wallet Types

The Routing Engine must support multiple wallet classes.

### Embedded Wallets
HDL-managed or app-native wallet experiences.

### External Wallets
User-linked wallets (Metamask, Ledger, Phantom, etc.)

### Smart Wallets
Programmable wallets with automation / session capability.

### Custodial Wallet References
Optional integrations where the platform can verify ownership or route metadata without directly controlling funds.

---

## Identity as Routing Infrastructure

A handle is more than display identity.

It becomes infrastructure.

That means HDL handles must support:

- wallet binding
- asset binding
- routing preferences
- proof / trust metadata
- privacy controls
- future permissions and delegation

---

## Privacy Rules

The Routing Engine must protect the user.

It should never expose:

- raw wallet graph publicly
- balances by default
- exact routing logic to unauthorized viewers
- sensitive wallet relationships

Users may reveal:
- supported assets
- receive-enabled status
- preferred visible wallet labels

without exposing the full graph.

---

## Anti-Failure Rules

The Routing Engine must prevent:

- sending BTC to the wrong chain
- token-standard mismatch
- ambiguous handle resolution
- duplicate handle impersonation
- unsupported asset delivery
- unsafe automatic bridging
- silent conversion without consent

If certainty is not high enough, the engine must stop.

---

## Confidence Model

Each routing plan should receive a confidence state.

Example:

```ts
type RoutingConfidence =
  | "direct-safe"
  | "safe-with-confirmation"
  | "complex-user-review"
  | "reject"
```

The engine should never pretend uncertain routing is safe.

---

## Explainability Requirement

Every route must be explainable in plain language.

Example:

> Sending BTC to @grandma will deliver native BTC to her preferred Bitcoin wallet.

Or:

> Sending USDC to @grandma requires delivery on Base because that is her configured stablecoin destination.

Or:

> This route would require a bridge from Ethereum to Solana. Confirmation required.

If the route cannot be explained clearly, it is not ready for execution.

---

## Relationship to OD

OD may assist the user in understanding the route.

OD may:

- explain what the engine is doing
- warn about unusual paths
- answer “why did it choose this wallet?”
- educate users on routing logic

But OD does not replace the Routing Engine.

OD interprets.

The Routing Engine decides.

---

## Relationship to Identity Anchor

The Routing Engine powers action.

The Identity Anchor powers presence.

One determines:

> Where value goes.

The other determines:

> Where the person appears in the HDL universe.

Together, they unify utility and meaning.

---

## Relationship to Proof Engine

The Proof Engine validates conviction and history.

The Routing Engine enables present-day action.

Proof gives a user historical gravity.

Routing gives a user practical utility.

Together, they make the HDL handle valuable.

---

## Future Extensions

The Routing Engine should be extensible to support:

- delegated routing permissions
- family / recovery routing models
- business / treasury routing profiles
- AI-assisted route explanation
- batched multi-asset sends
- NFT and non-fungible asset delivery
- subscription / recurring payment rails
- universal paylinks using HDL handles

---

## Canonical UX Promise

The Routing Engine is one of HDL's foundational promises.

It exists so that the world of crypto can move from:

> “What address do I use?”

to:

> “Just send it to my handle.”

That transition is not cosmetic.

It is civilizational UX progress for crypto.

---

## Final Statement

> Wallets hold assets.  
> Addresses receive them.  
> HDL handles make them human.

The Routing Engine ensures that value can move through the HDL universe with:

- safety
- clarity
- determinism
- dignity

So the user does not have to think like a protocol engineer
to participate in the future of finance.

---

## Status

**Canonical — Utility / Routing Layer**
