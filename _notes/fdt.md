---
title: Functional Decision Theory
tags: decision-theory
---

Functional Decision Theory (or FDT) is a [[decision theory]] model that brings the decision making algorithm itself into the decision process. In FDT, correct decision making centers on choosing the output of a decision function, instead of choosing the best 'physical' action to take ([[Causal Decision Theory]]) or taking the action with the highest probability of leading to the best outcome ([[Evidential Decision Theory]]). 

A key insight is that FDT incorporates the idea of [[embedded agency]] into decision theory - the agent making a decision is not separate from the environment, but part of it, and should be included in the decision selection. Contrast this with [[Causal Decision Theory]] which in essence says to take a particular action that will cause the best outcome, assuming the rest of the world stays fixed. If other agents are modeling that agent, for instance predicting what it is going to do, this can lead to counter-intuitive, bad outcomes, where the agent doesn't incorporate that external 'logical dependency' in its decision. This is particularly evident when there are many other versions of the same agents in environments.

For example, in the classic [[prisoner's dilemma]] game, CDT agents using the same decision making process always choose to defect, as they are identifying which action that they can take (while holding the other agent's actions as fixed). Two FDT agents, running the same algorithm, can identify that they are using the same algorithm and, realizing the logical dependency, set that to cooperate, maximizing payoff.

![](https://firebasestorage.googleapis.com/v0/b/firescript-577a2.appspot.com/o/imgs%2Fapp%2Fben%2FRErQs6g283.png?alt=media&token=f31ea875-272d-4b6b-986c-0d653dfcf5bf)
*Image from [FDT in an Evolutionary Environment](https://arxiv.org/pdf/2005.05154.pdf)*

This extends to cases where one agent predicts another agent's choices, which creates a logical dependency between them. For instance, [Parfit's Hitchhiker](https://arbital.com/p/parfits_hitchhiker/), a thought experiment involving murdering hitchhikers:

> You are stranded in the desert, running out of water, and soon to die. Someone in a motor vehicle drives up to you. The driver of the motor vehicle is a selfish ideally game-theoretical agent, and what's more, so are you. Furthermore, the driver is Paul Ekman who has spent his whole life studying facial microexpressions and is extremely good at reading people's honesty by looking at their faces.
>
> The driver says, "Well, as an ideal selfish rational agent, I'll convey you into town if it's in my own interest to do so. I don't want to bother dragging you to Small Claims Court if you don't pay up. So I'll just ask you this question: Can you honestly say that you'll give me $1,000 from an ATM after we reach town?"
>
> On some decision theories, an ideal selfish rational agent will realize that once it reaches town, it will have no further incentive to pay the driver. Thus, agents of this type answer "Yes," whereupon the driver says "You're lying" and drives off leaving them to die.

An FDT agent outperforms CDT agents because it can recursively reason about the driver's reasoning. If it were to decide to lie and say yes but then defect once its in the city, the driver would know and leave them to die. But, because an FDT agent could reason that if its algorithm had the option to defect and not pay in the city, it would die, then it can instead run the algorithm that has no ability to potentially defect. FDT enables binding precommitments between its current and future selves by modifying algorithms to lock in 'timeless' decisions. 



- [Functional Decision Theory: A New Theory of Instrumental Rationality](https://arxiv.org/pdf/1710.05060.pdf) 

- [FDT in an Evolutionary Environment](https://arxiv.org/pdf/2005.05154.pdf)