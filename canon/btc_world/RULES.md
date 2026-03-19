# BTC WORLD - RULES

## Purpose

This document defines the **non-negotiable rules** governing BTC World.

These rules ensure that all implementations:
- Preserve Bitcoin's real-world behavior
- Maintain canonical consistency
- Prevent UX decisions from distorting protocol truth

If a feature, visualization, or interaction violates these rules,
**it must not be implemented.**

---

## RULE CATEGORY 1: PROTOCOL INTEGRITY

### Rule 1.1 - Immutability is Absolute

- Once a block is added, it cannot be changed, removed, or rewritten
- Historical data must always remain intact
- No "undo", "edit", or retroactive mutation is allowed

---

### Rule 1.2 - Time Flows Forward Only

- The blockchain grows in one direction
- No rewinding, replaying, or reversing canonical state
- Past states may be *observed*, but never *modified*

---

### Rule 1.3 - Scarcity Must Be Enforced

- Total supply must never exceed 21,000,000 BTC
- No duplication, minting, or artificial inflation
- Visualizations must not imply expandable supply

---

### Rule 1.4 - Consensus is Emergent, Not Assigned

- No central authority determines truth
- No voting systems or governance overlays
- Consensus must appear as the result of independent validation

---

## RULE CATEGORY 2: DECENTRALIZATION

### Rule 2.1 - No Central Point of Control

- No entity may be represented as "in charge"
- No visual center implying authority
- No privileged node or system component

---

### Rule 2.2 - All Nodes Are Equal

- Nodes must not be ranked, scored, or prioritized
- No "master node" or "leader node" representations
- All validation is independent

---

### Rule 2.3 - Network Distribution Must Be Visible

- The system must feel distributed
- Clustering must not imply hierarchy
- Spatial layouts must avoid centralized structures

---

## RULE CATEGORY 3: ENTITY BEHAVIOR

### Rule 3.1 - Entities Must Behave According to Bitcoin

- Transactions must follow correct lifecycle:
  - Created -> Broadcast -> Pending -> Confirmed
- Blocks must only be created via mining
- Nodes must validate independently

---

### Rule 3.2 - No Fictional Mechanics

The following are strictly forbidden:

- Instant confirmations
- Guaranteed transaction inclusion
- Deterministic mining outcomes
- Artificial acceleration of consensus

---

### Rule 3.3 - Mempool Must Remain Dynamic

- Transactions must exist in a pending state before confirmation
- The mempool must reflect:
  - Competition
  - Prioritization (fees)
  - Temporary storage

---

## RULE CATEGORY 4: USER INTERACTION

### Rule 4.1 - The User Cannot Override the System

Users must NEVER be able to:
- Modify blocks
- Force transaction inclusion
- Alter consensus
- Change protocol rules

---

### Rule 4.2 - The User is an Observer or Participant

Users may:
- Observe the network
- Track transactions
- Initiate transactions via wallet interface

Users may NOT:
- Control the network
- Act as an authority
- Break protocol constraints

---

### Rule 4.3 - Wallet is an Interface, Not Power

- Wallets create and sign transactions
- Wallets do not control the network
- Wallets must not be represented as dominant entities

---

## RULE CATEGORY 5: VISUALIZATION CONSTRAINTS

### Rule 5.1 - Visuals Must Preserve Meaning

- Aesthetic choices must not distort functionality
- Visual metaphors must map to real behavior
- Clarity is prioritized over spectacle

---

### Rule 5.2 - No Misleading Representations

The system must NOT visually imply:

- Central control
- Infinite scalability without constraints
- Instant settlement
- Guaranteed success

---

### Rule 5.3 - Abstraction is Allowed, Distortion is Not

- You may simplify visuals
- You may stylize representation

But you may NOT:
- Change underlying mechanics
- Introduce false concepts

---

## RULE CATEGORY 6: CROSS-WORLD BOUNDARIES

### Rule 6.1 - BTC World Rules Are Self-Contained

- HDL World must not override BTC World rules
- UI/UX layers cannot alter protocol behavior

---

### Rule 6.2 - Portals Do Not Modify Rules

- Entry into BTC World does not grant control
- Portals only change *location*, not *authority*

---

## RULE CATEGORY 7: IMPLEMENTATION CONSISTENCY

### Rule 7.1 - All Layers Must Agree

BTC World must remain consistent across:

- DOM (web)
- Three.js (3D)
- VR / AR
- Future engines (Unity / Unreal)

Different renderings must show the **same underlying truth**.

---

### Rule 7.2 - Simulation Must Reflect Reality

If simulation is used:

- It must follow Bitcoin's real rules
- It must not introduce fictional shortcuts
- It must not prioritize UX over correctness

---

## ENFORCEMENT PRINCIPLE

If any feature conflicts with:

- Bitcoin protocol reality
- These canonical rules
- Entity definitions

Then:

> The feature is invalid and must be rejected.

---

## Final Note

BTC World is not designed to be controlled.

It is designed to be **understood**.

These rules exist to protect that truth.

No matter how the system evolves-
these constraints must remain intact.
