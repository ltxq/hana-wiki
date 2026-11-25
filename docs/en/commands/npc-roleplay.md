# Custom Roleplay NPCs

`/npc` is a server roleplay character management system powered by Discord Webhooks. Characters respond with their own designated name and avatar, creating an authentic in-character immersion.

> **Updated in v1.5.2:** `/npc` is now a **single command that opens a button panel**. The old subcommands (`create` / `list` / `move` / `edit` / `delete`) were removed — everything is done by pressing buttons, just like the secretary desk (`/secretary`).

---

## Key Highlights

- **One command, all buttons**: press `/npc` once, then use the buttons and drop-downs on the panel. No subcommand names or character IDs to memorise.
- **Webhook Representation**: Every reply is sent through a custom Discord Webhook featuring the NPC's specific avatar and name.
- **Easy 3-Field Creation**: press **➕ Create NPC** and fill in the Name, Personality/System Prompt, and Opening Greeting. The bot provisions the webhook and posts the opening line automatically.
- **Natural Interaction**: Server members interact with NPCs by **Replying directly** to an NPC message or by **writing the character's name** in the channel.
- **Real Conversation Memory**: Each character remembers up to 12 turns of your conversation (kept separately per character and per user, and forgotten after 6 hours of silence).
- **Your Choice of Model**: a drop-down on the management panel switches between Gemini, OpenRouter (DeepSeek, GPT, Claude), or a custom provider/model instantly.
- **3 Languages**: the whole panel follows your `/settings` language (Thai, English or Japanese).
- **Isolated Quota**: characters use their own API keys (Gemini / OpenRouter) first, then the server central keys from `/admin`, so the bot host's quota is never consumed.
- **Decoupled from Hana**: Hana remains a cheerful high-school student chatting in `/setroomai` rooms without role confusion.

---

## Opening the hub (`/npc`)

Simply run `/npc` in any server channel. Hana replies **ephemerally** (only you can see the panel) with:

- the number of characters on the server and how many are yours,
- the status of the server central API keys,
- a preview list of the characters (name, home channel, model, key source),
- a **select menu** to jump straight into a character's management panel.

Anyone can open the hub. Admin-only shortcuts (**Central keys**, **Secretary desk**) appear only for members with channel/server management permissions.

### Hub buttons

| Button | What it does |
| :--- | :--- |
| ➕ **Create NPC** | Opens the 3-field creation modal in the current channel |
| 🎭 **All** / 👤 **Mine** | Filters the list (and the select menu) to everyone / just your characters |
| ❓ **How to use** | Opens a short in-panel guide |
| 👑 **Central keys** | Jumps to `/admin` (admins only) |
| 👩‍💼 **Secretary desk** | Jumps to `/secretary` (admins only) |
| 🔄 **Refresh** | Reloads the panel after an external change |

---

## Creating a character

1. Run `/npc`.
2. Press **➕ Create NPC**.
3. Fill in the modal:
   - **NPC Name** — the webhook display name (e.g. `Yami`, `Sensei Aiko`, `Knight Arthur`).
   - **Personality** — role, background, traits, speech tone and behaviour boundaries.
   - **Opening Greeting** — the debut message posted into the channel immediately.
4. Submit. Hana creates the webhook, posts the greeting, and shows the character ID in an ephemeral confirmation.

---

## Interacting with NPCs

### 1. Direct Reply
Click **Reply** on any message sent by the NPC and type your response. The character uses its own conversation history to answer in context.

### 2. Mention by Name
Write the character's exact name anywhere in its channel:
```text
Hello Yami, did you finish the math assignment yet?
```
A matching NPC assigned to that channel will respond in character.

---

## Managing a character

Pick a character from the hub's select menu (or press its entry in the list) to open the management panel:

- **Model drop-down** — switch provider/model instantly; **⚙️ custom** opens a modal for `provider:model`.
- 📝 **Edit profile** — change name, personality, greeting and avatar URL.
- 🔑 **API key** — set or clear the character's own keys.
- 📍 **Move channel** — pick a text channel, or press **🌐 Any channel (Global)**.
- 🗑️ **Delete** — asks for confirmation before removing the character.
- 📋 **Back to hub** — returns to the main panel.

### API keys

1. Open the character's management panel.
2. Press **🔑 API key**.
3. Paste one key per line and save. Leave the field empty and save to **clear** the character's keys and fall back to the server central keys from `/admin`.

Hana rotates through keys automatically when one hits a rate limit. A character never uses another member's key, and Hana's own central key is only used as the final server-level fallback configured by an admin.

---

## Required Discord Permissions

For the NPC system to operate smoothly, ensure the bot has:
- `Manage Webhooks` (essential for creating and sending webhook messages)
- `View Channel`
- `Send Messages`
- `Read Message History`
