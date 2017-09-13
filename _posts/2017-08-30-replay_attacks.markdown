---
layout: post
title:  "Understaning Replay Attacks"
date:   2017-08-30 14:34:25
categories: blockchain segwit
tags: featured
image: /assets/article_images/2014-11-30-mediator_features/night-track.JPG
image2: /assets/article_images/2014-11-30-mediator_features/night-track-mobile.JPG
---

>Segwit2x has garnered some controversy over the fact that it will not have replay protection. In this article, I’m going to explain what a replay attack is and how it will affect the upcoming 2x hard fork.

#Bitcoin Transactions
In order to understand what a replay attack is, we first have to understand how a bitcoin transactions works.
Bitcoin can be thought of as a global ledger and Bitcoin transactions as bank checks. Because a global ledger is digital, anyone who wants to can audit that ledger by downloading an entire copy of the blockchain.
This also means that the actual checks are public. That is, anyone can look at an individual transaction and verify that the digital signature is valid.

#Hard Fork
A hard fork is essentially an upgrade to the global ledger. If everyone upgrades, there remains only one global ledger. If not everyone upgrades, instead of one global ledger, there are two: the legacy ledger and the forked ledger.
Up until the fork, the ledgers are exactly the same. That is, they share the exact same transaction history. But after the fork, as new blocks are found, the ledgers have different transactions and thus, balances.
This happened, for example in the Bitcoin Cash Hard Fork on August 1, 2017.

#Replay Attacks
If you own some amount on the ledger before the split, you will have the same amount on both ledgers after the split. What if you want to spend money on one ledger and not on the other?
This presents a problem because if you spend on one ledger, somebody can copy the same check, which has your signature, and present it for inclusion on the other ledger. That is, they can spend your money on the other ledger because your signature is valid on both ledgers. Of course, who you’re sending the money to and the actual amount has to be exactly the same, (or the signature would be invalid) but this still presents a problem.
The person who presents the copy of the check on the other ledger is replaying the transaction. This is a problem since you wanted to send on only one ledger. We call this a replay attack.
Bitcoin Cash solved this problem by changing the check ever so slightly. They created a special mark on the check that identified the check was for the BCH ledger and not the other ledger.
Thus, any node now auditing Bitcoin will automatically reject a Bitcoin Cash check since the check has that special mark. Anyone auditing Bitcoin Cash will reject a Bitcoin check since the check is missing the special mark.
This special mark is called replay protection since it prevents replay attacks.


#Replay Protection and Segwit2x
The developers behind Segwit2x are refusing to add replay protection. Instead, they are saying Bitcoin Core should add replay protection if it’s a concern.
Unfortunately, most replay protection schemes are hard forks. Because hard forks are not backwards compatible and not everyone will upgrade, this will cause two different ledgers. Many Bitcoin Core developers have held the view that a hard fork that’s not planned 12+ months in advance would cause this scenario.
So, if Bitcoin Core added replay protection in the short time span for the Segwit2x hard fork (3 months), this would most likely create three different ledgers: Segwit2x, Bitcoin with Replay and Bitcoin Legacy. And that is not even counting Bitcoin Cash.
This refusal by Bitcoin Core is consistent with the refusal to hard fork to Segwit2x. If Bitcoin Core developers were comfortable with a hard fork in the 3-month timeline, making a hard fork similar to Segwit2x would have made more sense. Instead, since many Bitcoin Core developers feel that 3 months is too short to prepare for a hard fork, replay protection on Bitcoin Core is a non-starter.

#Closing Thoughts
For those who that don’t transact much, replay will likely not be much of a problem. After the 2x hard fork, this will mean that users won’t, and probably shouldn’t, transact for a while until there’s a clear and accessible replay solution.
Though this may seem scary, but given the experiences with Bitcoin Cash, this may not be so terrible after all.