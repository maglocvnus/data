# Chapter 6. RAG and agents

## 6.1. RAG

### 6.1.1. RAG architecture

### 6.1.2. Retrieval algorithms

### 6.1.3. Retrieval optimisation

### 6.1.4. RAG beyond texts

## 6.2. Agents

The powerful new capabilities of foundation models have made possible applications that implement intelligent, rational agents — assistants, coworkers, coaches, etc. 

These agents can create websites, gather data, plan trips, do market research, manage customer accounts, automate data entry, interview candidates, negotiate deals etc. 

Their potential economic value is enormous. 

### 6.2.1. Agent overview

An agent can: 
- **perceive** its environment
- **act upon** its environment.

AI agents generally interact with their environments using **tools**.

For example, ChatGPT can call its internal tools to search the web, execute Python code, generate images, etc.

A foundation model functions as the brain of an AI agent — it interprets both the input task and feedback from the environment, plans a sequence of actions to achieve this task, and then determines whether the task has been accomplished. 

There are two main reasons why agents have a particular need for more powerful foundation models:
- Agents needs multiple steps to solve problems, each step can introduce mistakes, and these mistakes will compound; hence better models are needed that make fewer mistakes.
- Agents can use tools to perform actions in the real world, so the stakes are higher, and tolerance for mistakes is lower.

### 6.2.2. Tools

An agent needs to have a tool inventory.

Read-only tools allow an agent to perceive its environment. 

Write-only tools allow it to act upon its environment. 

Three categories of tool:
- knowledge augmentation tools (context construction)
- capability extension tools
- tools that let an agent act on its environment. 

#### Knowledge augmentation

Tools that augment a model with your organisations internal processes and information:
internal people search, inventiry API, slack retriever.

Tos that retrieve nformation from public sources, esp the web. 

Web browsing tools prevent a moddl from growing stale. 

#### capability extension

tools that address the inherent limitations of LLMs

eg. a calculator (since LLMs are bad at math)

calendar, timezone converter, unit converter, translator 

code interpreters and debuggers

text to image models
eg ChatGPT uses DALL-E

Latex compilers, HTMl renderers, etc

image captioning tool

audio transcription tool

OCR tool

Tools can significantly boost a model's performance

#### Write actions

SQL executor can update tables

email API can respond to emails

banking APIs can transfer money

But we need to take safety and security seriously. 

### 6.2.3. Planning

#### Planning overview

#### Foundation models as planners

#### Plan generation

#### Function calling

#### Planning granularity

#### Complex plans

#### Reflection and error correction

#### Tool selection




### 6.2.4. Agent failure modes and evaluation

## 6.3. Memory




----

Back up to: book | Maglocvnus
