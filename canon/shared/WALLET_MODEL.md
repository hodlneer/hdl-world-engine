
# WALLET_MODEL.md
## HDL / HODLNEER Canonical Wallet Model

This document defines the wallet architecture used across the HDL ecosystem.

The system operates across three distinct layers. These layers must remain conceptually separate.

## Related Documents

Parent navigation:
- `../CANON_INDEX.md`

Shared architecture siblings:
- `ENGINE_PIPELINE.md`
- `VISUALIZATION_RULES.md`

World dependencies:
- `../hdl_world/ROUTING_ENGINE.md`
- `../hdl_world/IDENTITY_ANCHOR.md`

---

# 1. Social Identity Layer

Route format:

/u/{username}

Example:

/u/stephan

This layer represents:

- user identity
- social profile
- posts
- followers
- tags
- reputation
- community engagement

This layer **does not directly store blockchain assets**.

It represents the **person within the HDL network**.

---

# 2. Universal Handle Wallet

Route format:

/@{username}

Example:

hdl.fun/@stephan

This wallet functions as a **universal routing wallet**.

Funds sent to the handle are automatically routed to the correct blockchain wallet.

Example routing:

BTC → Bitcoin wallet  
ETH → Ethereum wallet  
XRP → XRP wallet  
SOL → Solana wallet  

The handle wallet is therefore a **routing abstraction**, not the asset container.

---

# 3. Blockchain Asset Wallet Layer

These are the **actual blockchain wallets** that hold assets.

Examples:

- Bitcoin wallet
- Ethereum wallet
- XRP address
- Solana wallet

These wallets exist on their respective chains independently of HDL.

HDL provides:

- identity linkage
- wallet discovery
- visualization
- cross-chain routing

---

# 4. Wallet Visualization Mapping

Blockchain wallets may activate nodes inside network visualizations.

Example:

Bitcoin wallets activate nodes inside the **Bitcoin Sphere**.

Important rules:

- Nodes represent **network participation**
- Nodes do **not represent asset quantity**
- Wallet balances never create additional nodes

Example:

A wallet with 0.1 BTC and a wallet with 5 BTC both activate a node.
Visual intensity may vary, but node count does not.

---

# 5. Identity Flow

The full identity stack is:

User Profile  
↓  
Universal Handle Wallet  
↓  
Blockchain Wallets  
↓  
Network Visualization Nodes  

Example flow:

User creates profile → connects wallet → node activates in network world.
