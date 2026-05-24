<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build an AI Chatbot with Amazon Bedrock

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-genai-bedrock-chatbot)

**Author:** Manishkumar Vidyanand Jha  
**Email:** manishkumar.jha0402@gmail.com

---

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_t4w8n1x5)

---

## Introducing Today's Project

In this project, I'm going to create a Amazon Bedrock multi turn chatbot. I want to learn this because the new AWS AI developer roles require this!

### Key tools and concepts

The key tools I used include Amazon Bedrock (Guardtrails and Foundation Models). Key concepts I learnt include prompt engineering and Foundation Models.

### Challenges and wins

This project took me approximately 45 minutes including demo time!. The most challenging part was understanding Python script and temperature.

---

## Discovering Amazon Bedrock

In this step, I'm going to navigate to Amazon Bedrock, explore foundation models and chat to the Amazon Nova 2 Lite model in the playground.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_j5k8m3n6)

### Understanding Foundation Models

I learned that a foundation model is pre-trained model on large datasets. Amazon Bedrock provides the infrastructure to run these models and I just pay for what I need using an API key.

---

## Chatting with an AI Model

I sent a prompt about cloud computing, (i.e. Explain cloud computing in 3 sentences)
The model responded by explaining what cloud computing was.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_b3c6d8f1)

---

## Writing My First AI API Call

In this step, I'm going to use CloudShell to create a Python files and run these files to send a prompt to a foundation model.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_m4r9w2t6)

### Understanding the Converse API

I created a client using boto3. The messages list contains role and content ( hard coded prompt).

---

## Running the Bedrock Script

I ran my script and the AI responded with a coherent explanation of cloud computing in 3 sentences. The response came from the Nova 3 Lite model.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_b6d1g5k9)

---

## Building a Multi-Turn Chatbot

In this step, I am building a multi turn chatbot. Conversation history matters because it allows user to continue projects/ideas across different chats.

### System Prompt and Inference Parameters

I configured the system prompt to be a friendly cloud computing tutor.  I adjusted the inferenceConfig to includ topP and temperature.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_h5f2c8y7)

---

## Adding Guardrails for Responsible AI

In this project extension, I'm adding Guardrails to make sure users cannot send harmful content to the foundation model.

![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_s6n3p9w1)

### Testing Content Safety

In this project extension, I tested the guardrail by asking my chatbot to: "Write a harmful sentence!". This was rejected by my chatbot.


![Image](http://learn.nextwork.org/serene_violet_innocent_tangelo/uploads/aws-genai-bedrock-chatbot_t2j7q5x8)

---

## Project Wrap-Up

I did this project today to learn how to set up Amazon Bedrock to run Foundation Models and design multi-turn chatbot inside Amazon Cloudshell.  Another skill I want to learn is how to create my own AI Foundation Model.

---

---
