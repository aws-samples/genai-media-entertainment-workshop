# Generative AI Media Entertainment Workshop on AWS

## Introduction
This github repository contains the content for a workshop intended for customers in Media and Entertainment industry who are interested to learn about  Generative AI and its capabilities through hands on experience.

At a high level, this repository contains workshop training material focused on the following topics:

* [Amazon PartyRock](https://partyrock.aws/)
* Prompt Engineering techniques using [Amazon Bedrock](https://aws.amazon.com/bedrock/)
* Generative AI Knowledge Search Assistant with 
  * [Amazon Q for Business](https://aws.amazon.com/q/business-expert/)
  * [Knowledge Bases for Bedrock](https://aws.amazon.com/bedrock/knowledge-bases/)
  * [SageMaker Jumpstart](https://aws.amazon.com/sagemaker/jumpstart/)
  
* Avatar generation: Learn how to generate avatar images using text prompts.
* Rotoscoping and Inpainting: Rotoscoping is an animation technique that animators use to trace over motion picture footage, frame by frame, to produce realistic action. Inpainting is a conservation process where damaged, deteriorated, or missing parts of an artwork are filled in to present a complete image.
* Text to animation: Generate a video based on a text description

Expected duration: 4 hours

Level: 100-200

Within this series of labs, you'll explore some of the most common usage patterns we are seeing with our customers in Media and Entertainment industry for Generative AI. This is achieved by leveraging foundation models using AWS native services to help in text generation tasks, ranging from composing emails, summarizing text, answering questions to building chatbots, and creating images. You will gain hands-on experience implementing these patterns via Amazon Q for Business, Bedrock APIs and SDKs, SageMaker Jumpstart as well as vector database such as [Amazon OpenSearch Serverless](https://aws.amazon.com/opensearch-service/features/serverless/) and open-source software like [LangChain](https://python.langchain.com/docs/get_started/introduction).


Please refer to this [Step-by-step guided instructions on the workshop website](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US) for working through the labs.


## Getting started
Follow the detailed instruction [here](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/1-create-workspace-environment) to setup your AWS environment.

## Content
This repository contains notebook examples and instructions for the workshop. More detail can be found in the following:

### Amazon PartyRock
Please refer to this workshop [link](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/2-partyrock) for detail.

### Prompt Engineering With Amazon Bedrock
Please refer to this workshop [link](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/3-0-prompt-engineering-bedrock) for detail.


### Use Case 1 - M&E Assistant
- [Amazon Q for Business](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/4-usecase-1-media-entertainment-assistant/with-amazonq)
- [Knowledge Bases for Bedrock](./bedrock/kb_bedrock.ipynb): This notebook demonstrates how to build a RAG application using Knowledge bases for Bedrock.
- [Amazon SageMaker Jumpstart](./sagemaker/sagemaker-llm-rag.ipynb): This notebook demonstrates how to leverage open source LLMs such as Llama2 model to build a RAG application.


### Use Case 2 - Generate Avatar based on image
Pleae refer to this workshop [link](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/5-usecase-2-generate-avatar-based-on-image) for more detail.

### Use Case 3 - Inpainting / Roboscoping 
Pleae refer to this workshop [link](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/6-usecase-3-rotoscoping-replace-character-with-animated-one-in-video) for more detail.

### Use Case 4 - Text to Animation
Please refer to this workshop [link](https://catalog.us-east-1.prod.workshops.aws/workshops/c10312f0-aa83-4ba5-b908-599d80a75179/en-US/7-usecase-4-text-to-animation) for more detail.