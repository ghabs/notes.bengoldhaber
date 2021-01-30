---
tags: research productivity decisions
---

| Categories | #Article |  
| Author     | Jacob Steinhardt  | 
| Source | https://archive.vn/27Rvs

In a project where there are independent sources of uncertainty and it is unclear if the project can/will work, a good general principle is to reduce the uncertainty at the fastest rate possible.

To do that, sort the components of the project in order of most informative per unit of time to least informative per unit of time. You can sort the components by expected time saved - prioritizing the tasks that are easy to do and, if they fail, will save us the most time by not having to do the subsequent tasks. An example would be if a project was made up of ten tasks, with one task easy to complete in one day. If, on completion of the task, you are likely to learn something new about the world that could the other tasks are impossible, you should do that one first.

Alternatively you can sort the components by failure rate. Failure rate can be modeled as a Poisson arrival process. For instance, if a task takes 20 minutes and there is a 20% chance it fails, then roughly speaking there is a 1% chance every minute of a failure arriving. You can estimate the probability of success of a task and how long it will take, and then compute failRate = log(1/pSuccess) / Time. Sort the tasks in decreasing order, with the highest failure rate tasks first.

Ultimately we're modeling the research problem as a multi-round game where in each step we're taking an action that gives us information, and our goal is to 
    - Maximize the probability of eventual success.
    - Minimize expected time spent. If the problem is not feasible, we want to give up as soon as possible. If it is feasible we want to spend the least amount of time possible to find the solution.