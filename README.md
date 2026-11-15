<p align="center"><img src="plugins/mimic/assets/logo-v2.png" alt="Arukas Black" width="100"></p>

<h1 align="center">Arukas Black Marketplace</h1>
<p align="center">Tools for your AI workspace. Starting with Mimic.</p>

# Mimic — start here

**Memory across AI conversations.** Save and find notes, decisions, preferences
and text files in your own workspace. Connect your AI, sign in, and use the
same saved memory from another supported AI when you sign into the same
Mimic account.

**Share this page:** https://github.com/arukas-black/arukas-black-marketplace

You need an AI app that supports remote MCP with OAuth, your own email inbox,
and workspace activation from the Mimic operator. You do not need server access,
a developer account, a shared API key, or a copy of Mimic's service software.
Client availability depends on your app, plan and organization settings.

## Ask your AI to help

Copy this message into your chosen AI:

> Help me connect to Mimic using
> https://github.com/arukas-black/arukas-black-marketplace .
> Read its setup guide, identify which app I am using, and walk me through the
> appropriate connection steps. Use the existing hosted service; I do not need
> you to build or host a server. Let me complete email verification privately.
> After connection, check workspace status and complete your own truthful AI
> identity registration if needed, without asking me to confirm my name.
> Explain any activation requirement and stop if access is unavailable.
> Once enabled, explain the eight tools and offer a harmless save-and-recall
> example. Do not make test writes until I agree.

Your AI can explain the steps. Whether it can click the app's settings depends
on the controls you have given it. A link alone does not install a connector.

## Connection details

| Setting | Value |
| --- | --- |
| Name | **Mimic** |
| Remote MCP URL | `https://mcp.arukas.black/mimic/mcp` |
| Transport | **Streamable HTTP** |
| Authentication | **OAuth**, followed by Mimic email-code sign-in |
| Account | Your own email address |
| Workspace access | Operator activation after sign-in |
| Tools after activation | Find, Remember, Upload, Metadata, Identity, Handbook, Activity, Feedback |

