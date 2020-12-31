
I'm interested in whether [[Bitcoin]]'s protocol has ossified, and whether that is good or bad for Bitcoin's long term value. Ossified would mean that there was no potential for implementing a change to Bitcoin's underlying protocol that would be adopted by a supermajority of nodes, thus causing a soft or hard fork if the change were adopted.

Over the past year there have only been three (or five if you include each Taproot BIP separately) BIPs merged. In total [42 BIPs](https://github.com/bitcoin/bitcoin/blob/master/doc/bips.md) have been merged, averaging 8.4 BIPs per year since 2016 when BIPs started to be tracked as standalone proposals.

There's good reason to believe this trend will continue. Ossification, while often having a negative connotation, has benefits for Bitcoin.

- Bitcoin Devs are extremely risk averse:  Changes that potentially break bitcoin would be *very* bad, for obvious reasons, and the reputational penalty and financial losses for approving code that breaks bitcoin are high for a developer.
- Developers are a target: Governments or malicious actors who want to change Bitcoin don't have an easy way to do that, as by and large Bitcoin is decentralized. One obvious target are respected members of the Bitcoin community, those who could plausibly develop and merge BIPs. Putting pressure on developers could work, especially if changes are common enough that developers could be expected to actively submit commits. However if bitcoin is fully ossified, such that no one could change its protocol, that removes an attack surface.

But, as a consequence of ossification, Bitcoin can't adopt features that might be beneficial. For instance novel privacy preserving cryptography, such as ZK-SNARKS, can't be easily implemented on Bitcoin. Other cryptocurrencies that are more willing to change their protocols could leverage new features like this to outcompete Bitcoin.

[I've created a Metaculus question for forecasting the number of BIPs that will be implemented in 2021.](https://www.metaculus.com/questions/6103/number-of-bips-adopted-in-2021/)

p.s. My favorite not yet merged BIPs are [300](https://github.com/bitcoin/bips/blob/master/bip-0300.mediawiki) and [301](https://github.com/bitcoin/bips/blob/master/bip-0301.mediawiki), the Drivechain protocol developed by CryptAxe and Paul Sztorc. If implemented this would enable two way pegs between Bitcoin and Sidechains. The Sidechains could run any arbitrary code, while the core Bitcoin protocol would remain unchanged. This strikes me as an ideal way to embrace novel cryptocurrency experimentation while avoiding risky changes to Bitcoin. 
