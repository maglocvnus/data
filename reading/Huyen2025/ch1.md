# Chapter 1. Introduction to building AI applications with foundation models

Post-2020, AI has been all about **scale**, with two major consequences:
- AI models are becoming more powerful, capable of more tasks, enabling more applications, creating more economic value, and improving quality of life. 
- Few organisations can afford to train a state-of-the-art LLM, leading to the emergence of **model-as-a-service** architectures.

Demand for AI has increased as the barriers to entry have decreased, leading to the rise of <mark>AI engineering</mark> — the job of building applications on top of readily available AI models.

Contents:
- 1.1. [The rise of AI engineering](#11-the-rise-of-ai-engineering)
- 1.2. [Foundation model use cases](#12-foundation-model-use-cases)
- 1.3. [Planning AI applications](#13-planning-ai-applications)
- 1.4. [The AI engineering stack](#14-the-ai-engineering-stack)

## 1.1. The rise of AI engineering

### 1.1.1. From language models to large language models

#### Language models

There are two main types of language model:
- **masked** language models — trained to predict missing words anywhere in a sequence 
- **autoregressive** language models — trained to predict the next word in a sequence.

Masked language models (eg. BERT — bidirectional encoder representations from transformers) are commonly used for non-generative tasks like sentiment analysis and text classification, or code debugging.

Autoregressive language models are the models of choice for text generation. These models are the most widely used, since many different kinds of task can be framed as (probabilistic) ‘completion tasks’ — translation, summarisation, coding, solving maths problems, spam classification, etc.

Autoregressive language models are **generative**, since they can generate open-ended outputs from a fixed, finite vocabulary. 

#### Self-supervision

Language models are particularly scalable because they can be trained using self-supervised learning. The output labels needed for supervised learning do not need to be added (expensively and time-consumingly) by a human, but rather are inferred directly from the training corpus (the ‘next word’).

### 1.1.2. From large language models to foundation models

**Multimodal models** add additional data modalities to an LLM — images, audio, videos, 3D assets, protein structures, etc.

**Foundation models** are general-purpose models capable of many different tasks.

Some AI engineering techniques for adapting a foundation model to a new task are:
- **prompt engineering** — craft detailed instructions with examples of the desired output (one-shot or few-shot prompting)
- **retrieval-augmented generation** (RAG) — supplement the instructions with a database of relevant texts
- **fine-tuning** — further train the model’s parameters on a more specific dataset.

### 1.1.3. From foundation models to AI engineering

Three factors have led to rapid recent growth of AI engineering:
- foundation models have improved dramatically in their general-purpose problem-solving capabilities
- investment in AI has increased exponentially
- the (API-driven) model-as-a-service approach has lowered the entrance barrier for building AI applications. 

## 1.2. Foundation model use cases

Enterprises usually prefer to start their AI journeys by developing **lower-risk** applications:
- internal-facing applications (for employees) rather than external-facing ones (for customers)
- closed-end classification tasks, rather than open-ended generative tasks. 

### 1.2.1. Coding

AI coding tools are the most popular use case for generative AI, for example:
- code completion tools (eg. GitHub Copilot)
- screenshot-to-code tools for UI development
- code translators
- test generators and documentation generators.

AI tools are better at some software engineering tasks (eg. front-end development) than others (eg. back-end development).

### 1.2.2. Image and video production

The probabilistic nature of AI means that it excels at creative tasks, like image and video generation and editing. 

AI is often used to generate first drafts and prototypes for human experts to iterate upon (after initial user testing).

### 1.2.3. Writing

AI excels at writing tasks, for example:
- autocompletion and autocorrection
- email rewriting and improvement
- essay writing and customised book generation
- note-taking
- search engine optimisation.

This can have downsides though — AI slop. 

### 1.2.4. Education

Education use cases for AI include:
- summarising textbooks
- personalised lecture plans and learning materials
- roleplaying in language learning
- quiz generation.

### 1.2.5. Conversational bots

Conversational agents can be highly versatile, for example:
- AI therapists
- digital companions
- customer support assistants
- smart non-player characters (NPCs) in video games.

### 1.2.6. Information aggregation

AI is highly capable at filtering and digesting, distilling, aggregating and summarising  useful information. 

A good example involves **talk-to-your-docs** tools, which allow you to retrieve information in a conversational manner.

### 1.2.7. Data organisation

AI can help organise huge collections of unstructured or semi-structured data so that they can be searched later. 

For example, AI can automatically generate text descriptions of images and videos.

AI is also very good at analysing data — generating visualisations, identifying outliers, making predictions and forecasts. 

### 1.2.8. Workflow automation

AI can automate repetitive tasks like booking restaurants, requesting refunds, planning trips, filling out forms, lead management, invoicing, managing customer requests. 

**Agents** are AI tools that can create **plans**, and use **tools** to act on the outside world — look up phone numbers, place calls, add appointments to your calendar, etc.

AI agents have huge potential to generate economic value. 

## 1.3. Planning AI applications

Why build an AI application? 
How should you go about doing it?

### Use case evaluation

Consider the risks and opportunities:
- If you don’t do this, competitors with AI can make you obsolete. 
- If you don't do this, you’ll miss opportunities to boost profits and productivity. 
- You're still unsure where AI will fit into your business, but you don’t want to be left behind. 

#### The role of AI and humans in the application

AI can be used in a product in different ways:
- critical or complementary — the more critical AI is to the application, the more accurate and reliable the AI part has to be
- reactive or proactive — a reactive AI feature responds to users’ requests rather than whever there is an opportunity for it
- dynamic or static — are features updated continually or periodically?

To what extent is there a humsn in yhe loop?
- the human can choose between several AI generated responses
- AI handles simple requests, but complex ones sre touted to a human
- AI handles everything, with no human intervention 

cf. Microsoft’s Crawl-Walk-Run framework:
- Crawl: human involvement is mandatory
- Walk: AI can only interact directly with internal employees
- Run: AI can directly interact with external users. 

#### AI product defensibility


### 1.3.2. Setting expectations

### 1.3.3. Milestone planning

### 1.3.4. Maintenance




## 1.4. The AI engineering stack

AI engineering evolved out of ML engineering.
- Some companies treat AI engineering as a subtype of ML engineering.
- Other companies treat AI engineering as a whole new type of job.

### 1.4.1. Three layers of the AI stack

The three layers are:
- **application development** — providing a pre-trained model with good prompts and necessary context; requires rigorous evaluation and good interfaces
- **model development** — training and fine-tuning models; inference optimisation; dataset engineering; also requires rigorous evaluation
- **infrastructure** — model serving; managing data and compute; monitoring.

Many of the principles and techniques of ML engineering are still valid for working with foundation models, especially the importance of **systematic experimentation** — with different models, prompts, retrieval algorithms, sampling variables, etc.

### 1.4.2. AI engineering versus ML engineering

#### Model development

#### Application development

### 1.4.3. AI engineering versus full stack engineering




---

Back up to: [Huyen (2025)](index.md) | [Maglocvnus](../../index.md)