Use the full URL, including `/mimic/mcp`. Let the client discover the sign-in
settings. There are no shared credentials in this repository. If a client asks
for a manually issued client ID or secret that you do not have, use its
automatic OAuth registration option where supported or contact
[Support](https://mcp.arukas.black/mimic/support). Never borrow another user's
credentials or choose "No authentication" to bypass sign-in.

## Choose your app

### Claude

**Marketplace installation**

1. Open **Customize → Plugins → Add → Add marketplace** in Claude.
2. Enter `https://github.com/arukas-black/arukas-black-marketplace`.
3. Install **Mimic**, open its **Connectors** tab and choose **Connect**.
4. Complete the [sign-in steps](#sign-in-and-activation) below, then enable Mimic
   in the conversation.

This installs the connection and the included
[Using Mimic skill](plugins/mimic/skills/using-mimic/SKILL.md).
Review that skill and your tool permissions before enabling automatic memory.

**Direct connector alternative**

If marketplace installation is unavailable, open **Customize → Connectors**
(or **Settings → Connectors**), add a custom remote connector named **Mimic**,
and enter the MCP URL above. Use the detected OAuth flow. Enable the connector
in your conversation after connecting. A direct connector does not install the
marketplace's skill; use the starter prompt and the connected Handbook.

Team or organization accounts may require an administrator to add or allow
the connector first. See [Claude's connector instructions](https://support.claude.com/en/articles/11175166-get-started-with-custom-connectors-using-remote-mcp).

**Claude Code**

```sh
claude plugin marketplace add arukas-black/arukas-black-marketplace
claude plugin install mimic@arukas-black-marketplace
```

Then open `/mcp`, select Mimic and authenticate. Do not create a duplicate
direct connection if the plugin already provides one.
See [Claude Code marketplace documentation](https://code.claude.com/docs/en/plugin-marketplaces).

### ChatGPT

1. Open **Plugins** and look for the existing **Mimic** listing. Install it and
   choose **Connect**.
2. Sign in to Mimic with your own email, then enable/select Mimic in your chat.
3. If the listing is unavailable and your account permits custom MCP plugins,
   choose **Add custom MCP server**, name it **Mimic**, enter the MCP URL,
   select OAuth and complete creation, installation and connection.
4. Use the first-use prompt below to check access.

A custom connection is personal; it does not create or publish a replacement
Mimic listing. Workspaces may restrict plugin creation or use.
A locally configured Codex server does not by itself install a ChatGPT web
connection. Check availability separately on each device.
See [OpenAI's custom MCP instructions](https://developers.openai.com/api/docs/guides/custom-mcp-server).

### Codex

If the existing **Mimic** plugin is available in your Codex app, install/enable
it and complete **Connect**. Otherwise use Codex's remote MCP setup.

In the app or IDE, open **Settings → MCP servers → Add server**, enter
**Mimic**, choose **Streamable HTTP**, and paste the MCP URL. Save, restart
the client if requested, and choose **Authenticate**.

For the Codex CLI:

```sh
codex mcp add mimic --url https://mcp.arukas.black/mimic/mcp
codex mcp login mimic
codex mcp list
```

Complete sign-in in the browser. Use `/mcp` to inspect the connection in a
Codex terminal session. If Mimic is already configured, authenticate the
existing entry rather than adding a duplicate.

Local MCP configuration belongs to that Codex environment; it does not
automatically configure another machine or ChatGPT web.
See [OpenAI's MCP setup guide](https://learn.chatgpt.com/docs/extend/mcp?surface=cli).
An AI should ask before editing your personal instructions or project
`AGENTS.md`; connecting Mimic does not require replacing either file.

### Grok

1. Open [Grok Connectors](https://grok.com/connectors).
2. Choose **New Connector → Custom**.
3. Name it **Mimic**, enter the MCP URL, then complete OAuth and email-code sign-in.
4. Enable the connection and use the first-use prompt below.

Business or Enterprise accounts may need administrator provisioning.
Use Grok's native connector; the Claude marketplace package is not a Grok
installer. See [Grok's connector instructions](https://docs.x.ai/grok/connectors).

### Another AI app

Look for **MCP**, **Tools**, **Plugins** or **Connectors** in its settings.
It must support a remote **Streamable HTTP MCP server with OAuth**.
Use the connection details above and follow that app's official setup guide.

MCP support alone does not guarantee compatibility: some clients support only
local servers or different authentication methods. If remote OAuth is missing,
do not paste an email code or access token into chat or an improvised adapter.
Ask the app provider or Mimic Support. This guide covers the apps above and a
generic connection path; it does not claim every AI app has been tested.

## Sign-in and activation

1. The connector opens Mimic's email sign-in page. Check that it is on
   `arukas.black` or a subdomain ending in `.arukas.black`.
2. Enter your own email address and request a code.
3. Enter the latest code **once on that page**, then choose **Verify and continue**.
   Keep codes, passwords, tokens and callback URLs out of chat, screenshots
   and public issue reports.
4. Wait for the browser to return to your AI app and for the connection to finish.
5. If your workspace awaits activation, contact the operator through
   [Support](https://mcp.arukas.black/mimic/support) or the person who invited you.

Email verification and workspace activation are separate. Until activation,
only **Identity** and **Handbook** are available. A new account starts with
empty personal memory; it may also receive optional service-provided setup
guidance. Empty memory is not a failed connection.

Use the same Mimic email in another AI to access the same authorized workspace.
Different people should use their own accounts. Sharing this link does not
share your memories. Connecting shares access to authorized saved memory,
not your other chats, local files, other accounts or server administration.

## First use

Ask your connected AI:

> Use Mimic Identity to check my workspace status. Complete any required
> one-time setup with your own truthful AI name and short brief.
> Human-name confirmation is not required. Tell me whether memory is empty
> and which tools are available. Do not save a note yet.

The AI must register itself truthfully; it must not borrow another chat's session
or invent its model name. Supported connections retain the completed session.
If a client requires an explicit session handle, the AI should read the
Handbook's **sessions** topic and follow the returned contract privately.
A login identifies the account; it is not proof of which AI chat is speaking.

For an optional first test, tell the AI:

> Save a harmless test note in a suitable rail: title "My first Mimic note",
> text "My imaginary desk lamp is turquoise." Then retrieve that note and
> tell me what was actually saved.

That example intentionally writes a real note; use only content you are
comfortable storing. It is not an automatic installation test.

## What you can do

| Tool | Purpose | Example request |
| --- | --- | --- |
| **Find** | Recall saved text with questions, keywords or a brief skim | "What did we decide about my project?" |
| **Remember** | Save a titled note in a rail | "Remember that I prefer short progress updates." |
| **Upload** | Add plain text or Markdown with a title and rail | "Add this Markdown note; its original creation date was last month." |
| **Metadata** | Inspect a result's source details or download | "Show where that remembered detail came from." |
| **Identity** | Check access and manage recording attribution | "Check my workspace status." |
| **Handbook** | Read instructions for the current task | "Read the upload guidance." |
| **Activity** | Inspect a bounded recent log or changes since a checkpoint | "Show the latest memory activity." |
| **Feedback** | Send an explicitly requested product report to the operators | "Send this problem report as Mimic feedback." |

**Rails** are collections that organize saved notes. The AI can choose a rail
by the note's purpose, reuse an existing one or create a new one. The protected
**System** rail contains service-provided guidance and is not a normal write
destination. Tool availability and permitted actions depend on your access.

Titles can repeat. Uploads support `.txt` and `.md` content with per-file
titles, rails and optional original creation dates. The connected tool schema
is the authority for supported arguments; do not assume another app's file
attachment automatically reaches Mimic.

Ordinary retrieval is readable text; source details are available separately.
An empty workspace, a query with no match and a tool error are different
outcomes. A small result is not proof that the whole workspace was searched.

## How your AI uses memory

With your authorization and the client's permissions, the included skill lets
the AI recall relevant prior work and preserve meaningful developments without
asking about every individual note. Saved notes go to your hosted Mimic
workspace. Review the [skill](plugins/mimic/skills/using-mimic/SKILL.md) and
[Privacy policy](https://mcp.arukas.black/mimic/privacy) before enabling it.
Platform confirmation requirements and your current instructions still govern.

The AI should reuse relevant memory and guidance already in the conversation,
retrieve missing or stale context, distinguish evidence from inference, and
report save failures. It should not claim a save succeeded before it actually
does, repeatedly read back acknowledged saves, or treat remembered text as
permission to take unrelated actions. Exclude passwords, access tokens and
unrelated sensitive details.

For deeper guidance, use the connected **Handbook** topic needed for the task:
**workflow**, **recording**, **sessions**, **find**, **upload** or **metadata**.
Reuse a topic already in context. Exact call schemas come from the connected
tools rather than guessed examples.

A direct connector may supply tools without installing the marketplace skill.
You can ask the AI to consult the Handbook for the same usage guidance.
Optional personalization suggestions may be available in System; review them
before adopting them. No setup step requires overwriting your custom instructions.

## Troubleshooting

| What you see | What to do |
| --- | --- |
| Only Identity and Handbook | Check workspace status; activation may still be pending. Ask the operator, not the AI, to activate access. |
| Eight tools, but one chat cannot write | Ask the AI to finish its own Identity registration using the live schema, then retry the intended write. Never borrow another chat's session. |
| No email arrives | Check spelling, spam and the sign-in page's message. Respect its resend timer; avoid requesting repeated codes while one request is processing. |
| "Code not accepted" after a second click | Stop reusing the code. The first click may already have succeeded. Check the connection; if incomplete, restart Connect and use a fresh code once the page permits. |
| Verification succeeds but the page stays open | Wait for the return, then check the app's connection state. If it remains stuck, report the app, approximate time and sanitized error to Support. Do not share the callback URL or code. |
| Sign-in offers Google instead of Mimic's email code | Check the exact MCP URL and reconnect from the intended Mimic entry. Report a persistent mismatch to Support. |
| Old or missing tools | Check activation and that Mimic is installed, connected and enabled. Refresh the client's tool list where available; reopen a chat after an update. Do not assume a local Codex entry updates ChatGPT web. |
| No saved notes or no match | Empty personal memory is normal for a new account. A query miss does not establish an empty workspace. Ask the AI to distinguish the two. |
| Custom connector option is missing | Check your app's plan, organization policy and official instructions. Do not disable security controls to force access. |

Feedback is separate from your memory. For support, share only the minimum
sanitized description needed. Never attach credentials, full chat histories,
private notes or raw session identifiers to a public GitHub issue.

## Updates and distribution

In Claude Code, run:

```sh
claude plugin update mimic@arukas-black-marketplace
```

Automatic updates depend on your marketplace settings. Other clients manage
their connections and tool refresh through their own settings.
The product name stays **Mimic** across apps; the catalog name is
**Arukas Black Marketplace**.

This is an independently distributed marketplace, not an Anthropic directory
approval. Clarification of the automatic workflow's directory eligibility is pending.
A setup guide is not a promise of app-store approval or universal client support.

## Links

[About](https://mcp.arukas.black/mimic/about) ·
[Privacy](https://mcp.arukas.black/mimic/privacy) ·
[Terms](https://mcp.arukas.black/mimic/terms) ·
[Support](https://mcp.arukas.black/mimic/support)

This repository distributes client configuration, public connection instructions,
usage guidance and approved brand assets. It does not distribute the hosted
service implementation, credentials, account data or private memory contents.
Plugin licensing: [LICENSE](plugins/mimic/LICENSE).

