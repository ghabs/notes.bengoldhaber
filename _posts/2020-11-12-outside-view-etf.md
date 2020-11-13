---
layout: post
title: Outside View ETF - Creating indexes of forecastable questions
tags: draft
---
Prediction aggregation sites like the Good Judgement Open, Metaculus, and others have had success incentizing 'powerusers' to predict on well operationalized questions. The tournaments have a good track record of being well calibrated and accurate.

However, I think they are missing out on a potentially large number of users because of problems inherent in the format.

- Time intensive: Wading into the weeds of a question and investigating the ways it could resolve can take a considerable amount of time, which is a turnoff especially since there are few monetary rewards.
- Requires specialized expertise to understand the nuances: There are many ways that a specific question can resolve in unexpected ways - an experienced forecaster knows how to "lawyer" a question and evaluate edge cases
- Boring: There are many areas that I care about and am invested in that I don't necessarily want to dig into specific details. For instance, Foretell is a competition forecasting China and AI - I have high level thoughts on the area, but I don't really want to spend my free time compiling publication rates of Chinese researches.

Often I want to be able to bet my general attitude about a question or series of questions, and get feedback on it's calibration, without having to investigate the specifics of a question.

In essence I'd like to predict on a basket of questions, like an ETF, that represents my models. For instance if I'm a techno-optimist, I'd like to register a prediction on the topic area of self-driving cars, using a generally optimistic model. I would "buy" a collection of optimistic forecasts on a series of questions that are tied to self-driving cars. 

## Structure

<iframe style="border:none" width="800" height="450" src="https://whimsical.com/embed/9HBqeWEE87yvJsup27x95M"></iframe>

Fund managers assemble a basket of questions that will reflect a specific domain.

They express a theme for the fund - aka techno-optimism - and register predictions that represent that view. Then everyone who is part of their fund can forecast on the forecasts, which copies and transforms the underlying predictions. 1 is exactly the point of view of the fund, 0.5 would move the prediction to the midpoint, and 0 would sell the etf, inverting the predictions.

In forecasting aggregator competitions the fund manager is compensated by bringing more forecasters into the market, which increases the payout for being right (or potentially through some percentage of profits)

Example "funds":

- Outside view fund: Use the base rates and reference classes for a set of questions as the primary (only?) input to a forecast.
- Cynicism fund: What would the most cynical person in the world forecast on a set of questions?
- Momentum fund: Maybe there are strong "follow the crowd" effects on these sites where you could profit by quickly seeing which direction the crowd is forecasting and registering a prediction with them.

MVP:

I created a colab notebook where I registered predictions on a collection of ML/AI questions from a perspective that the field of AI will soon go through another AI winter. If you sign in with your metaculus account you can use those same forecasts or apply a transformation representing your confidence in my forecast (thanks to the Ought team for releasing the ergo library that made this easy to do!)


## Is this good?
Outside of whether this will work, there's the question of 'should this work'? Perhaps the reason forecasting competitions are effective is they weed out casual users who aren't willing to go through the effort of researching each question, and by introducing etfs we will make them less accurate.

I think this is a possibility, but I expect that incentives could be tweaked - for instance giving ETF creators more opportunities to get points or requiring a minimum participation rate of active traders - to prevent overweighting casuals. I also think there are a number of benefits, like more opinions coming in from a wider group and the opportunity to get more specific info on why someone registered a prediction the way they did (i.e. if I bet on the cynical etf, it reveals more of my underlying models.)

