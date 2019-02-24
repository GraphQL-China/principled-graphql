---
path: /integrity
title: Integrity Principles
description: Ensuring that the graph is well-defined, stable, and consistent
order: 1
image: ../images/integrity.png
---

## 1. One Graph

> Your company should have **one unified graph**, instead of multiple graphs created by each team.

只使用一个图，你可以最大化 GraphQL 的价值：

* 可以通过单个查询访问更多数据和服务
* 代码、查询、技能和经验可跨团队移植
* 图的每个用户都可以查看所有可用数据的中心目录
* 实现成本最小化，因为无需重复图的实现工作
* 图的中心管理——例如，统一访问控制策略——变得可能

当不同团队在没有协调工作的情况下分别创建独立的图时，几乎不可避免出现图之间的重叠，于是只能以不兼容的方式向图添加相同的数据。在最好的情况下也会造成很高的返工成本；而在最坏的情况下会造成混乱。应当尽早在公司的数据图使用中遵循本原则。

## 2. Federated Implementation

> Though there is only one graph, the implementation of that graph should be **federated** across multiple teams.

如果没有高度专业化的基础结构，单片架构很难扩展，数据图也不例外。不应当在单个代码库中实现组织的整个数据图这一层，而是应当在多个团队之间划分定义和实现图的职责。每个团队都应当负责维护公开其数据和服务的那一部分 schema，同时具有独立开发和在自己的发布周期中运行的灵活性。

这样可以保持图作为单一统一视图的价值，同时解耦整个公司的开发工作。

## 3. Track the Schema in a Registry

> There should be a **single source of truth** for registering and tracking the graph.

就像在版本控制系统中跟踪源代码一样，跟踪 schema 注册表中对于图的定义非常重要。你的公司应当有一个单独的 schema 注册表作为对图的权威定义，而不是依赖于当前正在运行的任何进程或是在开发人员的笔记本电脑上签入的任何代码。与源代码控制系统一样，schema 注册表应该存储更改历史记录以及创建它们的人员，并且应该理解图的多个版本的概念（例如暂存、生产环境或不同的开发分支），在某种程度上类似于软件开发过程。

Schema 注册表应成为系统的中心枢纽，为开发者工具、工作流或任何将从数据图以及对其任何实际或建议的更改中受益的业务流程提供支持。

<!-- end -->
