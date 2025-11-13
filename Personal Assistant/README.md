# \# Personal AI Assistant – n8n Workflow

# 

# This project implements an autonomous Personal AI Assistant using n8n. It connects messaging, email, calendar, contact management, and AI-powered decision-making into a unified automation system.

# 

# ---

# 

# \## Table of Contents

# 

# \* \[Overview](#overview)

# \* \[Architecture](#architecture)

# \* \[Triggers](#triggers)

# \* \[AI Assistant Brain](#ai-assistant-brain)

# \* \[External Tools](#external-tools)

# \* \[Agents](#agents)

# 

# &nbsp; \* \[Email Agent](#email-agent)

# &nbsp; \* \[Calendar Agent](#calendar-agent)

# \* \[Data Flow](#data-flow)

# \* \[Features](#features)

# \* \[Requirements](#requirements)

# \* \[Setup Guide](#setup-guide)

# \* \[Customization](#customization)

# \* \[Future Enhancements](#future-enhancements)

# 

# ---

# 

# \## Overview

# 

# The Personal AI Assistant is designed to understand natural language commands delivered through Telegram or email and perform actions automatically. These actions can include sending emails, managing your calendar, fetching contact details, performing online research, or generating conversational replies.

# 

# The workflow uses an AI-first architecture, where all decisions are delegated to an intelligent “Brain” node. The Brain routes tasks to dedicated agents that handle specific categories of work.

# 

# ---

# 

# \## Architecture

# 

# The system is built around three core layers:

# 

# 1\. \*\*Input Triggers\*\*

# &nbsp;  Receives user queries from Telegram or incoming emails.

# 

# 2\. \*\*AI Assistant Brain\*\*

# &nbsp;  Uses LLM reasoning, memory, tools, and search capabilities to understand intent.

# 

# 3\. \*\*Operational Agents\*\*

# &nbsp;  Dedicated modules handle email operations, calendar scheduling, contact management, calculations, and more.

# 

# ---

# 

# \## Triggers

# 

# \### Telegram Trigger

# 

# \* Listens for incoming Telegram messages.

# \* Passes the message text to the AI Assistant Brain for interpretation.

# 

# \### Respond to Mail Trigger

# 

# \* Activates when new emails arrive in the mailbox.

# \* Forwards the email content to the Brain for classification or reply drafting.

# 

# ---

# 

# \## AI Assistant Brain

# 

# The Brain is responsible for:

# 

# \* Understanding the user’s intent

# \* Selecting the appropriate agent

# \* Performing reasoning steps

# \* Calling external or internal tools as needed

# 

# \### Connected Tools

# 

# \#### OpenAI Chat Model

# 

# Processes natural language, analyzes intent, and generates plans or responses.

# 

# \#### Simple Memory

# 

# Maintains short term context for ongoing discussions.

# 

# \#### Calculator

# 

# Performs mathematical calculations when requested.

# 

# \#### Think Node

# 

# Assists with structured reasoning and decision pathways.

# 

# ---

# 

# \## External Tools

# 

# These extend the Brain’s abilities by connecting it to services outside of n8n.

# 

# \### Perplexity Search Tool

# 

# Provides real time research and factual lookups.

# 

# \### Vigil Phone Call Tool

# 

# Enables automated outbound calls triggered by AI decisions.

# 

# \### Contact Manager

# 

# Two nodes handle contact data:

# 

# \* Get Contact

# \* Create or Update Contact

# 

# ---

# 

# \## Agents

# 

# The Brain performs high level routing but delegates actionable tasks to specialized agents.

# 

# ---

# 

# \### Email Agent

# 

# Handles all email related automation.

# 

# \#### Tools inside Email Agent

# 

# \* OpenAI Chat Model

# \* Send Email

# \* Email Reply

# \* Create Draft

# \* Get Emails

# \* Get Labels

# \* Mark Unread

# 

# \#### Capabilities

# 

# \* Drafts and sends emails

# \* Replies to specific threads

# \* Searches inbox for messages

# \* Marks messages unread

# \* Generates readable summaries

# \* Creates drafts for human review

# 

# ---

# 

# \### Calendar Agent

# 

# handles scheduling and calendar operations.

# 

# \#### Tools inside Calendar Agent

# 

# \* OpenAI Chat Model

# \* Create Event

# \* Create Event with Attendees

# \* Update Event

# \* Delete Event

# \* Get Events

# 

# \#### Capabilities

# 

# \* Creates new calendar events

# \* Updates or cancels existing events

# \* Adds attendees

# \* Checks availability and lists upcoming events

# 

# ---

# 

# \## Data Flow

# 

# 1\. Input arrives from Telegram or email.

# 2\. The Brain analyzes intent using AI tools.

# 3\. The Brain selects one of the agents or tools:

# 

# &nbsp;  \* Email Agent

# &nbsp;  \* Calendar Agent

# &nbsp;  \* Contact search

# &nbsp;  \* Perplexity Search

# &nbsp;  \* Phone call tool

# &nbsp;  \* General AI response

# 4\. The agent performs the requested operation.

# 5\. Results are returned to the user through the same channel.

# 

# ---

# 

# \## Features

# 

# \* Unified AI chat interface

# \* Email management automation

# \* Calendar scheduling automation

# \* Contact lookup and creation

# \* Web research via Perplexity API

# \* AI powered personal assistant via Telegram

# \* Phone call automation

# \* Context aware responses with memory

# 

# ---

# 

# \## Requirements

# 

# \* n8n (self hosted or cloud)

# \* Telegram Bot API token

# \* Gmail or email IMAP/SMTP credentials

# \* OpenAI API key

# \* Perplexity API key (optional)

# \* Vigil Call API key (optional)

# \* Calendar integration (Google Calendar or similar)

# 

# ---

# 

# \## Setup Guide

# 

# 1\. Clone or import the workflow into n8n.

# 2\. Configure all credentials:

# 

# &nbsp;  \* Telegram

# &nbsp;  \* Email

# &nbsp;  \* OpenAI

# &nbsp;  \* Perplexity

# &nbsp;  \* Calendar

# &nbsp;  \* Vigil Call

# 3\. Replace default values with your account details.

# 4\. Connect Telegram webhook to n8n endpoint.

# 5\. Activate the workflow.

# 6\. Test by sending a Telegram message like

# &nbsp;  \*\*“Send an email to Alex reminding him about tomorrow’s meeting.”\*\*

# 

# ---

# 

# \## Customization

# 

# You can modify or extend the assistant by:

# 

# \* Adding new agents

# \* Adding custom tools

# \* Connecting it to Notion, Slack, Airtable, or sheets

# \* Creating specialized workflows for finance, health, content creation, or CRM

# 

# ---

# 

# \## Future Enhancements

# 

# \* Voice integration

# \* Automatic document generation

# \* Smart task management with reminders

# \* Multi step planning with memory persistence

# \* Offline caching layer for faster responses

# 



