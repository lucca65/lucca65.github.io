---
layout: post
title: Creating UI for your Ethereum Ðapps
published: false
categories: ethereum tutorial web3js solidity blockchain theconf talks
---


The Conf Presentation
Julien: Hi, I'm Julien
Esdras: Hey, I'm Esdras and today we are going to talk a little about how to interact with smart contracts: How it looks like, what our possibilties are, and how can we integrate it with existing technologies

Slide 2
Julien: Our agenda will be the following:
* Introduction 
    * Just simple introduction so you guys get to know us better 
* Recap 
    * Not much to do here since Victor and Bernado already did the heavy lifting for us 
* Basic interaction with smart contracts 
    * The most basic, although not the easiest form of interaction 
* Web based interaction with smart contracts	 
    * Where all the magic will happen 
* Examples 
    * Some examples of Dapps in the wild 
* Questions 
    * And a little time for questions 

Slide 3
Esdras: Those are our emails and github, in case you want to get in touch with us

Slide 3.1
Julien: We've been working together for a while now, we did a Payment Gateway using Elixir, Ruby and native apps...

Slide 3.2 [On beluga]
Julien: In a BigData database called BelugaDB, using NodeJS, ReactJS, C++...

Slide 3.3 [Now at 314]
Julien: and now we are working at a 314coins, a Ethereum exchange using Elixir and NodeJS

Slide 4 [Open Source Communities]
Esdras: We both love open source and we maintain the meetup Elixir User Group SP...

Slide 4.1
Esdras: And also meetup Ethereum SP. Please feel free to join the community, so you can learn more and help us grow. 

Slide 5 [Emoji explanation]
Julien: So, one way for us to see the Blockchain is as a big database, distributed across several nodes. Therefore, decentralized, and all the communcation and trust are done through cryptography.

Slide 6 [Questions and Bitcoin/Ethereum comparison]
Esdras: In Bitcoin, the blockchain has only one use: to compute and keep track of transactions between wallets. But in Ethereum we can do way more, because you can programm it we can run Turing Complete scripts that can act on their own, like reacting to events and send funds as needed.

Julien: How many of you here have some Ether?
Julien: How many of you have participated on THE DAO?
Julien: How many of you already interacted with a smart contract?

Esdras: Well, actually if you participated on THE DAO, you DID interacted with a smart contract.

Slide 7 [Billboard]
Esdras: But let's make it more real. We've created a smart contract that will control a publicity space, very simple, with only one string. It will cost you 10 finney (0.01 ETH) to use it. And you will be able to interact with it in real time.

Slide 8 [Smart Contract]
Julien: The way that we actually program smart contracts is with a programming language called Solidity. Solidity is real simple and it was designed to be very alike to Javascript, so you will probably already be familiar with it. This is a simple snipped of how we set the message: We check if the value sent to the contract is the same as the configured fee, set the message and emit an event

Slide X [Metamask, parity, mist]
We need three things: 
1. the client (mist, parity and metamask) that will download and interact with the blockchain
2. the Address
3. The ABI Interface. It’s a schema like a C/C++ header

Slide 9 [Watching the contract]
Esdras: We've created a smart contract using solidity, and the standard way for someone to interact with it is to watch the contract from your ethereum node client, like parity or mist. we're going to do that right now. For that we're going to need two informations: the address of the smart contract and the ABI interface, which is a kind of "header" if we're going to compare it with C/C++

Slide 10 [Watching the contract]
Julien: With those infos in hand we can finally interact with the smart contract. We will pay 10 finney to change the message that the contract holds. It acts as a simple "SETTER" of a internal value

Slide 11 [Early Web vs Early Blockchain]
Julien: Well this is a painful process. Not only I have to download a platform specific blockchain client that downloads the WHOLE blockchain, but I also have to know those terms: "WATCH", "ABI", etc. That's not very human. It's like when we used to say: "Please check my company web site, it's so cool, type in there: "http://143.88.9.233/index.php". Totally different from something elegant as "theconf.club"

Slide 11 [JSON RPC slide]
Esdras: Thinking of that, Ethereum foundation made a JS library that interacts with the blockchain. It does that through a JSON Remote call procedure -- JSON RPC for short. The blockchain client daemon have a port, and the browser can make requests for it. This way is possible for us to interact with the blockchain.

Slide 12 [thedapp.club]
Julien: The code is pretty simple, and we've made a live demo for you. It's avaliable on thedapp.club (gladly we've found this lovely domain on time). You can access it right now, but you'll need to run the blockchain locally or use Metamask, a chrome plugin that does that for you. 

Slide 13 [Smart Contract slide]
Julien: Well this totally looks like a very simple website, but there's a downside: it takes a while to actually work. But it's so much more. The backend cannot be taken down by any entity, it does not cost us a thing to run it (sorry AWS) and it is autonomous, it gathers money by itself and we can bake any logic that we want. Like kill the contract after a while, send funds when a value is reached, etc etc

Slide 14 [Other Dapps]
There is a lot Dapps already running in the main net (production).Actually we have a directory of over 700 dapps! Several games such as (), Decentralized Exchange. which for me is the most game changer for us right now, as we don’t need people to do that, Services that make our lives better such as ENS a DNS like service so we don’t have to remember hashs

Slide 15/16 [Links/Questions]
Esdras:  Those are some useful links, you can take a picture if you want.

Slide 17
Esdras: Thank you very much, it's been awesome to be here with you

[Questions]

