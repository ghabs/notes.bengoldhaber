---
layout: post
title: Uniswap Simulation
---
__Originally posted on the [HASH blog](http://hash.ai/blog/uniswap)__

*This is the first in a series of cryptocurrency simulations. [View the simulation.](https://core.hash.ai/@b/uniswap/main)*

![](https://lh4.googleusercontent.com/U7QSu8j7drSrXCuFf_zTgFu_FoyWKDpguJZawWRY1mssQizd6XGDy2O66ARk_0o-B1nHC0C5wm60T1caH7O66x60UQip6Bh158AxmGWmYZoYVJDtgThQnOatOCo2mb2DdeBlbef6)
https://uniswap.org/docs/v2/protocol-overview/how-uniswap-works/

One of simulation’s great benefits is that it can help us explore complex systems and discover unexpected outcomes. There are few domains that exhibit quite as much complexity as cryptocurrencies, and the surprising and unexpected seem to occur on a constant, regular basis.

The rise of decentralized finance has dramatically increased the options available to investors and traders, and understanding key elements of it through modeling and simulation can help reduce uncertainty. It’s also just a really interesting space – [for example](https://rope.lol/) – which means a lot of fun can be had building simulations. Over the next few weeks we’ll be publishing models and explainers covering a few different projects in the crypto-world. By following along, you’ll be able to fork these models, expand them, and experiment with alternative crypto mechanics.

Uniswap is a fully decentralized protocol for automated liquidity provisioning on Ethereum. [Building on a Reddit post](https://www.reddit.com/r/ethereum/comments/55m04x/lets_run_onchain_decentralized_exchanges_the_way/) by Ethereum co-founder Vitalik Buterin, Uniswap is part of a class of automated market makers that use a defined algorithm to set prices for buying and selling tokens. Users can swap token A for Token B at a rate set by the constant product formula x*y = k, where x is the reserve of tokens A, y is the reserves of token B, and K is a constant. As more of token A is purchased, and thus more of token B is deposited, the price of A in terms of B will rise.

![](https://lh4.googleusercontent.com/rUx2e3tvf1eWnx-1p1CvDrPit-Kspcj9yBZIuAKq4rKgbvTNX6SBipGp2knjuhLXgMI8jTJWUClNaHtX8aVMvXBrJhiaebBf8wY2DmIhfJdCTS3KOCmC15015JUzUk6KuyOyIHxr)
*https://bitcointalk.org/index.php?topic=5276423.msg%msg_id%*

Reserves of the token pairs are deposited by liquidity providers, who “invest” in the pool by depositing a proportional amount of tokens A and B, and receive liquidity shares, which grant them a fractional claim on tokens in the pool. Liquidity providers can redeem their shares and reclaim the tokens, which may in the meantime grow from fees charged during trading.

As the exchange rate changes for exogenous reasons, arbitrageurs have an incentive to buy and sell the tokens, aligning the price.

Uniswap, and similar automated market makers, are interesting systems to simulate given their well defined behaviors and operation in complex environments, where different starting parameters (token reserves, fees) can lead to significantly different outcomes for traders, investors, and users.

![](https://cdn-us1.hash.ai/site/Screenshot-2020-11-17-1606111.png)

## About This Model
This simulation models the Uniswap protocol and evaluates arbitrage between two balancer pools and the gains / potential impermanent loss

It is made up of four agents:

- Two automated market makes running the Uniswap protocol
- An arbitrage agent that compares the price between the automated market maker. The agent arbitrages any differences.
- A liquidity providing agent that adds liquidity to a pool and later removes it.

## Running the model
With the default parameters we suggest stepping through the model to observe the price changes from steps 1-50. All the action happens in the plots tab (select it in the top right). It demonstrates price equalizing due to arbitrageur actions and gains to the liquidity provider. Then experiment with different fee/initial token allocations.

## Next Steps
There are many ways to expand the model:

- Compare the Uniswap agent with a traditional exchange, modeled as as a Brownian motion process).
- Calibrate the scenario against historical data, using a real token pair and exchange data to observe how well the model matches actual trading behavior. 
- Add competing arbitrage agents, and malicious “rug pull” strategies. 

If you’re interested in adapting it or just want to chat about the implementation – or point out a bug 🙂 - drop me a line!
