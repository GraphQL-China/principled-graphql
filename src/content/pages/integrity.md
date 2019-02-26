---
path: /integrity
title: 完整原则
description: 确保图被明确定义、稳定且一致
order: 1
image: ../images/integrity.png
---

## 1. 单一图

> 你的公司应当只有**一个统一的图**，而不是多个团队分别创建的多个图。

By having one graph, you maximize the value of GraphQL:

* More data and services can be accessed from a single query
* Code, queries, skills, and experience are portable across teams
* One central catalog of all available data that all graph users can look to
* Implementation cost is minimized, because graph implementation work isn't duplicated
* Central management of the graph – for example, unified access control policies – becomes possible

When teams create their own individual graphs without coordinating their work, it is all but inevitable that their graphs will begin to overlap, adding the same data to the graph in incompatible ways. At best, this is costly to rework; at worst, it creates chaos. This principle should be followed as early in a company's data graph adoption journey as possible.

## 2. 联合实现

> 虽然只有一个图，但该图应该由多个团队**联合**实现。

Monolithic architectures are difficult to scale without highly specialized infrastructure, and data graphs are no exception. Instead of implementing an organization's entire data graph layer in a single codebase, responsibility for defining and implementing the graph should be divided across multiple teams. Each team should be responsible for maintaining the portion of the schema that exposes their data and services, while having the flexibility to develop independently and operate on their own release cycle.

This maintains the value of a single, unified view of the graph, while keeping development efforts across the company decoupled.

## 3. 追踪在注册表中的 Schema

> 注册和追踪图时应当有一个**单一的事实来源**。

Just like it's important to track source code in a version control system, it's important to track the definition of your graph in a schema registry. There should be a single schema registry for your company that is the authoritative definition of the graph, rather than relying on whatever processes are running at the moment or whatever code is checked in on a developer's laptop. Like a source control system, the schema registry should store the history of changes to the graph and who made them, and it should understand the concept of multiple versions of the graph (for example, staging and production, or different development branches) in a way that parallels the software development process.

The schema registry should become the central hub of the system, powering developer tools, workflows, or any business processes that would benefit from awareness of the data graph and any actual or proposed changes to it.

<!-- end -->
