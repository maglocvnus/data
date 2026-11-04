# Chapter 1. Introduction to building AI applications with foundation models

Post-2020, AI has been all about **scale**, with two major consequences:
- AI models are becoming more powerful, capable of more tasks, enabling more applications, creating more economic value, and improving quality of life. 
- Few organisations can afford to train a state-of-the-art LLM, leading to the emergence of **model-as-a-service**.

Demand for AI has increased as the barriers to entry have decreased, leading to the rise of <mark>AI engineering</mark> — the job of building applications on top of readily available AI models.

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

Enterprises usually prefer to start by developing lower-risk applications:
- internal-facing applications rather than external-facing ones
- closed-end classification tasks, rather than open-ended generative tasks. 

### 1.2.1. Coding

AI coding tools are by far the most popular use case:
- code completion tools, like GitHub Copilot
- screenshot-to-code tools for UI development
- code translators
- test and documentation generators

AI is better at some software engineering tasks than others. 
For example, they appear to be better at front-end development than back-end programming. 

### 1.2.2. Image and video production

The probabilistic nature of AI means that it excels at creative tasks, like image and video generation and editing. 

AI is often used to generate first drafts and prototypes for human experts to iterate upon (perhaps after user testing).

### 1.2.3. Writing

AI excels at writing tasks:
- autocompletion and autocorrection
- email rewriting and improvement
- essay writing and customised book generation
- note-taking
- search engine optimisation

This can have downsides — AI slop. 

### 1.2.4. Education

Education use cases include:
- summarising textbooks
- personslised lecture plans and learning materials
- roleplaying in language learning
- quiz generation 

### 1.2.5. Conversational bots

Conversational bots are highly versatile:
- therapists
- digital companions
- customer support bots and copilots
- smart non-player characters in video games

### 1.2.6. Information aggregation

### 1.2.7. Data organisation

### 1.2.8. Workflow automation

## 1.3. Planning AI applications

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
