# StacksConnect - Decentralized Social Network Protocol

StacksConnect is a **privacy-first decentralized social networking protocol** built on **Stacks Layer 2**, bringing secure, encrypted, and rate-limited peer-to-peer interaction to Bitcoin-backed applications. It offers smart contract-based enforcement of user permissions, rate limits, batch processing, and activity tracking—all while preserving Bitcoin’s security guarantees.

## 🌐 Overview

StacksConnect enables users to:

* Create and update secure profiles
* Manage friendship and block relationships
* Control privacy on a granular level
* Post status updates within rate limits
* Participate in batch-optimized communication flows
* Maintain compliance with decentralized governance norms

## ⚙️ Features

* ✅ **Privacy-First Design**: End-to-end control over visibility of friend lists, status updates, metadata, and profile images
* 🔐 **Encryption Capabilities**: Optional encryption key storage and management for privacy-enhanced messaging
* 📈 **Rate Limiting**: Platform-wide enforcement of interaction quotas per user per day
* 🌀 **Batch Processing**: Automatic and manual batch size adjustment for throughput optimization
* 🔁 **Bidirectional Friendships**: Smart contract-enforced relationship state with pending, active, and blocked statuses
* 🛡️ **Activity Logging**: Transparent analytics with privacy-preserving design
* ⚖️ **Security & Compliance**: Built on Stacks, inheriting Bitcoin’s finality, making it suitable for mission-critical decentralized social interaction

## 🏛 Smart Contract Architecture

### Core Components

```text
+----------------------+
|      Users           |
|----------------------|
| name, status, etc.   |
+----------------------+
           |
           v
+----------------------+
|     UserPrivacy      |
|----------------------|
| Visibility toggles   |
| & encryption flags   |
+----------------------+

+----------------------+      +----------------------+
|     RateLimits       |<---->|   update/check rate  |
+----------------------+      +----------------------+

+----------------------+      +----------------------+
|     Friendships      |<---->|    Bidirectional     |
|    status, pending   |      |  friendship control  |
+----------------------+      +----------------------+

+----------------------+      +----------------------+
|    BlockedUsers      |<---->|  Safety & blocking   |
+----------------------+      +----------------------+

+----------------------+      +----------------------+
|    UserBatches       |<---->|   Batch processing   |
|   size, timestamps   |      +----------------------+

+----------------------+
|   UserActivity       |
|  login, seen, etc.   |
+----------------------+
```

## 📦 Contract Structure

* **Constants**: Well-defined error codes, statuses, rate limits, and batch sizes
* **Maps**:

  * `Users`: Core profile information
  * `UserPrivacy`: Privacy configuration
  * `RateLimits`: Daily rate tracking
  * `UserBatches`: Batch message handling
  * `UserActivity`: Tracking logins and actions
  * `Friendships`: Friend state management
  * `BlockedUsers`: Block enforcement
* **Private Functions**:

  * Rate limit checking, incrementing
  * Activity logging
  * Friendship and user status validation
  * Privacy fallback logic
* **Public Functions**:

  * `update-user-profile`: Optional field-based profile update
  * `update-advanced-privacy-settings`: Full privacy toggle API
  * `record-login`: Login tracking
  * `optimize-batch-size`: Algorithmic batch tuning
  * `set-batch-size`: Manual override for batch config

## 🔐 Security Considerations

* Enforced **rate limits** prevent abuse
* **Deactivation status** halts all user actions
* Bidirectional block & friend relationship checks ensure integrity
* **Internal utilities** help avoid unbounded or unchecked actions

## 📜 Usage Example

```clarity
;; Update a user’s privacy preferences
(update-advanced-privacy-settings true false true true false true)

;; Set a manual batch size
(set-batch-size u50)

;; Log in user and track activity
(record-login)

;; Optimize batch size based on usage
(optimize-batch-size tx-sender)
```

## 📄 Deployment Requirements

* **Stacks Blockchain** (Testnet or Mainnet)
* **Clarity** Smart Contract Environment
* Compatible **Stacks Wallet** for interaction

## Contributing

Contributions, feature requests, and security audits are welcome! Please open an issue or submit a pull request for consideration.
