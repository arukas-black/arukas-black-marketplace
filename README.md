<p align="center"><img src="plugins/mimic/assets/logo-v2.png" alt="Arukas Black" width="100"></p>

<h1 align="center">Arukas Black Marketplace</h1>
<p align="center">Tools for your AI workspace. Starting with Mimic.</p>

## Install Mimic in Claude

1. Open **Customize → Plugins → Add → Add marketplace**.
2. Enter this repository URL:

   **https://github.com/arukas-black/arukas-black-marketplace**

3. Add **Mimic**, open its **Connectors** tab, then connect and sign in.

An organization administrator may need to allow the marketplace or connector.
Installation and sign-in are separate steps; the plugin contains no shared credentials.

### Claude Code

```sh
claude plugin marketplace add arukas-black/arukas-black-marketplace
claude plugin install mimic@arukas-black-marketplace
```

## Mimic

**Memory across AI conversations.** Save and find notes, decisions and text files
in your own workspace. Ask a question, use keywords or skim for orientation.
Source details are available separately, keeping ordinary results readable.

Mimic provides eight tools: **Find, Remember, Upload, Metadata, Identity,
Handbook, Activity and Feedback**.

### Sign in and activate

- Use your own email and enter the email code only on the sign-in page.
- The operator activates your workspace. Before activation, only Identity and
  Handbook are available. A new account starts with empty memory.
- During this pilot, email-code delivery is limited to enabled, verified test
  recipients. Contact the person who invited you to arrange access.
- Enable Mimic in a conversation, then ask: **“Use Mimic Identity to show my
  workspace status. Do not save anything.”**

### Automatic memory

The included [Using Mimic skill](plugins/mimic/skills/using-mimic/SKILL.md)
retains the existing automatic memory workflow. With your authorization, Claude
can save meaningful notes without asking for each save and recall relevant notes
across chats to inform answers and work. Saved notes are sent to your hosted
Mimic workspace. Review the skill and privacy policy before enabling it; exclude
passwords and secrets. Your current instructions and permissions remain authoritative.

This is an independently distributed marketplace, not an Anthropic directory
approval. Clarification of the automatic workflow's directory eligibility is pending.

## Updates

In Claude Code, run:

```sh
claude plugin update mimic@arukas-black-marketplace
```

Automatic updates depend on your marketplace settings. The plugin name remains
`mimic`; the catalog name is `arukas-black-marketplace`.

## Links

[About](https://mcp.arukas.black/mimic/about) ·
[Privacy](https://mcp.arukas.black/mimic/privacy) ·
[Terms](https://mcp.arukas.black/mimic/terms) ·
[Support](https://mcp.arukas.black/mimic/support)

This repository contains the client plugin, usage guidance and brand assets.
Service implementation, account data and memory contents are not distributed.
Plugin licensing: [LICENSE](plugins/mimic/LICENSE).
