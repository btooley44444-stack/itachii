# 🎵 YouTube Discord Bot (discord.js)

A Discord bot like NotSoBot — stream YouTube audio in voice channels and download videos/audio to chat.

---

## ✅ Requirements

- **Node.js 18+** — https://nodejs.org
- A Discord bot token

> No need to install FFmpeg separately — it's bundled via `ffmpeg-static`.

---

## 🚀 Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Create your `.env` file

```bash
cp .env.example .env
```

Then edit `.env` and paste in your bot token:
```
DISCORD_TOKEN=your_actual_token_here
```

### 3. Create your Discord bot

1. Go to https://discord.com/developers/applications
2. Click **New Application** → give it a name
3. Go to **Bot** → click **Add Bot**
4. Click **Reset Token**, copy it into your `.env`
5. Scroll down and enable **Message Content Intent**
6. Go to **OAuth2 → URL Generator**
   - Scopes: ✅ `bot`
   - Bot Permissions: ✅ `Send Messages` `Embed Links` `Attach Files` `Connect` `Speak` `Use Voice Activity` `Read Message History`
7. Copy the generated URL, open it in your browser, and add the bot to your server

### 4. Run the bot

```bash
npm start
```

---

## 📖 Commands

| Command | Aliases | Description |
|---------|---------|-------------|
| `!play <url or search>` | `!p` | Stream a YouTube video in your voice channel |
| `!search <query>` | `!s` | Search YouTube and show top 5 results |
| `!download <url or search>` | `!dl`, `!save` | Download a video as MP4 and send it (max 10 min) |
| `!audio <url or search>` | `!mp3` | Download audio as MP3 and send it |
| `!skip` | `!next`, `!sk` | Skip the current song |
| `!queue` | `!q` | Show the current queue |
| `!nowplaying` | `!np` | Show what's currently playing |
| `!pause` | | Pause playback |
| `!resume` | | Resume playback |
| `!stop` | | Stop playback and clear the queue |
| `!leave` | `!dc`, `!disconnect` | Disconnect the bot from voice |
| `!help` | | Show all commands |

---

## ⚠️ Notes

- **File size limit:** Discord caps uploads at 25 MB (Nitro-boosted servers get more). If a video is too big, use `!play` to stream it instead.
- **Download limits:** Videos capped at 10 min, audio at 20 min.
- YouTube occasionally blocks requests. If streams stop working, the `play-dl` package usually handles this — try `npm update play-dl`.

---

## 🔧 Troubleshooting

| Problem | Fix |
|---------|-----|
| `Cannot find module` | Run `npm install` |
| Bot joins but no audio | Make sure you granted `Connect` + `Speak` permissions |
| Downloads fail | Run `npm update yt-dlp-exec` |
| Token error | Regenerate token in Discord Developer Portal |
| Node version error | Upgrade to Node.js 18+ |
