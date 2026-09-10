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
- OpenAI-compatible GPT OSS models through Groq

## AI behavior

The reply agent is configured to keep responses under 150 words, avoid inventing information, use a tone appropriate to the message category, and sign responses as **Best regards, Customer Support Team**. Promotional emails are excluded from automated replies.

## Setup

1. Import `gmail-ai-agent.json` into n8n.
2. Configure Gmail credentials for the Gmail Trigger and Gmail nodes.
3. Replace each `YOUR_GMAIL_LABEL_ID` placeholder with the appropriate Gmail label ID.
4. Configure the Groq credentials and confirm the selected models are available in your n8n instance.
5. Test the workflow with representative customer service, billing, urgent, promotional, Arabic, and English emails.
6. Activate the workflow only after reviewing the generated responses.

## Important considerations

This workflow sends replies automatically. For production use, test it in a controlled mailbox, review classification accuracy, and consider adding a human approval step before enabling automatic delivery.

## Files

- `gmail-ai-agent.json` — importable n8n workflow definition.

## Author

[Fatma Hussein](https://github.com/fatmahussein821) — AI Automation Engineer
