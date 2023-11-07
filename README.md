# F23_Blockchain_Bazaar
Blockchain Bazaar is an AI controlled video game item shop. Currently, video game economies typically fall into two categories: player shops and non-player character (NPC) shops. 

In player shops, item prices, quantities, and value are dynamic and change based on free market forces. However, player shops can be plagued by dishonesty and price gouging. In NPC shops, prices are static and non-interactive. Apart from a lack of immersion , the flaw here is that the value of an item is irrelevant if the shops can provide an unlimited supply of it and inevitably cause the inflation of in-game currency.

Blockchain Bazaar aims to take the best of both systems by using blockchain to secure trades and maintain unique items while AI is used to alter prices based on user transactions.

## Team Members
Lorenzo Mercado (mercal)  
Justin Chang (changj11)  
Konain Qureshi (quresk)

## Overview and Diagrams

### Architecture
An architecture diagram showing the components of our system. Metamask is the player's wallet which will be connected to our user interface (transaction API). Prices will be stored on the user interface and AI will be update those prices based on feedback from successful smart contract transactions which will be relayed back to the user interface.

![High-level Diagram for Architecture/Component](./assets/Architecture%20Diagram.png)

### Sequence Diagram
Below is a diagram showing the buy item process.

![High-level Diagram for Architecture/Component](./assets/Sequence%20Diagram.png)

### AI Overview
The AI is going to be used to alter prices for both buying and selling of items within shops based on user transactions
- Utilizing contextual bandits or associative reinforcement learning
    - implemented from a github repository of multiple such algorithms
    - https://github.com/david-cortes/contextualbandits
    - also included is a paper going over each algorithm
    - https://arxiv.org/abs/1811.04383
    - RL suited to dense reward training
    - online model can be constantly trained with each new transaction
    - Implement mainly with numpy and sklearn
- Optimize value generated by balancing sales and purchases through price manipulation
- Update pricing to the UI which can be queried by the oracle

### Blockchain Overview
A permissionless blockchain to keep single line of truth for transactions as well as unique items in shops. Facilitated through Smart Contracts.
- Permissionless since any player should be able to participate in the market
- Eliminate fraudulent transactions and manipulation of past transactions
- Keep track of unique items and provide a more transparent depiction of the value of the item
- Automate transactions when conditions are met using Smart Contracts

Metamask will be utilized as our player’s wallets and SepoliaETH as the currency.

