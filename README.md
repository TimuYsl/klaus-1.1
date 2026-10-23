# Klaus

Klaus is a lightweight Discord bot that replies when mentioned using an AI model exposed through the Pollinations API. It is designed to feel like a casual Discord user: brief, dry, conversational, and in-character rather than formal or verbose.

## Features

- Responds when the bot is mentioned in a Discord channel or DM
- Uses referenced messages as reply context
- Pulls recent channel conversation for short background context
- Connects to an OpenAI-compatible API endpoint
- Supports custom system prompts and model selection
- Handles rate limits with a simple retry flow
- Splits long messages to fit Discord’s 2000-character limit

## How it works

The application does the following:

1. Reads configuration from environment variables
2. Connects to Discord with a bot token
3. Watches for messages that mention the bot
4. Builds a compact prompt from the current message and recent chat context
5. Sends the request to the configured Pollinations endpoint
6. Replies back to Discord with the generated text

## Requirements

- Go 1.24.4 or newer
- A Discord bot token
- Access to a Pollinations-compatible endpoint

## Configuration

Set these environment variables before starting the bot:

```bash
export KLAUS_DISCORD_BOT_TOKEN="your_discord_bot_token"
export KLAUS_POLLINATIONS_API_KEY="your_optional_api_key"
export KLAUS_POLLINATIONS_MODEL="openai"
export KLAUS_POLLINATIONS_URL="https://text.pollinations.ai/openai"
export KLAUS_SYSTEM_PROMPT="You are Klaus, a regular user on this Discord server and not a formal AI assistant. Keep your replies extremely short, dry, and casual in a typical Discord chat style."
```