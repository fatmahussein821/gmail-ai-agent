# Gmail AI Agent

An n8n workflow that turns an inbox into an intelligent first-response system. It monitors incoming Gmail messages, classifies them by business intent, applies the matching Gmail label, and generates concise replies for actionable conversations.

## What it does

- Monitors Gmail for new messages every minute.
- Classifies emails into **customer service**, **finance/billing**, **high priority**, or **promotion**.
- Applies a corresponding Gmail label to each message.
- Generates professional replies for customer service, billing, and urgent messages.
- Skips promotional emails instead of replying to them.
- Replies in the same language as the incoming email, including Arabic and English.
- Sends the generated response as a Gmail reply.

## Workflow

`Gmail Trigger → Text Classifier → Gmail Label → AI Reply Agent → Send Gmail Reply`

Promotional messages are labeled but intentionally do not proceed to the reply step.

## Integrations

- n8n
- Gmail
- Groq Chat Model

## AI behavior

The reply agent is configured to keep responses under 150 words, avoid inventing information, use a tone appropriate to the message category, and sign responses as **Best regards, Customer Support Team**. Promotional emails are excluded from automated replies.

