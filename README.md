# Stream Pulse (SP)

A lightweight Android app that monitors a Twitch channel's live status in the background and notifies you the moment it goes online, so you never miss a stream.

## Features

- Periodic live-status checks against the Twitch API
- Local push notification when the channel goes live
- Simple setup — just plug in your Twitch API credentials and target channel
- Runs quietly in the background with minimal battery/network overhead

## How It Works

SP authenticates with Twitch's API using your app's Client ID and Client Secret, then periodically checks whether the configured channel is currently streaming. When a status change (offline → live) is detected, the app fires a local notification.

## Prerequisites

To connect to Twitch's API, you'll need your own app credentials:

1. Go to the [Twitch Developer Console](https://dev.twitch.tv/console/apps).
2. Register a new application (any redirect URL, e.g. `http://localhost`, works for this use case).
3. Copy the generated **Client ID** and **Client Secret**.
4. Note the **channel name** (Twitch username) you want to monitor.

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/wynnylwy/twitch-network-notifier.git
   ```
2. Open the project in Android Studio.
3. Add your Twitch credentials to the app config (e.g. `local.properties` or `secrets.xml`):
   ```
   TWITCH_CLIENT_ID=your_client_id_here
   TWITCH_CLIENT_SECRET=your_client_secret_here
   TWITCH_CHANNEL_NAME=your_target_channel
   ```
4. Build and run the app on an emulator or device.

## Tech Stack

- Android (Kotlin)
- Twitch Helix API

## Notes

- Credentials are used only to authenticate API requests and are never sent anywhere besides Twitch's servers.
- This project is for personal/notification use only and is not affiliated with Twitch.
