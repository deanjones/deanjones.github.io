---
layout: post
title:  "Agents and hammers"
date:   2025-06-10 14:00:08 +0100
categories: agents
---

"When all you have is a hammer, everything looks like a nail". Ok, but what if you open the toolbox and you see this:

![A variety of hammers](hammers.png "Hammers")

This is an issue which is gaining some attention in relation to LLMs currently. If an LLM has access to a large selection
of tools, how does it choose the best tool for a given situation?

In ["RAG-MCP: Mitigating Prompt Bloat in LLM Tool Selection via Retrieval-Augmented Generation"](https://arxiv.org/abs/2505.03275) the authors
refer to this as *decision overhead*: "with a long list of tools (many of them similar in scope), the model faces a more complex decision when
choosing if and which tool to invoke. The greater the choice, the higher the chance of error, such as selecting an suboptimal tool or
misinterpreting what a tool does."

An alternative approach is to appeal to the system design principle of [separation of concerns](https://en.wikipedia.org/wiki/Separation_of_concerns).
A well-designed system (whether it uses LLMs or not) is composed of multiple modules, which have the freedom to vary independently. In an agentic system,
these "independent modules" are agents. The functional boundaries of agents should be defined according to the principle of
[cohesion](https://en.wikipedia.org/wiki/Cohesion_(computer_science)): "the degree to which the elements inside a module belong together". If complex systems
are decomposed into a set of co-operating, cohesive agents, each agent only has to select from the smaller set of tools that it uses.
However, as a German colleague once said to me: "[Problem nicht gelöst, sondern verschoben](https://translate.google.com/?hl=en&sl=de&tl=en&text=Problem%20nicht%20gel%C3%B6st%20sondern%20verschoben&op=translate)".
We now have the problem of *agent discovery*. 



