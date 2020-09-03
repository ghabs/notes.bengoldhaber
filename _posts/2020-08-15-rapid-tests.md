---
layout: post
title: Rapid Tests
---

*[Visit the accompanying simulation to explore the model](https://hash.ai/index/5f2c19d54951e8798edeb8cb/sir-infection-network-w-rapid-tests)*

## Introduction

With all of the controversy around lockdowns and mask wearing, it feels as if attention has fallen away from scientific and technical solutions to the SARS-CoV-2 pandemic. But of course this is still an enemy that doesn't care about the political implications of policies - only whether it results in fewer infections.

The sooner someone learns they have SARS-CoV-2 the sooner they can self-isolate and reduce transmission. This is why increasing testing capacity has been - and still is - so important.

But not all tests are created equally. Different approaches have different sensitivity, different turnaround times, and different costs. In this simulation we explore the effect of these tradeoffs and conclude that readily available, quick turnaround tests are an excellent approach to slowing and ending the pandemic. The FDA should immediately relax the strict sensitivity requirements for rapid tests.

## Test Types

Currently almost all of the testing is done with RT-PCR assays. Someone who suspects they might have the virus goes to a specialized site where a doctor or nurse uses a nasal swap to collect a sample. 

This sample, either on site or off-site, is then treated to remove extraneous substances, and the RNA is reverse transcribed to DNA. If the virus is present it will bind to additional fragments of DNA, added in the process. The DNA fragments are placed in a PCR machine which cycles through a heating and cooling process which amplifies the DNA sample exponentially. By the end there's enough viral DNA present to make it easy to identify through fluorescence. 

RT-PCR is very sensitive - minuscule amounts of SARS-CoV-2 can be detected. However it can take several days to receive the results, and the process is complicated enough that it requires specialized training, limiting the number of providers and the total number of tests.

Over the past few months new alternative approaches of testing have been developed. These include paper strip style tests, cheap enough that [millions could be manufactured for daily use.](https://archive.vn/ZR0Q6) In particular the RT-LAMP assay approach seems promising for getting testing into the hands of individuals. A spit sample is mixed with the primers, enzymes, and transcriptase and the reaction happens at a constant temperature - it's possible for anyone to do it at home in a manner of minutes.

However, RT-LAMP is less sensitive than RT-PCR; it requires the virus to have already reached a certain viral load in the body, around the point where an individual becomes infectious.

[Dr. Eric Topol](https://twitter.com/EricTopol/status/1288512276845039617?s=20) has a great table showing the differences between the two tests.

![Image](https://pbs.twimg.com/media/EeG3ABdVAAEkr9g?format=jpg&name=small)

RT-LAMP tests aren't being manufactured because there's uncertainty whether the FDA will approve the use of less sensitive tests. Implicit is the question of how important the sensitivity of a test is relative to other parameters, such as the speed or cost of a test. 

## Simulations

This question piqued our interest because at HASH we develop multi-agent simulations to model complex systems. These are systems where the second order outcome of a decision are not obvious, such as the decision to choose between two different testing regimes.

 We can model the introduction of tests with different sensitivity and turnaround time, and see how this affects behavior in a simplified SIR (susceptible - infectious - recovered) simulation and the relative rates of infection. 

*Note*: This specific simulation isn't a quantitative forecast - it is **not** calibrated to real world data. Rather, it's useful as a way of making a qualitative comparison; given the choice between tests that are very sensitive and slow, or ones that are less sensitive but fast, which is better? If we ground our intuitions in simulations, we can make better decisions.

The core of the simulation is a social graph representing a contact network. We use the Watts-Strogatz algorithm to produce a network with small world properties. Like the tests themselves we wanted to rapidly create these models, and so we extended a [Watts-Strogatz network](https://hash.ai/index/5ef79da2478e6ebf1d6a6003/watts-strogatz-network) simulation published by a [HASH user, @eadan](https://hash.ai/@eadan) in our open market of agent based models. 1000 "people" agents are spun up with several degrees of connection to other agents in the graph. Every time step (roughly representing one day) they meet with a random number of connected agents. If a susceptible person meets with an infected person, there's a chance that they'll catch the virus. After a certain number of time steps the agents will recover from the infection and is immune from the disease.

From there we crafted intervention scenarios. 

- Scenarios
  - No testing. The base case is no testing is available for any agents.
  - PCR based testing. Using PCR tests that can detect any amount of the virus, but  turnaround results in two to five days and are not always available to the agent.
  - LAMP based testing. Tests which turn around in the same day and are available on hand, but that can only detect the virus after a certain number of time steps has passed. 

If a PersonAgent learns from a test that they're sick, they'll stop meeting with people until they've recovered.

## Running the Scenarios

Open the simulation and select the globals.json file in the left hand sidebar. Set the scenario_select property to the name of the scenario to run. The default options are ["no_testing","pcr", "lamp"].

You can view the results of a scenario in the 3D viewer or in the plots tab, which will display a chart of the number of susceptible, infected, and recovered agents.

In globals.json you can modify any of the parameters of the simulation. For instance changing the sensitivity of a test type or the likelihood that a person will take a test on a given day.

## Results

**No Testing**
![notesting](https://cdn-us1.hash.ai/site/notesting-e1596820957454.png)

**PCR**
![pcr](https://cdn-us1.hash.ai/site/pcr-e1596821077940.png)

**LAMP**
![LAMP](https://cdn-us1.hash.ai/site/lamp-e1596821364358.png)


The results are dramatic. The faster turnaround time and availability of the LAMP tests reduces the rate of infection by at least half, and that's under the most generous of assumptions for the current testing regime, where every person is being tested every few days. 

If we try and model real world conditions - for instance based off of studies of [confirmed cases vs. serological prevalence of COVID antibodies](https://www.statnews.com/2020/07/21/cdc-study-actual-covid-19-cases/) - the likelihood of getting a traditional test might be an order of magnitude lower, and the comparison becomes much starker:

![](https://cdn-us1.hash.ai/site/notesting-e1596820957454.png)

Across parameter runs we see that the most important factor is the speed and availability of tests. Even very low sensitivity tests, if readily available, can change the course of the pandemic. 

## Conclusion

Policy is currently being made by ungrounded assumptions and status quo bias. The default expectation is that the more sensitive the test the better. By simulating different approaches to testing we can get a gut level appreciation that in fact the speed of test results matter much more than does the sensitivity of the tests.

From simple simulations we can see that a cheap test regime approach save lives and let us reopen the country quickly and responsibly. The technology is available now, we're hamstrung solely by a lack of political will to clarify the regulatory environment.

[Call your governor, and write to your representative.](https://www.rapidtests.org/) And If you're interested in building more detailed simulations of SARSCOV2 (or other simulations) [reach out to us](https://hash.ai/contact). We'd love to help.