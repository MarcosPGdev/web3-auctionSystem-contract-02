# 🛒 Web3-auction-system-02 – Auction Smart Contract in Solidity

This project is a smart contract written in Solidity that enables the creation and management of a basic auction system using Ether. It was developed as a learning exercise and is part of a broader Web3 development journey.

---

## 🚀 Key Features

* 👑 Only the contract **owner** can create new auctions.
* ⏳ Auctions have a **deadline** and close automatically when the time expires.
* 💸 Users can place **bids with Ether**. Only higher bids are accepted.
* 🔁 **Previous bidders are refunded** automatically.
* 📈 Tracks number of bids and current highest bidder.
* 🔐 Funds can be withdrawn **only after** the auction is closed.
* ❌ **Auction names must be unique**.

---

## 🧠 Auction Structure

Each auction includes:

* `name`: unique name of the auction
* `initialPrice`: minimum required to start bidding
* `currentPrice`: highest bid received
* `bidder`: address of the current highest bidder
* `deadline`: timestamp indicating auction end
* `bidCount`: number of total bids
* `status`: Open / Closed / Payed

---

## ⚙️ How to Deploy and Test (Remix)

1. Open **Remix IDE**
2. Paste the contents of `AuctionSystem.sol`
3. Compile the contract using **Solidity 0.8.24**
4. Deploy the contract from your account (will be the owner)
5. Interact with the contract via the functions listed below

---

## 🔘 Available Functions

| Function                                  | Description                                                |
| ----------------------------------------- | ---------------------------------------------------------- |
| `createNewAuction(name, price, duration)` | Creates a new auction (owner only)                         |
| `sendNewBid(index)`                       | Sends a new bid with `msg.value` (higher than current)     |
| `closeAuction(index)`                     | Closes an auction manually (owner only)                    |
| `withdraw(index)`                         | Transfers final bid to owner after auction ends            |
| `getAuctionDetails(index)`                | Returns the current winner, bid, time remaining and status |
| `getTotalAuctions()`                      | Returns number of created auctions                         |
| `getBidCount(index)`                      | Returns number of bids on a specific auction               |

---

## 🔐 Security and Validations

* `OnlyOwner`: only the contract owner can create or close auctions
* `checkAuctionStatus`: automatically closes expired auctions before allowing new bids
* `checkNewBid`: ensures bid is higher than both the initial and current price
* `notOwner`: owner cannot bid on their own auctions
* `auctionNameAbiable`: prevents duplicate auction names
* `onlyAuctionExists`: avoids access to non-existent auctions

---

## 📦 Events

* `CreateAuction(name, initialPrice)`
* `UpdatedAuctionState(name, status, index)`
* `UpdatedBid(index, value, bidder)`
* `AuctionWithdraw(index, amount, owner)`

---

## 🧱 Technologies

* **Solidity 0.8.24**
* **Remix IDE** for testing and deployment
* **Ether** (via `msg.value`) for real bidding and transfers

---

## ✍️ Author

Developed by **Marcos Pérez** as part of his Web3 development training.
This smart contract is one of the first entries in his **Web3 Developer Portfolio**.

---

## 📜 License

This project is licensed under the **MIT License**.

---

¿Te gustaría que te lo formatee directamente como archivo `README.md`?
