🧾 AuctionSystem – Solidity Smart Contract
A simple Web3 auction system built in Solidity.
It allows an owner to create time-limited auctions and users to place Ether bids. The highest bid wins when the auction ends.

🚀 Features
👑 Only the owner can create auctions

🛑 Auctions have a deadline and automatically close when expired

📈 Bidders must send Ether higher than both the initial and current bid

💸 Automatically refunds the previous highest bidder

🧠 Tracks bid count and current winner

✅ Auctions must have a unique name

🔐 Funds can only be withdrawn by the owner after the auction ends

🛠️ Contract Structure
📦 Structs
solidity
Copiar
Editar
struct Auction {
  string name;
  uint256 initialPrice;
  uint256 currentPrice;
  address payable bidder;
  uint256 deadline;
  uint256 bidCount;
  AuctionStatus status;
}
🔁 Enum
solidity
Copiar
Editar
enum AuctionStatus { Open, Closed, Payed }
🔐 Modifiers
OnlyOwner: restricts access to contract owner

auctionNameAbiable: ensures unique auction names

checkAuctionStatus: auto-closes expired auctions

checkNewBid: checks if msg.value is higher than current and initial bid

notOwner: prevents owner from bidding

onlyAuctionExists: ensures valid auction index

💡 Usage
1. Deploy
Deploy AuctionSystem in Remix using Solidity 0.8.24.

2. Create an auction
solidity
Copiar
Editar
createNewAuction("MacBook", 1 ether, 3600)
3. Bid with ETH
solidity
Copiar
Editar
sendNewBid(0) payable: 1.2 ether
4. Close and withdraw funds
solidity
Copiar
Editar
closeAuction(0)
withdraw(0)
📤 Events
CreateAuction: when a new auction is created

UpdatedAuctionState: when an auction changes status

UpdatedBid: when a new bid is placed

AuctionWithdraw: when owner withdraws the final bid

📚 Extra Functions
getAuctionDetails(uint): returns winner, current price, time left, status

getBidCount(uint): returns number of bids on auction

getTotalAuctions(): returns total number of auctions

🧠 Ideas for Future Improvements
Add support for ERC721 NFTs or metadata

Add auction categories or tags

Allow users to cancel or pause auctions

Add frontend using Ethers.js or Web3.js

