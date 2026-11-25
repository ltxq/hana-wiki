# Custom Roleplay NPCs

`/npc` is a server roleplay character management system powered by Discord Webhooks. Characters respond with their own designated name and avatar, creating an authentic in-character immersion.

---

## Key Highlights

- **Webhook Representation**: Every reply is sent through a custom Discord Webhook featuring the NPC's specific avatar and name.
- **Easy 3-Field Creation (`/npc create`)**: Simply provide the character's Name, Personality/System Prompt, and an Opening Greeting. The bot automatically provisions the webhook and posts the opening line.
- **Natural Interaction**: Server members can interact with NPCs either by **Replying directly** to an NPC message or by **Mentioning the character's name** in the channel.
- **Real Conversation Memory**: Each character remembers up to 12 turns of your conversation (kept separately per character and per user), so it can hold a thread instead of forgetting every reply.
- **Your Choice of Model**: Pick between Gemini, OpenRouter (including DeepSeek, GPT, Claude), or specify your own provider and model.
- **Isolated Quota**: Supports user or server-level API keys (Gemini / OpenRouter) with key rotation, preventing bot host quota exhaustion.
- **Decoupled from Hana**: Hana remains a cheerful high-school student chatting in `/setroomai` rooms without role confusion.

---

## Command Reference (`/npc`)

| Subcommand | Description | Required Permissions |
| :--- | :--- | :--- |
| `/npc create` | Opens a modal to create a new NPC in the current channel | Server Members / Configured |
| `/npc list` | Displays all active NPCs in the server with IDs and channels | Everyone |
| `/npc move` | Relocates an NPC to a specific channel (or all channels) | NPC Owner / Admins |
| `/npc edit` | Edits an NPC's name, personality prompt, or avatar | NPC Owner / Admins |
| `/npc delete` | Deletes an NPC and cleanly cleans up its Discord Webhook | NPC Owner / Admins |

---

## How to Create an NPC (`/npc create`)

1. Type `/npc create` in the channel where you want the character to reside.
2. Complete the 3-field modal form:
   - **NPC Name**: The display name for the character (e.g. `Yami`, `Sensei Aiko`, `Knight Arthur`).
   - **Personality / Prompt**: Role, background, personality traits, speech tone, and behavior boundaries.
   - **Opening Greeting**: The debut message the NPC posts into the channel upon creation.
3. *(Optional)* Upload an avatar image file or provide an avatar image URL.
4. Submit the form. The bot will configure the channel webhook and post the greeting immediately!

---

## How to Interact with NPCs

Members can chat with NPCs using two convenient methods:

### 1. Direct Reply
Click **Reply** on any message sent by the NPC and type your response. The bot fetches recent dialogue context and generates a contextual reply from that character.

### 2. Mention by Name
Mention the character's exact name anywhere in your channel message, for example:
```text
Hello Yami, did you finish the math assignment yet?
```
The matching NPC assigned to that channel will respond in-character.

---

## Managing Your NPCs

### Listing Server NPCs (`/npc list`)
Run `/npc list` to view an embed listing all server NPCs:
- Character ID (used as an argument for edit/move/delete)
- Display Name
- Assigned Channel
- Creator / Owner

### Moving an NPC (`/npc move`)
```text
/npc move id:npc_xxxxxx channel:#roleplay-tavern
```
Leave the `channel` option empty to allow the NPC to reply across any eligible channel.

### Editing an NPC (`/npc edit`)
```text
/npc edit id:npc_xxxxxx
```
Re-opens the configuration modal to modify the character's name, prompt, or avatar. The management panel also lets you pick the **AI model** and set the character's own **API key**.

### Deleting an NPC (`/npc delete`)
```text
/npc delete id:npc_xxxxxx
```
Permanently removes the NPC, its stored conversation history, and safely purges the associated Discord Webhook from the channel.

---

## Setting an API Key

Each character can use its own key, so it never eats into the bot's central quota:

1. Run `/npc edit id:npc_xxxxxx`
2. Press **Set API key**
3. Paste your keys, one per line, and save

Hana rotates through the keys automatically when one hits a rate limit, and never substitutes another member's key or the bot's central key. If no key is usable, the character owner is told.

> Server moderators can set the shared keys for the whole server with `/admin`. An NPC uses those when it has no key of its own.

---

## Required Discord Permissions

For the NPC system to operate smoothly, ensure the bot has:
- `Manage Webhooks` (Essential for creating and transmitting webhook messages)
- `View Channel`
- `Send Messages`
- `Read Message History`
