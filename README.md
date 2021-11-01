# ZILNFTIndexMarketplace
## Introduction 
As NFTs are on-chain assets, it is possible to develop a smart contract that wraps multiple NFTs and mint tokens representing the value of NFTs it owns. This would allow collectives of buyers to invest in NFTs that they might not be able to afford individually while ensuring that they maintain ownership of the NFT. [ZILLIQA ON GITCOIN: NFTs BEYOND ART - Decentralised Index Fund For NFTs](https://gitcoin.co/issue/zilliqa/zilliqa/2716/100026478)

## Concepts
![alt text](https://github.com/vintageplayer/ZILNFTIndexMarketplace/blob/master/DecentralizedNFTFund.drawio(1).png?raw=true)

### Entities
* **Fund Manager**: A trusted person or DAO having NFT purchase/selling decision power.
* **Fund MarketPlace**: Dapp for creating, managing and participating in an NFT Index Fund.
* **Investor**: A entity interested in collectively investing in NFTs.

### Marketplace Contract
  Marketplace Contract is reponsbile for generating tokens and accepting fees from each fund and managing tokenomics of the entire DApp.
### Fund Contact
  Contract managing an indivdual Index Fund of NFT, keeping track of investors, the ZIL pooled, NFT assets owned and controls change in any of these.

### Scenarios
* Creation of Marketplace: A marketplace Dapp is created, with an initial supply of marketplace tokens. Fee is collected from fund specific operations and is used to drive the token value.
* Creation of Fund: A fund manager or DAO can create their fund on demand, setting an inital token price to pool money from interested investors.
* Investor Onboarding: An investor joins one of the funds available by putting Zil and receiving tokens of the specific fund in return.
* Procurement of NFT: Fund Manager decides to transfer Zil from the fund contract to an NFT owner and transfers the ownership to the fund contract.
* Sale of NFT: Fund Manager sells an NFT owned by the fund and add Zil to the fund contract.
* Investor Exit through Primary Market: Investor returns the token back to the fund and takes Zil out according to the current set price.
* Investor Exit through Secondary Market: Without hampering a funds performance, investors can sell their fund token on secondary market to other interested investors.

### Fee
Fee in current plan, will be taken in two different places
* Fee for Purchasing fund token 
A small fee (like 0.1%) of the Zil exchanges for the Fund Tokens will be taken as fee for the marketplace
* Fee for Selling an NFT

### Fee for Fund Managers
During creation of a specific fund contract, fund manager/owner sets the percentage of profit for each NFT sold back as their earning. Currently during a loss, no fee is paid to the fund manager, neither is any penalty mechanism in place currently.

### Tokenomics
#### Minting Tokens
At the time of marketplace contract creation, a set number of token supply for DApp management & promotion is generated.

#### Token Distribution
A pre-determined percentage of initially minted tokens is allocated for incentivising purchase of NFT behaviour.
Based on the bonding curve explained below, every purchase of NFT grants the investors of the funds a newly accessible tokens in their respective investment size proportions.
#### Bonding Curve
Considering NFT can be high value assets which are not frequently sold and could be held for longer periods of time, we use cumulative prices of NFT purchases done through the marketplace to incentivise early adopters. The formula for determing new tokens to be granted to a fund on purchasing NFT is: P<sub>b</sub>/(P<sub>c</sub> + k)
Here:
* P<sub>b</sub>: Price for the current purchase of NFT
* P<sub>c</sub>: Sum of prices for all NFTs purchased till date (including P<sub>b</sub>)
* k: Damping Factor. To ensure a smooth gradual drop in token reward over time.

This ensures early adopters getter rewarded more tokens.

#### Summarization for User Journey
1. Investors, looking forward to getting marketplace tokens on purchasing of an NFT, will add Zil to a fund, thus paying a fee to marketplace.
2. The procurement grants them access to new marketplace Dapp tokens which they can sell in secondary market.
3. At some point in the future, NFT is sold back at a desired price, giving fees to the marketplace Dapp.
4. At this stage, user is again incentivized to put money in an NFT to acquire more Dapp tokens rather than pulling profits out.

A user looking to rapidly sell high-value NFTs for acquiring marketplace Dapp tokens will not be able to do so due to market place fee on sell and only a fraction of it going back to the tokens. Thus making profitable NFT trades is still the primary incentive for an investor or fund manager.


#### Value Distribution
A fraction of profits generated in Marketplace Contract will be distributed to token owners by purchasing tokens from exchanges in secondary market at the market rate periodically.


## Transitions
### Fund Contract
1. Add Funds
2. Remove Funds
3. Buy NFT
4. Sell NFT
5. Toggle Can Sell Token
6. Set Token Price


## Things to be done
1. Combine the two smart contracts for MarketPlace and Fund creation.
2. Create a UI for creating funds
3. Update contracts with fee attribution and token distribution

## Future Road Map
1. Create a dao road map
2. Performance Analystics on fund managers
3. Connecting with Marketplaces
4. Give Options of public/private funds

## Contact
EmailID: adityag2511@gmail.com
