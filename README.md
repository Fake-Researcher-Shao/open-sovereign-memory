# Open Sovereign Memory (OSM)

> **"Memory and Context should be user assets, not model parameters."**

![License](https://img.shields.io/badge/license-MIT-blue.svg) ![Status](https://img.shields.io/badge/status-concept-orange.svg) ![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)

## 📖 The Manifesto

We live in a multi-model world.

* **General Inquiry:** Gemini, ChatGPT
* **Quick/Edge Questions:** Grok
* **Engineering & Data:** Cursor, Antigravity, Trae

Each tool is brilliant, but they are fragmented. They only know the "Task-Specific User." When you switch from one AI to another, the relationship resets. The familiarity is lost.

**The Core Problem:**
Currently, context and memory are assets owned by the *Model Providers*. This makes our relationship with AI non-transferable.

**The Vision:**
Context and memory must become **User Assets**.
* Portable.
* Standardized.
* Inheritable.

When memory follows the human, models simply become interchangeable interfaces—specialized workers accessing the same shared understanding of *who you are*.

---

## 🚀 Project Goal

**Open Sovereign Memory (OSM)** aims to define a standard protocol and file format for storing user context, preferences, working memory, and long-term history locally.

This enables a unified experience where:
1.  **Cursor** knows you just returned from a business trip (via OSM).
2.  **Gemini** helps you brainstorm research based on code you just wrote in Trae (reading the same OSM).
3.  **Local LLMs** audit your work with full knowledge of your stylistic preferences.

## 🏗 Architecture

The OSM operates as a middleware layer between the User and the various AI Models/Tools.

```mermaid
graph TD
    User((User)) --> OSM_Core[Open Sovereign Memory Core]
    
    subgraph "The Memory Asset (Local/Encrypted)"
        Profile[Static Profile]
        LTM[Long Term Memory / Vector DB]
        STM[Short Term Working Context]
        Prefs[Tool Preferences]
    end
    
    OSM_Core <--> Profile
    OSM_Core <--> LTM
    OSM_Core <--> STM
    
    OSM_Core -->|Inject Context| GPT[ChatGPT / OpenAI]
    OSM_Core -->|Inject Context| CLD[Claude / Anthropic]
    OSM_Core -->|Inject Context| GEM[Gemini / Google]
    OSM_Core -->|Inject Context| LOC[Local Models / Ollama]
    OSM_Core -->|Inject Context| IDE[Cursor / Trae]
    
    GPT -->|Update Memory| OSM_Core
    IDE -->|Update Memory| OSM_Core

🇨🇳 原文：关于用户主权记忆的思考 (Origin)
This project was born from the following reflection:

我算是 Gemini 和 ChatGPT 的重度用户，一些零碎的小问题会更倾向用 Grok，而在更偏工程和数据处理的场景里，我常用 Cursor、Antigravity、Trae 这类工具做本地任务。不同模型、不同工具，各司其职。

从效率上看，这是一个很理想的多模型协作状态。但用久了，会慢慢浮现一个很抽象的问题。每一个模型，和我之间的 context 和 memory 都是“围绕任务的碎片化存在”。它们都很聪明，但它们认识的只是“某个任务中的我”。

于是就出现了一种很奇妙的状态：我可能和某一个 AI 聊得热火朝天，但换到另一个 AI 去处理工作任务，彼此之间却形同陌路。从体验上看，它们都是抽象的 AI；但从关系上看，我和每一个 AI，其实都在建立不同强度、不同深度的关系。

这就自然引出了一个更底层的问题：context 和 memory，到底是谁的资产？

如果它们是模型的资产，那我和每一个 AI 的关系，本质上都是不可迁移、不可复用、不可继承的；一旦切换模型、工具或平台，熟悉感就会被强制清零。

但如果 context 和 memory 是用户的资产，那是否可以被我带走、沉淀、标准化？

一种可能的形态是：OpenAI 能读，Anthropic 能读，Google 能读，国内模型也能读，甚至我自己 fine-tune 的小模型也能读。记忆和上下文跟着人走，模型只是不同的职业分工、不同人格风格的接口。

于是就会出现一种全新的协作状态：一个 AI 负责本地任务，一个 AI 负责 research，另一个 AI 随时解答小问题、审核结果；但它们都知道我昨天刚出差回来，都理解我的工作习惯、偏好和当前状态。

在这种情况下，我和所有 AI 的关系都会变得更紧密，而且是同时成立的。

甚至可以再往前推一步：如果这份 context 和 memory 资产一旦丢失，我很可能会在工作效率和生活状态上，出现明显、长期的下降。这时 AI 就不再只是“更换成本很低的工具”，而开始变成一种高迁移成本的生产与生活基础设施。

也许真正值得行业认真思考的，不是模型还要多聪明，而是—— 用户的记忆，是否应该继续被锁在单一模型里。
