# Chapter 1. Introduction to building AI applications with foundation models

Post-2020, AI has been all about **scale**, with two major consequences:
- AI models are becoming more powerful, capable of more tasks, and enabling more applications.
- Few organisations can afford to train an LLM, leading to the emergence of **model-as-a-service**.

Demand for AI has increased as the barriers to entry have decreased, leading to the rise of <mark>AI engineering</mark> — the job of building applications on top of readily available AI models.

## 1.1. The rise of AI engineering

### 1.1.1. From language models to large language models

#### Language models

There are two main types of language model:
- **masked** language models — trained to predict missing words anywhere in a sequence 
- **autoregressive** language models — trained to predict the next word in a sequence.

Masked language models (eg. BERT — bidirectional encoder representations from transformers) are commonly used for non-generative tasks like sentiment analysis and text classification, or code debugging.

Autoregressive language models are the models of choice for text generation. These models are the most widely used, since many different kinds of task can be framed as ‘completion tasks’ — translation, summarisation, coding, solving maths problems, spam classification, etc.

#### Self-supervision

Language models are particularly scalable because they can be trained using self-supervised learning. The output labels needed for supervised learning do not need to be added (expensively and time-consumingly) by a human, but rather are inferred directly from the training corpus (the ‘next word’).

### 1.1.2. From large language models to foundation models

**Multimodal models** add additional data modalities to an LLM — images, audio, videos, 3D assets, protein structures, etc.

**Foundation models** are general-purpose models capable of many different tasks.

Some AI engineering techniques for adapting a foundation model to a new task are:
- **prompt engineering** — craft detailed instructions with examples of the desired output (one-shot or few-shot prompting)
- **retrieval-augmented generation** (RAG) — supplement the instructions with a database
- **fine-tuning** — further train the model’s parameters on a more specific dataset.

### 1.1.3. From foundation models to AI engineering



## 1.2. Foundation model use cases

### 1.2.1. Coding

### 1.2.2. Image and video production

### 1.2.3. Writing


### 1.2.4. Education


### 1.2.5. Conversational bots

### 1.2.6. Information aggregation

### 1.2.7. Data organisation

### 1.2.8. Workflow automation

## 1.3. Planning AI applications

## 1.4. The emerging AI stack


---

Back up to: [Huyen (2025)](index.md) | [Maglocvnus](../../index.md)
