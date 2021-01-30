---
tags: academic research ai
---

- Author:: Rich Sutton
- Source:: https://archive.vn/sD0RM

The biggest lesson from [[AI]] research is that general methods that leverage computation are the most effective by a large margin. This is because of [[Moore's law]]. The background assumption of a lot of AI research was that computation is constant but in actuality the available compute is increasing. [[For how much longer?::rmn]]This assumption led researchers to take actions that were effective in the short term - such as fine tuned, complex models - but that will fall to general methods as computation increases. In the long run this trend will dominate, and simple methods that can use large amounts of compute will work better.

Taking a fine tuned vs general approach are not necessarily opposed, but in practice if you spend time doing one you won't do the other. This same pattern played out in chess, in Go, in computer vision, in speech recognition, etc. Researchers tried to make the systems work the way they thought human minds worked, or by leveraging knowledge of the structure of the problem domain, but in the end massive computation was better. AI Researchers have, frequently, tried to build specific knowledge into their agents, which helps in the short term and is satisfying, but in the long run it plateaus and inhibits further progress. Breakthrough progress has come from scaling learning and search, both of which (appear) to scale to arbitrarily high levels. 

Minds are very complex and we should stop trying to think that we can build in the important parts; instead we should build the ability to discover into computers so they can find the effective path.

I frequently return to this essay as a cornerstone gear in my models of [[AI]] development. I am particularly keen in applying the lesson to [[agent based models]].
