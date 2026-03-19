# BTC WORLD - ENTITIES

## Purpose

This document defines the **canonical entities** that exist within BTC World.

Entities are the **fundamental components of the Bitcoin network**, translated into spatial and visual form.

Each entity must:
- Reflect real Bitcoin behavior
- Preserve protocol integrity
- Avoid abstraction that introduces false mechanics

---

## Entity Classification

All entities in BTC World fall into one of three categories:

1. **Structural Entities** - define the system's architecture
2. **Active Entities** - perform actions within the network
3. **Transitional Entities** - represent state changes over time

---

## STRUCTURAL ENTITIES

### 1. Block

**Definition:**
A Block is a container of validated transactions, permanently appended to the ledger.

**Properties:**
- Immutable once added
- References previous block (hash linkage)
- Contains a set of confirmed transactions
- Exists in a strict sequential order

**Behavior:**
- Created through mining
- Appended to the chain upon successful validation
- Never altered or removed in canonical representation

**Visualization Notes:**
- Represented as modular units forming a continuous chain
- Must visually reinforce permanence and sequence

---

### 2. Blockchain (Ledger Spine)

**Definition:**
The Blockchain is the ordered sequence of all Blocks.

**Properties:**
- Append-only
- Time-directional
- Globally shared state

**Behavior:**
- Continuously extends forward
- Represents the single source of truth

**Visualization Notes:**
- Must appear as a forward-extending structure
- No branching in canonical view (forks are abstracted away)

---

## ACTIVE ENTITIES

### 3. Node

**Definition:**
A Node is an independent validator that enforces Bitcoin's rules.

**Properties:**
- Equal to all other nodes
- Operates independently
- Maintains a full or partial copy of the blockchain

**Behavior:**
- Validates transactions and blocks
- Rejects invalid data
- Propagates valid information to peers

**Constraints:**
- No node has authority over another
- No central coordination

**Visualization Notes:**
- Must be distributed across space
- Must not imply hierarchy or centralization

---

### 4. Miner

**Definition:**
A Miner is a specialized node that performs proof-of-work to create new blocks.

**Properties:**
- Competes with other miners
- Consumes computational energy
- Selects transactions from the mempool

**Behavior:**
- Constructs candidate blocks
- Attempts to solve cryptographic puzzles
- Broadcasts successful blocks to the network

**Constraints:**
- Success is probabilistic
- No guaranteed winner
- No coordination between miners

**Visualization Notes:**
- Must reflect competition and energy expenditure
- Should not appear deterministic or scripted

---

## TRANSITIONAL ENTITIES

### 5. Transaction

**Definition:**
A Transaction is a state change representing the transfer of value.

**Properties:**
- Contains inputs and outputs
- Must be cryptographically signed
- Is either pending or confirmed

**States:**
1. Created
2. Broadcast
3. Pending (in mempool)
4. Confirmed (included in block)

**Behavior:**
- Propagates through nodes
- Becomes immutable once confirmed

**Visualization Notes:**
- Represented as moving signals or packets
- Must clearly transition from pending -> confirmed

---

### 6. Mempool

**Definition:**
The Mempool is the temporary holding space for unconfirmed transactions.

**Properties:**
- Exists across nodes (not globally singular, but conceptually unified)
- Continuously changing
- Prioritized by fees

**Behavior:**
- Receives new transactions
- Supplies transactions to miners
- Clears transactions upon confirmation

**Visualization Notes:**
- Represented as a dynamic, fluid layer of activity
- Must feel transient and constantly shifting

---

### 7. Hash

**Definition:**
A Hash is the cryptographic output that secures blocks and transactions.

**Properties:**
- Deterministic
- Unique to input data
- Irreversible

**Behavior:**
- Links blocks together
- Validates integrity
- Powers proof-of-work

**Visualization Notes:**
- Represented as transformation or encoding events
- Must feel abstract but precise

---

## SUPPORTING ENTITIES

### 8. Wallet (Observer Interface)

**Definition:**
A Wallet represents a user's interface to the Bitcoin network.

**Important Distinction:**
A wallet is **NOT part of the protocol itself**.
It is a **bridge between the user and BTC World**.

**Properties:**
- Holds keys (not coins)
- Signs transactions
- Tracks balances via the ledger

**Behavior:**
- Creates transactions
- Observes blockchain state

**Constraints:**
- Does not alter network rules
- Does not exist as a controlling entity

**Visualization Notes:**
- May appear as an interface layer or access point
- Should not be confused with protocol-native entities

---

## NON-ENTITIES (Important)

The following must NEVER be treated as entities in BTC World:

- "Accounts" (Bitcoin is UTXO-based, not account-based)
- "Balances" as stored objects (they are derived states)
- Central authorities or governing bodies
- Artificial scoring or ranking systems

---

## Entity Relationships

Wallet -> creates -> Transaction
Transaction -> enters -> Mempool
Miner -> selects -> Transaction
Miner -> creates -> Block
Block -> extends -> Blockchain
Node -> validates -> Block + Transaction

This flow must remain consistent across all implementations.

---

## Canon Constraints

All entities must:

- Reflect real Bitcoin mechanics
- Avoid introducing fictional behaviors
- Maintain decentralization
- Preserve immutability and scarcity

---

## Final Note

Entities are not UI elements.

They are **truth representations**.

Every visual, interaction, or experience in BTC World must be built from these entities-
and must never contradict them.
