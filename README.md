# A Web3 for eSport & Entertainment Industry 
A digital assets wallet management development for eSport and Entertainment Industry.

## Description of Request

A closed loop wallet system, which has the capacity to hold multi-currencies  as well as to receive funds from other source such as bank. 

The wallet will be segregated by the Phone number of the customer. Customers phone number is the account ID of their wallet. 

One master wallet (Counter) will be used to collect revenue from all the wallets. 

The wallet has to be secure and protected from hacking.

Capability to connect to a spot crypto exchange and the PSP at a later stage. 

# Proposition

We propose the wallet holds three different types of currencies/tokens; 

1. KHR pegged which is 1:1 exchange rate to U.S dollar. The customers could buy for their wallet by depositing KHR from their bank account to the wallet via payment service provider to the **Counter** 

2. USD pegged which is also 1:1 exchange rate to USD. Customer acquire this token same as above.

3. Game Token which will have the exchange rate in the future, the more people using and holding it. It could be a speculative investment with some utility. 

Thus, there will not be any exchange rate for the first two, as the transfer is in the same currency from the customer’s bank account to the customers wallet. 

Example: 
```mermaid
flowchart LR
    A[Users] -->|Send| B(USD)
    F --> A
    B -->|from Bank Account| C{Counter}
    D --> F(Wallet)
    C -->|Send| D(USD pegged)
```

## Game Token Utility

- As Discount and VIP privilege: Users or customers who hold X amount of the Game Token, will be charged less in transaction fees within the game. 

- As APY return: Users who hold the Game Token could also stake it to the game and earn APY in Game Token. 

- As Investment Asset: Users could cash out to other currencies or crypto at open exchange. 

## KHR and USD pegged utility

Wallet users could utilized these pegged currency to bet in the game, pay each others, receive rewards, or cash out to their bank accounts outside of the wallet.  

## Benefits for Game Operators

For Game Operator, the wallet allow them to hold customers' money within their phone, while the custom cash has already deposited to the Game Operator's bank account.

The cash only return back to the customers when they need to cash out. Though, since the wallet will have the capacity to transfer among themselves and make payment outside, the customer will less likely to take the cash out, but use it for game or buy things at the Operators' partnership stores. 

## Benefits for users
Since the Game operators save money from bank fees, the users/customers could be rewarded via discount program and many more others variety.

## Technology

A Blockchain will be to mint and burn the tokens in the wallet. The Mint function is will take place, when customers transfer CASH from their bank account to buy the currency into the wallet. Burn function is will take place, when they transfer tokens back to their bank account.

Smart contract will be used to automate these functions and many others tasks that will reduce the cost of people time managing the process. At the same time, save cost from running centralized data center or servers to store those data, since the transactions are done over the Blokchain. 

The wallet has to be secure and protected from hacking than a centralized database on data center or centralized cloud because it is used Smart Contract.

The tokens is a blockchain token standard, which ERC-20 token, thus it has the capability to connect to a spot crypto exchange and the PSP, that will open to support it. 

## Game Gallery Example

A game gallery to will aggregate the all the game into one portal landing page. Similar to the image below; 

![](https://www.pokcas.com/wp-content/uploads/2021/04/Casiplay-Casino-New-Games-1280x720-1-1024x576.jpg)

## Registration Process

```mermaid
sequenceDiagram
    autonumber
    actor A as User
    participant B as Wallet App
    participant C as Smart Contract

    A ->> A: User download, install, and open the Wallet mobile app
    A ->> B: User input their phone number to register in the app
    B ->> C: Wallet registers user's phone in the contract
    C ->> C: Contract bind user's phone number to wallet address
```

## Payment Process

```mermaid
sequenceDiagram
    autonumber

    actor A as User
    participant B as Wallet App
    actor C as Counter
    participant D as Games

    rect rgba(255, 255, 255, 0.2)
    Note over A,C: Top-up process
    #A ->> B: User send $CASH via their phone number, registered above
    A ->> C: User transfer $CASH  to the counter with the registered phone number as remark to top-up the wallet
    C ->> B: Counter transfers tokens to the user's wallet
    end
    rect rgba(255, 255, 255, 0.2)
        Note over B,D: Gaming process
        B ->> D: User use the token in the wallet to bet in the game
        alt LOST
            D ->> C: If user lost, the game transfers bets to counter
        else WON
            D ->> B: If the user won, the game transfers reward to
        end
    end

    rect rgba(255, 255, 255, 0.2)
    Note over A,C: Cash-out process
    B ->> C: User send token from the wallet the counter
    C ->> A: Counter transfers to money to the user
    end

```

## Gaming Process

```mermaid
sequenceDiagram
    autonumber
    actor A as Counter
    actor B as Player
    actor C as Escrow Contract
    participant D as Game

    B ->>+ C: Select game
    C -->>- B: Reqeust bet
    B ->> C: Deposit bet
    C ->>+ D: Start game session for player

    D -->>- C: On game end report result
    alt win
        C ->> B: Transfer reward to player
    else lost
        C ->> A: Transfer bet to counter
    end
```

## Gallery Interaction

```mermaid
sequenceDiagram
    autonumber
    actor A as Player
    participant B as Gallery
    participant C as Contract
    participant D as Game

    A ->> B: Connect wallet
    A ->> B: Choose game
    B -->> A: Request bet deposit
    A -->> B: Deposit bet
    B -->> C: Regiseter user in bet pool
    C -->> D: Start game for user
    D -->> C: Report game result
    alt WON
        C ->> A: Transfer reward
    end
```

# Question to Clarify

- Is the existing game system already in place?

- If so, we do need access to the games in order to understand how integrate the wallets and estimate the time it will take to do it?

- How many tokens/currencies do you need to develop? Please help clarify its nature, for example; stable value 1:1 USD.

# Cost

The cost will calculated after the clarify question has been answered.  