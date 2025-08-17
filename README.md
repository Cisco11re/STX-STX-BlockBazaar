
# STX-BlockBazaar - Decentralized Digital Marketplace Smart Contract on Stacks blockchain

A trustless, decentralized marketplace for digital goods, built with Clarity for the Stacks blockchain. This smart contract enables users to list, buy, and sell digital assets with built-in **escrow**, **dispute resolution**, and a **reputation system** — ensuring security, fairness, and transparency without a central authority.

---

## 📌 Features

* ✅ **Trustless Listings & Purchases**
  Anyone can list digital goods, and others can purchase using on-chain logic.

* 🔒 **Escrow System**
  Funds are held in escrow until the buyer confirms receipt of the digital good.

* ⚖️ **Dispute Resolution**
  Arbitrators can resolve disputes fairly in case of delivery issues or fraud.

* ⭐ **Reputation & Rating System**
  Users build a public reputation through verified transactions.

* 🧠 **Marketplace Admin Settings**
  Admin can configure marketplace fees and designate arbitrators.

---

## 🧱 Contract Structure

### Constants

* **Error Constants**: Predefined error codes for contract failures.
* **Status Constants**: Enumerations for listing, purchase, and dispute statuses.

### Data Variables

* `listing-counter`, `purchase-counter`, `dispute-counter` — Auto-incremented identifiers.
* `marketplace-admin` — Deployer/admin of the marketplace.
* `marketplace-fee-percentage` — Fee charged on each transaction (default 2.5%).
* `confirmation-period`, `dispute-period` — Time windows in seconds for confirmation and dispute raising.

### Data Maps

* `listings` — Stores active and expired listings.
* `purchases` — Stores purchase information and current status.
* `escrow-funds` — Keeps track of funds held in escrow.
* `disputes` — Tracks disputes between buyers and sellers.
* `user-ratings` — Ratings data for marketplace participants.
* `arbitrators` — List of verified arbitrators who can resolve disputes.

---

## 🔍 Read-Only Functions

| Function Name           | Description                                       |
| ----------------------- | ------------------------------------------------- |
| `get-listing`           | Fetches a listing by ID                           |
| `get-purchase`          | Fetches a purchase by ID                          |
| `get-dispute`           | Fetches a dispute by ID                           |
| `get-escrow-amount`     | Retrieves funds held in escrow for a purchase     |
| `get-marketplace-stats` | Returns marketplace-wide counters and fee setting |
| `get-user-rating`       | Returns rating stats for a given user             |

---

## 🛠️ Helper Functions (Private)

| Function Name               | Description                                  |
| --------------------------- | -------------------------------------------- |
| `get-next-listing-id`       | Auto-increments and returns next listing ID  |
| `get-next-purchase-id`      | Auto-increments and returns next purchase ID |
| `get-next-dispute-id`       | Auto-increments and returns next dispute ID  |
| `calculate-marketplace-fee` | Calculates fee from given amount             |
| `calculate-seller-amount`   | Computes seller’s payout after fees          |

---

## 🧪 Future Development Areas

* [ ] Write functions for creating listings, making purchases, and confirming delivery.
* [ ] Implement full arbitrator workflow.
* [ ] Allow marketplace admin to approve or remove arbitrators.
* [ ] Rating system updates after transactions complete.
* [ ] Time-based actions like auto-confirmation after `confirmation-period`.

---

## ⚙️ Deployment

1. **Prerequisites**:

   * Stacks blockchain environment
   * Clarity smart contract tooling

2. **Deployment Steps**:

   * Set `marketplace-admin` to the deploying address
   * Configure `marketplace-fee-percentage` if needed

---

## 📝 License

This smart contract is released under the **MIT License**. Feel free to use and modify it for your own decentralized commerce needs.

---
