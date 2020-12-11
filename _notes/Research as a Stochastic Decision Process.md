---
tags: research productivity decisions
---

| Categories | #Article |  
| Author     | Jacob Steinhardt  | 
| Source | https://archive.vn/27Rvs

- ## Notes
- In a project where there are independent sources of uncertainty, a general principle is to reduce uncertainty at the fastest rate possible.
- To do that, sort the components of the project in order of most informative per unit time to least informative per unit time. You can sort the components by expected time saved - prioritizing the tasks that are easy to do and, if they fail, will save us the most time by not having to do the subsequent tasks. Or you can sort the components based on failure rate.
- Failure rate can be modeled as a Poisson Arrival Process. For instance, if a task takes 20 minutes and there is a 20% chance it fails, then roughly speaking there is a 1% chance every minute of a failure arriving.
    - You can estimate the probability of success of a task and how long it will take, and then compute failRate = log(1/pSuccess) / Time. Sort the tasks in decreasing order, with the highest failure rate tasks first.
- Additionally derisk the components of a task - quick processing of individual component tasks.
- Ultimately we're modeling the research problem as a multi-round game where in each step we're taking an action that gives us information, and our goal is to 
    - Maximize the probability of eventual success
    - Minimize expected time spent. If the problem is not feasible, we want to give up as soon as possible. If it is feasible we want to spend the least amount of time possible to find the solution.