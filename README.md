# Web3 Game 
A digital assets wallet management development for eSport and Entertainment Industry.

## Description of Request

A closed loop wallet system, which has the capacity to hold multi-currencies  as well as to receive funds from other source such as bank. 

The wallet will have to be numbered or segregated by the Phone number of the customer. Customers phone number is the account number in the wallet. 

After the wallet is segregated by individual wallet for customers one wallet will be for segregating the revenue

The wallet has to be secure and protected from hacking etc.

Capability to connect to a spot crypto exchange and the PSP at a later stage

Example: 
```mermaid
flowchart LR
    A[Users] -->|Send| B(USD)
    F --> A
    B -->|from Bank Account| C{Counter}
    D --> F(Wallet)
    C -->|Send| D(USD pegged)
```


# Proposition

We propose that the wallet holds three different types of currencies/tokens; 

1. KHR pegged which is 1:1 exchange rate to U.S dollar. The customers could buy for their wallet by depositing KHR from their bank account to the wallet via payment service provider to the **Counter** 

2. USD pegged which is also 1:1 exchange rate to USD. Customer acquire this token same as above.

3. Game Token which will have the exchange rate in the future, the more people using and holding it. It could be a speculative investment with some utility. 

Thus, there will not be any exchange rate for the first two, as the transfer is in the same currency from the customer’s bank account to the customers wallet. 


## Game Token Utility

- As Discount and VIP privilege: Users or customers who hold X amount of the Game Token, will be charged less in transaction fees within the game. 

- As APY return: Users who hold the Game Token could also stake it to the game and earn APY in Game Token. 

- As Investment Asset: Users could cash out to other currencies or crypto at open exchange. 

## KHR and USD pegged utility

Wallet users could utilized these pegged currency to bet in the game, pay each others, receive rewards, or cash out to their bank accounts outside of the wallet.  

## Benefits for Game Operators

For Game Operator, the wallet allow them to hold customers' money within their phone, while the custom cash has already deposited to the Game Operator's bank account.

The cash only return back to the customers when they need to cash out. Though, since the wallet will have the capacity to transfer among themselves and make payment outside, the customer will less likely to take the cash out, but use it for game or buy things at the Operators' partnership stores. 

## Benefits for Users


## Technology

We will use blockchain to mint and burn the tokens needed. Mint is taken place, when customers transfer cash from their bank account to buy currency for wallet. Burn is taken place, when they transfer token back to their bank account.

We will use smart contract to automate these tasks and some others 


## Game Gallery Example

![](https://www.pokcas.com/wp-content/uploads/2021/04/Casiplay-Casino-New-Games-1280x720-1-1024x576.jpg)

## Payment Process

```mermaid
sequenceDiagram
    autonumber

    actor A as User
    participant B as Wallet
    actor C as Cashier
    participant D as Games

    rect rgba(255, 255, 255, 0.2)
    Note over A,C: Top-up process
    A ->> B: User send $CASH via their phone number, registered above
    A ->> C: User transfer money to cashier to top-up the wallet
    C ->> B: Cashier transfers tokens to the user's wallet
    end
    rect rgba(255, 255, 255, 0.2)
        Note over B,D: Gaming process
        B ->> D: User use the token in the wallet to bet in the game
        alt LOST
            D ->> C: If user lost, the game transfers bets to cashier
        else WON
            D ->> B: If the user won, the game transfers reward to
        end
    end

    rect rgba(255, 255, 255, 0.2)
    Note over A,C: Cash-out process
    B ->> C: User send token from the wallet the cashier
    C ->> A: Cashier transfers to money to the user
    end

```

## Gaming Process

```mermaid
sequenceDiagram
    autonumber
    actor A as Cashier
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
        C ->> A: Transfer bet to cashier
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


