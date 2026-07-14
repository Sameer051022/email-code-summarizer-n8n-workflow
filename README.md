# Email Code Summarizer (n8n Workflow)

An automated n8n workflow that watches a Gmail inbox for incoming emails containing code, uses OpenAI to analyze that code, and emails back a combined summary with inline comments, all without manual intervention.

## Overview

This workflow is designed for developers and teams who want a quick, automated way to understand and document code snippets sent over email. When triggered, it pulls the code from an incoming message, runs it through two parallel AI analysis steps, merges the results, and sends the final report back to the recipient as a reply email.

## How It Works

1. Gmail Trigger: Watches a Gmail inbox and fires when a new email containing code arrives.
2. Conditional Check (If node): Validates the incoming email and content before processing.
3. Parallel AI Processing: A Code Summary chain generates a concise summary of what the code does, while a Comments Addition chain generates line by line comments for the code.
4. Merge: Combines the two parallel outputs, summary and comments, into a single data stream.
5. Aggregate: Consolidates the merged items into one unified payload.
6. Edit Fields: Concatenates and formats the final text for readability.
7. Basic LLM Chain: Performs a final pass over the combined content to polish the output.
8. Send Email: Delivers the finished summary and commented code back to the user via Gmail.

## Tech Stack

n8n for workflow automation, Gmail for the email trigger and delivery, and OpenAI for LLM powered code summarization and comment generation.

## Prerequisites

A running n8n instance (self-hosted or cloud), a Gmail account connected via OAuth2 credentials in n8n, and an OpenAI API key configured as a credential in n8n.

## Setup

First, import the workflow JSON into your n8n instance (workflow file to be added). Next, configure your Gmail Trigger node with valid Gmail OAuth2 credentials, and configure the OpenAI Chat Model nodes with your OpenAI API key. Then activate the workflow. Finally, send a test email containing a code snippet to the connected Gmail account and check your inbox for the automated summary reply.

## Project Status

This repository currently contains project documentation only. The workflow export file and any supporting assets will be added soon.

## License

To be determined.
