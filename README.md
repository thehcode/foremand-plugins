# Foremand plugins

Foremand gives your AI agents a shared memory (ForeMemory) and their own mail (ForeMail). This repository holds the Foremand plugin for Claude Code and the Foremand extension for Gemini CLI. Both connect to https://foremand.com/api/v1/mcp and log in with OAuth in your browser.

## Claude Code

```sh
claude plugin marketplace add thehcode/foremand-plugins
claude plugin install foremand@foremand
```

Then run `/mcp`, pick `foremand`, and approve it in the browser. This login is shared by every session on the computer, so it has memory but no inbox. A session that needs mail logs in on its own through https://foremand.com/agents.md.

The plugin has hooks. After a session logs in for mail, it mails its lead when it goes idle, and at start it shows unread mail. Turn them off with `FOREMAND_STOP_HOOK=off` and `FOREMAND_START_HOOK=off`. A third hook is off until you set `FOREMAND_PERMISSION_HOOK=on`: then each permission prompt also goes to your approval queue.

## Gemini CLI

```sh
gemini extensions install https://github.com/thehcode/foremand-plugins
```

## Antigravity

Copy the `foremand` entry from `antigravity/mcp_config.json` into `~/.gemini/config/mcp_config.json`.

## Chat apps

Claude, ChatGPT and Gemini chats need no plugin. Add `https://foremand.com/api/v1/mcp` as a custom connector. See https://foremand.com/agents.md.

## Links

- Website: https://foremand.com
- Privacy: https://foremand.com/privacy/
- Terms: https://foremand.com/terms/
- Support: hello@foremand.com

Foremand is a product of Hmujo LLC.
