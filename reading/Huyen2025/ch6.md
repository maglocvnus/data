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

An agent needs to have a **tool inventory**:
- **Read-only** tools allow the agent to perceive its environment.
- **Write-only** tools allow it to act upon its environment. 

There are three main categories of tool:
- knowledge augmentation tools
- capability extension tools
- write-action tools

#### Knowledge augmentation tools

Knowledge augmentation tools are read-only tools that allow an agent to retrieve additional context from sources such as:
- organisation-internal databases, document repositories, and APIs
- public sources, like the web.

These kinds of information retrieval tools prevent a model from becoming **stale**.

#### Capability extension tools

Capability extension tools are read-only tools that address the inherent limitations of large language models.

Some examples are:
- arithmetic calculators
- calendars, time zone and unit converters, translators
- code interpreters and debuggers.

Some tools allow outputs to be rendered non-textually:
- text-to-image models, like DALL-E
- Latex compilers for maths formulas
- HTML renderers.

Other tools allow non-textual input to be captured:
- image-captioning tools
- audio transcription tools
- OCR tools.

#### Write-action tools

Write-action tools allow an agent to make changes to its environment.

For example:
- An SQL executor can create new tables, or update or delete existing ones.
- An email API can send and respond to emails.
- A banking API can transfer money between accounts.

### 6.2.3. Planning

Complex tasks require planning — the creation of a roadmap outlining the steps needed to accomplish the task.

The planning process can be seen as having three stages:
1. Understand the task
2. Consider different options to accomplish the task
3. Choose the most promising option.

#### Planning overview

Some plans are more efficient than other plans. Therefore, planning itself should be decoupled from execution of the plan:
1. Generate a plan (task decomposition)
2. Validate the plan
3. Execute the plan; otherwise, generate a new plan.

Each of these phases can be delegated to a specialist agent, resulting in a **multi-agent** system. 

Alternatively, you can generate multiple plans **in parallel**, and have an agent choose the best one.

The first phase of planning could involve **intent classification** — figuring out what the user is trying to achieve in a prompt (from a finite set of possibilities).

Finally, humans can be involved at any stage of the planning process.

#### Foundation models as planners

Some commentators are sceptical about the potential for autoregressive foundation models to generate good plans.

Planning is a search problem, often requiring backtracking, and simple models just work forwards.

Therefore, a foundation model should probably be just one component in a multi-agent planner, alongside other components like a search tool, a state tracking system, etc.

#### Plan generation

The simplest way to turn a model into a plan generator is with prompt engineering.
- tell the model you want it to create a plan
- list the available actions
- give it a few examples of plans

The more detailed the prompt, the bestter the plan will be. 

#### *Function calling*

Function calling is the part of plan generation where a tool is invoked. 

Two parts to function calling:
- craste a tool inventory
- specify the tools an agent can use


#### *Planning granularity*

A plan can have different levels of granularity. 
- quartwr by quarter
- month by month
- week by week

Hierarchical planning involves:
- start by generating a quarter by wuarter plan
- for each quarter generate a month by month plan
- for each month, generate a week by week plan



#### *Complex plans*

Plans are not just sequential but can have a control flow
- parallel flows
- conditionsl floows
- loops




#### Reflection and error correction

Even the best plans need to be constantly evaluated and adjusted to maximise their chance of success. 

Reflectoon and error correction can be fone by a soecialist agent, eg a scorer. 

A common pattern involves interleaving reasoning and action. 

At each step the agent must explain its thinking, take actions, and then anslyse onservations, until the task is considered complete. 

This can be done in a multi agent framework. 

Reflection can be expensive however, requiri g a lot of tokens to be consumed. 

#### Tool selection

Tool selection requires a lot of experimentation to find the optimsl tool inventory for an agent. 

Agents caould also be asked to snalyae their own tool use and then suggest or even build new tools. 


### 6.2.4. Agent failure modes and evaluation

## 6.3. Memory




----

Back up to: book | Maglocvnus
