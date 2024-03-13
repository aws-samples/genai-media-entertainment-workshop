# Question Answering

---
Question answering (QA) is an important task that involves extracting answers to factual queries posed in natural language.
Foundation Models (FMs) like Amazon Titan, Anthropic Claude, and Cohere Command are trained on vast amounts of text. From that training, they develop the probability distributions that can predict next token/word in an answer sequence when given a question.

Despite how good these models have become, they are pronoun to **hallucination**, a phenomenon where a FMs generates false or inaccurate information. In the lab, we will experiment with different techniques to reduce hallucination and improve model response accuracy. 

> **_NOTE:_**  Some of these techniques are core to how enterprises build reliable GenAI knowledge search assistant. They are building blocks for [Retrieval Augmented Generation (RAG)](https://docs.aws.amazon.com/sagemaker/latest/dg/jumpstart-foundation-models-customize-rag.html).

## Interact with Titan Test

1. Select [Text Playground](https://us-west-2.console.aws.amazon.com/bedrock/home?region=us-west-2#/text-playground) from Amazon Bedrock Console.
2. Select **Titan Text G1 - Express** model.

![22-select-titan-text.png](images%2F22-select-titan-text.png)

3. Let's experiment with Titan with a few questions:

Here is a Titan prompt. replace `{question}` with the actual questions below.

> You are a question and answer chatbot. Please answer the following question.
> 
> {question}

- What is a Academy Awards?
- In what year was the first Academy Awards ceremony?
- Who holds the record for the most Oscars won?
- who nominates oscar nominees?

![23-titan-answer-correct.png](images%2F23-titan-answer-correct.png)

## hallucination
So far so good. Now let's try a few question where the model may not answer correctly.

3. Submit following question to Titan.

- What are the “Big Five” awards?
- In what year did ‘Forrest Gump’ win Best Picture?
- In what year was the first Oscar for Best Animated Feature awarded?

As of 02/24/2024, response for `What are the “Big Five” awards?`
> The Big Five awards are the Academy Awards, Emmy Awards, Grammy Awards, Tony Awards, and Pulitzer Prize.
> 
> Correct Answer: Best Picture, Best Director, Best Actor, Best Actress, Best Screenplay (either Original or Adapted)

## Prompt Engineering
4. How do we improve the model response? We can use prompt engineering to force model to say "I don't know" instead of a wrong answer.

Paste the new prompt into the text box and click **Run**

> You are a question and answer chatbot. Please answer the following question. Say "I don't know" if you are not sure.

> What are the “Big Five” awards?

![24-titan-answer-idk.png](images%2F24-titan-answer-idk.png)

## In-Context Learning

5. Now let's help the model answer this question correctly.

Following passage is copied from Wikipedia: [List of Big Five Academy Award winners and nominees](https://en.wikipedia.org/wiki/List_of_Big_Five_Academy_Award_winners_and_nominees). Let's also feed this passage to Titan as context.

> At the Academy Awards, the so-called "Big Five" awards are those for Best Picture, Best Director, Best Actor, Best Actress, and Best Screenplay (either Best Original Screenplay or Best Adapted Screenplay).[1] As of the 94th Academy Awards (2021), a total of 43 films have been nominated in all five of these award categories. Only three films have won all five of these major awards: It Happened One Night (1934), One Flew Over the Cuckoo's Nest (1975), and The Silence of the Lambs (1991). Eight films failed to win any of the five major awards after being nominated.

6. Build a new prompt with the context, and click **Run**

> You are a question and answer chatbot. Please answer the following question only use the context below. Say "I don't know" if you are not sure.
> 
> {context}
> 
> What are the “Big Five” awards?

![25-titan-in-context.png](images%2F25-titan-in-context.png)

> **_NOTE:_** Congratulations! You have successfully completed this lab. 
> Think about how you can turn the prompt into repeatable templates and how we can dynamically retrieve the correct context for the FMs. That is the idea behind a RAG system for knowledge search assistants.

