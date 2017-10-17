---
layout: post
title: Creating UI for your Ethereum Ðapps
published: true
categories: ethereum tutorial web3js solidity blockchain theconf talks
---


On the 2017 [TheConf](http://www.theconf.club) me and [Esdras](https://github.com/esdrasedu) did a presentation about web based interaction with [Ethereum Blockchain](https://www.ethereum.org) using [Web3JS](https://github.com/ethereum/web3.js/)

The result was [The Dapp](http://thedapp.club), which you can access, use and [fork](https://github.com/lucca65/thedapp)

We've basically covered those topics:

- [Blockchain overview](#blockchain-overview)
- [Billboard Example](#billboard)
- [Web3JS Code](#web3js-code)
- [Conclusion](#conclusion)

## Blockchain overview

One way for us to see the Blockchain is as a big database, distributed across several nodes. Therefore, decentralized, and all the communcation and trust are done through cryptography. In Bitcoin, the blockchain has only one use: to compute and keep track of transactions between wallets. But in Ethereum we can do way more, because you can programm it we can run Turing Complete scripts that can act on their own, like reacting to events and send funds as needed.

My first interaction with a smart contract was rather a disastrous one. I've invested in [The DAO](https://daohub.org/) back in 2016, that suffered a serious [attack](https://www.coindesk.com/understanding-dao-hack-journalists/). What if we could create a naive example that wouln't completely create [another coin](https://ethereumclassic.github.io)?

## Billboard

Enter [The Dapp](http://thedapp.club). Its pretty straight foward. It displays a value that is stored inside the contract, thus in the blockchain. That value can be updated, for a fee of [10 finney](http://ethdocs.org/en/latest/ether.html#denominations).

- It checks if you have a blockchain client running such as [Metamask](http://metamask.io)
- Gets a value from the contract
- Displays it
- Also display a Dapp form to update the value


The way that we actually program smart contracts is with a programming language called [Solidity](https://solidity.readthedocs.io). Solidity is real simple and it was designed to be very alike to Javascript, so you will probably already be familiar with it. This is a simple snipped of how we set the message: We check if the value sent to the contract is the same as the configured fee, set the message and emit an event

{% highlight javascript linenos %}
  function setMessage(string _message) public payable {
    require(msg.value == fee);
    message = _message;
    OnUpdateMessage(); // Emit event
  }
{% endhighlight %}

#### So the contract is just a big Getter/Setter

## Web3JS Code

This is the part that the browser runs. It basically look for an avaliable Blockchain node in the default `localhost:8545` address and then interacts with it using a simple JSON remote call. Basically just an API call that we've all being doing for long now.

<script src="https://gist.github.com/lucca65/2d4cef4dd560b286ff9d9b8badfcfd29.js"></script>

<hr/>


First we need to parse the [ABI](https://github.com/ethereum/wiki/wiki/Ethereum-Contract-ABI) which is basically a header for our Solidity code. We need that because the blockchain stores the smart contracts as binary in the blockchain, so we need a way to know what we can do with that contract without resorting to techniques such as [reflection](http://www.wikiwand.com/en/Reflection_%28computer_programming%29).

With that in place we can create an object that represents in JS our Solidity contract.

From there it's pretty straight foward function calling.

## Conclusion

If you are interesed in buying Ethereum easily using Reais (BRL), checkout our tool [314coins](https://314coins.com)! It's still on beta but make sure to take a moment on it. Any feedbacks can be sent [here](mailto:contato@314coins.com)

-----------
