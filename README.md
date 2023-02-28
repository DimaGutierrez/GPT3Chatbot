# Build ChatGPT from GPT-3

## Introduction
ChatGPT has blown up in the past month, gaining a million users in just a week. Surprisingly, the underlying model, GPT-3 debuted in 2020 and was released for public access over a year ago!

For those who don't know, ChatGPT is a new language model from OpenAI that was finetuned from GPT-3 to be optimized for conversation1. It has a user-friendly chat interface, where you can give input and get a response from an AI assistant. Check it out at chat.openai.com.

While the early versions of GPT-3 weren't as advanced as the current GPT-3.5 series, they were still impressive. These models have been available through an API and a playground web UI interface that lets you tune certain configuration hyperparameters and test prompts. GPT-3 gained significant traction, but it did not approach the virality of ChatGPT.

What makes ChatGPT so successful, compared to GPT-3, is it's accessibility as a straightforward AI assistant for the average person, regardless of their knowledge of data science, language models, or AI.
[GPT3Chatbot.py](https://gist.github.com/DimaGutierrez)
## The Prompt
Prompting is the process of instructing an AI to do something. As you have probably seen in ChatGPT examples online, you can prompt it to do just about anything. Common use cases are summarizing text, writing content based on a description, or creating things like poems, recipes, and much more.
ChatGPT is both a language model and user interface. The prompt input by a user to the interface is actually inserted into a larger prompt that contains the entire conversation between the user and ChatGPT. This allows the underlying language model to understand the context of the conversation and respond appropriately.

GPT-3 is able to 'learn' from a simple instruction or a few examples in the prompt. The latter is called few-shot, or in context learning3. In the chatbot prompt above, I create a fictitious chatbot named Skippy, and instruct it to provide responses to users. GPT-3 picks up on the back-and-forth format, USER: {user input} and SKIPPY: {skippy response}. GPT-3 understands that Skippy is a chatbot and the previous exchanges are a conversation, so that when we provide the next user input, "Skippy" will respond.
[chatbotPromptV1.py](https://gist.github.com/DimaGutierrez)
## Memorization
Past exchanges between Skippy and the user get appended to the next prompt. Each time we give more user input and get more chatbot output, the prompt expands to incorporate this new exchange. This is how chatbots like Skippy and ChatGPT can remember previous inputs. There is a limit, however, to how much a GPT-3 chatbot can remember.
  
Prompts can get massive after several exchanges, especially if we are using the chatbot to generate long responses like blog posts. Prompts sent to GPT-3 are converted into tokens, which are individual words or parts of them. **There is a limit of 4097 tokens (about 3000 words)** for the combined prompt and generated response for GPT-3 models, including ChatGPT.
      
