# tincubed

incubed with tor (onion services) support (hackathon project)
Tincubed is building on the awesome [INCUBED (IN3) project](https://download.slock.it/whitepaper_incubed_draft.pdf)

## Why?

Ethereum (and most other blockchains) have a privacy problem. This needs to be attacked on multiple fronts. One of them was described by [Péter Szilágyi at Devcon4](https://www.youtube.com/watch?v=J1JenTo7oLE) If you are not aware of the full extend of the problem (e.g. you think mixers would solve the problem completely) Please watch this talk before reading on.

## What?

This project intends to build one building block towards a solution. It wants to do this by combinding onion services with incubed. You basically get minimal verification services with an extra option for anonymity.

## How?

With incubed you register one URL at a smart contract by calling this function:

```solidity
function registerServer(string _url, uint _props) public payable;
```

just instead of calling it with a normal URL - you would register it with an URL pointing to an onion service. BehinThrereThrered this onion service is than a normal incubed node. Basically it is just wrapped in the onion service.

Then we need to modify the client so it can filter for these onion adresses and connect to them. And e.g. the wallets should have an opt-in or opt-out for it (like a checkbox [ ] I need anonymity for my MetaData). It might not be on by default as it is a trade-off between speed and cost vs anonymity.
 
## There is more

As a drive by kill I think it also helps the resillience of the system. For big actors (like states) it is actually not that hard to attack a service like infura as it is well known and e.g. make a lot of Etherum dApps unusable this way. But it is quite hard to take down onion services as Silk Road nicely showed. Just instead of sending interesting physical packets - in this case we use it to transport interesting digital packets only.

