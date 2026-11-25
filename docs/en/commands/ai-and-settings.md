# AI and Settings

To create and manage custom roleplay characters in your server, see the [`/npc`](npc-roleplay.md) guide.

---

## `/guildbook`

Opens an interactive guide inside Discord detailing how to chat and interact with Hana.

---

## `/statusai`

Shows Hana's current status according to Japan Standard Time. To keep it short and useful, it only includes:

- Japanese time
- What she is doing now
- Her location
- Sapporo weather
- What she is wearing
- Today's mood
- Health note
- Current interest
- Today's event

Personality, summary, energy level, Discord status and the university calendar were removed from this panel.

---

## `/settings`

Your private personal control panel; other members cannot view it. **The language menu is on the very first page**, so you can change Thai / English / Japanese (or Automatic) immediately.

- 🌐 Choose your language on the first page (shown in your current language)
- Toggle reply mentions on or off
- Configure your personal timezone
- Add, update, or remove personal profile details (e.g. nickname, interests, birthday)
- Delete your personal data from the **Data** page

> Memory is now short-term, so the old "view memory" button was removed. Memory and relationship data are always scoped per server and cannot be shared across servers.

> **Important:** Do not enter addresses, phone numbers, passwords, financial records, or sensitive personal data. Nicknames or hobbies are more than enough.

Hana does not send unsolicited proactive tags to avoid disturbing members.

---

## `/profile`

Displays the personal profile details you configured and your relationship standing with Hana in the current server.

### Relationship Levels:

| Score | Level |
| :--- | :--- |
| 0–24 | Acquaintance |
| 25–100 | Regular Chat |
| 101–300 | Friend |
| 301–500 | Close Friend |

> Hana is strictly a close friend and will never engage in romantic roleplay.

---

## `/hanainsights`

Shows this server's weekly AI quota and the features currently active for everyone (full status, Hana Context, NPC roleplay). All features are free during beta — there is no Premium tier.

---

## `/hanacontext` — For Server Administrators

Opens the server context management dashboard and **Dedicated Server Secretary Desk**. Features 1-click room assignment via `ChannelSelectMenu`, server guidelines/rules setup, and zero bot quota leak using the admin's own API key.

The **Server Admin Hub** (central API keys, NPC and secretary shortcuts) has its own command, [`/admin`](../roomai-and-permissions.md), and is separate from this panel.

For full details, see the [Server Owner Guide & Secretary Desk](../roomai-and-permissions.md).
