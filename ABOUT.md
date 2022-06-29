# Exotic Gaming

The exotic protocol is a decentralised gaming application.

## Introduction

We are releasing an early beta of our gaming protocol while iterating towards a general access release. We aim to offer fairer odds than any bookmaking available by using **real** protocol owned liquidity (POL) as counterparty to users bets. We will grow the POL organically by generating real revenue from genuine use cases. Using this POL will enable us to implement new game/event inputs and wagering engines.

This initial release is an alpha release and our contracts **aren't verified**, we do plan to do this after a security audit by a reputable organisation. The only user funds at risk are non determined bets, however this risk is tempered by having maximum bet limits set quite low. There are workarounds of course but please use your own judgement when playing (funds may be with sifu).

## Protocol Overview

The architecture of the system is quite simple. One central contract is the "house" (and holds the POL), games (contracts) can be enabled (with risk limits) to both contribute to and draw from the POL. Doing this helps both seperate our concerns with logic and enable us to introduce new gaming experiences while having the usage of the POL.

The games contain the actual logic of the wagering engine and the interface for users to bet on. This decoupling could allow independently developed games make use of the POL in their own game with acceptance of the game being decided by governance vote. Our initial relase uses an parimutuel wagering engine system.

Our current release target includes:
* A single intentionally simple game contributing to POL
* Using POL as a "jackpot" feature in game

### POL

The POL allows games to be registered with it and to use its POL in their own engines. The POL contract is still being developed and eventually ownership of the contract will be fully controlled by token holders. Initially we do envision needing updates to the POL contract to develop a flexible interface that can provide support for a large variety of games.

## POL contribution

An adjustable fee (currently set to 0.5%) of each wager amount is contributed to building protocol owned liquidity. This is calculated by taking the fee amount of the total msg.value sent to the game while betting. This fee along with all others will eventually be delegated to gauges voted on by protocol token owners.

## Revenue Fee

There is also a fee (currently set to 0.5%) that is charged for usage of the protocol.

## XTC token

The XTC token is a fair launch token that is used during the bootstrap phase to incentivise users to place bets. This token will be used in the future to govern the protocol parameters and also enables users to take part in revenue sharing.

The token distribution as part of games does not follow a pre-defined emission schedule. The protocol team reserves the right to use emissions as we deem the most effective way to grow the protocol. There are no token sale events planned and their are no third party investors in our project.

## Revenue distribution

Holders of the XTC token who stake in the RevenueStaking contract earn a proportion (based on the weight of their XTC vs sum of all stakers) of all revenue fees. Fees accrue in real time and are always claimable.

## Initial game.

The initial game we release is dog track simulator. It uses a parimutuel wagering system and a fixed probability random outcome. The odds from the wagering engine should track the fixed probability as if not arbitrage could exist between real vs virtual odds. The betting pools will ultimatly accomadate many advanced bet types (each way/exacta etc) but initially is released with a single choose winner bet.
