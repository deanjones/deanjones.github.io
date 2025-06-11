---
layout: post
title:  "Structured outputs"
date:   2025-05-13 18:30 +0100
categories: llms
---

Getting an LLM to generate a structured output (e.g. JSON which conforms to some schema) is key aspect of engineering LLM-based solutions.
For example, in August last year OpenAI released [Structured Outputs](https://openai.com/index/introducing-structured-outputs-in-the-api/) which is a replacement
for the previous method, JSON-mode, which was unreliable and didn't guarantee that generated JSON conformed to the desired schema. The Python API allows
you to specify that the output should be structured to conform to Pydantic-defined classes, which is super-useful.

However, what if you're building a solution using a local model, and still want structured output? This is where tools like [Instructor](https://python.useinstructor.com/)
 and [Outlines](https://github.com/dottxt-ai/outlines) are useful. Instructor uses a retry-based approach - it asks the LLM to generate JSON, and if the response
 doesn't match the required structure, it tries again (up to some specificed limit). This repeated querying does have an impact on latency and (if you're paying
 to use a third-party model) cost. Outlines takes a different approach; it modifies the model logits (the unnormalised predictions from the model) to ensure that
 only valid outputs are generated. It's actually more general than just generating JSON - it provides a [DSL](https://dottxt-ai.github.io/outlines/latest/reference/regex_dsl/)
 which essentially allows regular expressions to be defined which specify the allowed structured output to be defined.
 

