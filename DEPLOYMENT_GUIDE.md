# 🎵 MusicFlow Bot - Deployment Guide

A production-ready Telegram music bot with Spotify integration and high-quality audio downloads.

## 🚀 Quick Deployment on Render

### Step 1: Repository Setup
1. Create a new repository on GitHub
2. Clone this repository or upload all files
3. Push to GitHub

### Step 2: Render Deployment
1. Go to [Render.com](https://render.com)
2. Click "New" → "Web Service"
3. Connect your GitHub repository
4. Configure the service:
   - **Name**: `musicflow-bot` (or your choice)
   - **Environment**: `Docker` or `Python 3`
   - **Build Command**: `pip install -r requirements_simple.txt`
   - **Start Command**: `python app.py`

### Step 3: Environment Variables
Add these environment variables in Render:

| Variable | Description | Where to Get |
|----------|-------------|--------------|
| `TELEGRAM_BOT_TOKEN` | Bot token from BotFather | [@BotFather](https://t.me/BotFather) |
| `SPOTIFY_CLIENT_ID` | Spotify App Client ID | [Spotify Developer Dashboard](https://developer.spotify.com/dashboard) |
| `SPOTIFY_CLIENT_SECRET` | Spotify App Client Secret | [Spotify Developer Dashboard](https://developer.spotify.com/dashboard) |

### Step 4: Getting API Keys

#### Telegram Bot Token
1. Message [@BotFather](https://t.me/BotFather) on Telegram
2. Send `/newbot`
3. Choose a name and username for your bot
4. Copy the token provided

#### Spotify API Keys
1. Go to [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
2. Click "Create an App"
3. Fill in app name and description
4. Copy the Client ID and Client Secret

### Step 5: Deploy
1. Click "Deploy" in Render
2. Wait for build to complete
3. Your bot will be live at `https://yourapp.onrender.com`
4. Visit `https://yourapp.onrender.com/status` for the beautiful status page

## 📁 Project Structure

```
musicflow-bot/
├── app.py                 # Flask web server + bot runner
├── main.py                # Alternative bot runner
├── config.py              # Configuration settings
├── keep_alive.py          # Keep-alive utilities
├── requirements_simple.txt # Clean dependencies
├── requirements.txt       # Full dependencies with hashes
├── Procfile              # Render start command
├── runtime.txt           # Python version
├── .gitignore           # Git ignore rules
├── bot/
│   ├── handlers.py       # Telegram message handlers
│   ├── spotify_client.py # Spotify API integration
│   ├── audio_processor.py # Audio download logic
│   ├── utils.py          # Utility functions
│   └── demo_songs.py     # Demo track functionality
└── templates/
    └── status.html       # Beautiful status page
```

## ✨ Features

- 🎵 **Spotify Integration** - Extract metadata from shared links
- 🎧 **High-Quality Downloads** - Multiple quality options (128/192/320 kbps)
- 🎯 **Smart Recognition** - Automatic track, playlist, and album detection
- ⚡ **Fast Processing** - Concurrent downloads with timeout handling
- 🌐 **Web Interface** - Beautiful status page with real-time updates
- 🔄 **24/7 Uptime** - Keep-alive system for continuous operation
- 📱 **Interactive UI** - Button-based interface, no boring commands

## 🔧 Local Development

1. Clone the repository
2. Install dependencies: `pip install -r requirements_simple.txt`
3. Set environment variables in `.env` file
4. Run: `python app.py`

## 🌟 Production Ready

- ✅ Error handling and logging
- ✅ Automatic file cleanup
- ✅ Concurrent download limits
- ✅ Health monitoring endpoints
- ✅ Beautiful web interface
- ✅ Docker compatibility
- ✅ Environment-based configuration

## 📞 Support

After deployment, your bot will be available 24/7 at the Render URL. Users can:
- Share Spotify links for instant downloads
- Choose quality preferences
- Download entire playlists and albums
- Access demo tracks for testing

The status page at `/status` shows real-time bot health and uptime information.