# Get a Gemini API Key

This guide walks you through generating a personal Google Gemini API key to power your **Dedicated Server Secretary Desk (`/hanacontext`)** or **Custom Roleplay NPCs (`/npc`)** in just 2–3 minutes.

> ⚠️ **Security Warning:** Your API key is as sensitive as a password. Never post it in public channels, share it with others, or take screenshots showing the full key. If exposed, delete the key immediately in Google AI Studio and generate a new one.

---

## 1. Open Google AI Studio

Visit [Google AI Studio](https://aistudio.google.com/welcome) and sign in with your Google account.

If visiting for the first time, click **Get started** and agree to the Google Terms of Service to proceed.

![Get started button on Google AI Studio](../.gitbook/assets/gemini-api-key-01-get-started.png)

---

## 2. Navigate to API Keys

Once in the AI Studio Dashboard, click the key icon labeled **API Keys** on the left navigation sidebar.

![Key icon to open the API Keys page](../.gitbook/assets/gemini-api-key-02-menu.png)

---

## 3. Create a Key

Click **Create API Key**.

![Create API Key button](../.gitbook/assets/gemini-api-key-03-create.png)

- New accounts may already have an initial project and pre-generated key ready to use.
- If prompted to select a project, pick an existing Google Cloud project or create a new dedicated project for Hana.
- Once created, click the **Copy** icon and temporarily store the key securely.

---

## 4. Enter the Key into Hana

### For the Dedicated Server Secretary Desk (`/hanacontext`)
1. In Discord, run `/hanacontext` in your server.
2. Select the designated room using the `ChannelSelectMenu`.
3. Click the **Setup Secretary / Edit Details** button.
4. Paste your key into the **Gemini API Key** field and submit.
5. The bot verifies the key immediately. The Secretary will answer questions without depleting the bot's shared host quotas!

### For Custom Roleplay NPCs (`/npc`)
- The NPC system supports server-configured API keys or user keys, enabling smooth multi-turn roleplay without host quota friction.

---

## Troubleshooting & Best Practices

- School or enterprise Google Workspace accounts may restrict API key generation. Use a standard personal Google account instead.
- All API keys stored in Hana are **strictly encrypted using AES-256-GCM** prior to database storage. Keys are never logged in system outputs or exposed to other members.
- Official Google documentation: [Gemini API Quickstart](https://ai.google.dev/gemini-api/docs/get-started) · [Managing API Keys](https://ai.google.dev/gemini-api/docs/api-key)
