# Introduction to Prompts

## Overview
In programmatic interactions with large language models, the prompts have to be very specialized and include context.

## Components of a Prompt
1. **Instructions**: Tell the model what and how to construct the output.
   - **External Information**: Context or additional information for the model, which can be manually inserted into the prompt, retrieved via a vector database, or pulled via other means.
   - **User Input/Query**: Input or question specified by the user.
   - **Output Indicator**: Determines the format of the to-be-generated response. The prompt can mention a meaningful textual structure or a technical structure like JSON, XML, HTML, etc.

## RAG Applications
In RAG applications, the prompts we write have to be generic. The variables passed in the prompt have to be dynamic so they can change based on the question provided by the user.

# Prompt Templates
- **Template Components**: A template may include instructions, few-shot examples, specific context, and questions appropriate for a given task.
- **Frameworks**: Tools like LangChain and LlamaIndex provide tooling to work with and route prompt templates.

# Advanced Prompts

## Chain of Thought (CoT)
- **Definition**: A technique used to guide LLMs through a series of logical steps towards completing complex tasks.

## Self-Consistency
- **Purpose**: Aims to replace the naive greedy decoding used in chain-of-thought prompting.
- **Method**: Sample multiple, diverse reasoning paths through few-shot chain of thought, and use the generations to select the most consistent answer. This helps to boost the performance of chain-of-thought prompting on tasks involving arithmetic and common-sense reasoning.

## Context Window
- **Definition**: The max number of tokens that can be shared between one question and response.
- **Application in RAG**: When building RAG applications, the context window size will also contain the augmented data that we are sending to the model, along with the prompt. So the context + prompt + answer has to fit within the context window.

## Tokenization
- **Definition**: Different models have different context window sizes, measured in terms of **tokens**.
- **Explanation**: Given a piece of text, tokens are the logical chunks of information that the model considers as tokens.

