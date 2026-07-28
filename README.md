# Stream Pulse (SP)

A lightweight Android app that monitors a Twitch channel's connection status in the background and notifies you the moment something changes, such as **online**, **offline**, or **connection** issues, so you're always in the loop.

## Screenshots

### Home

| Default | Monitoring |
|---|---|
|  <img width="200" height="400" alt="image" src="https://github.com/user-attachments/assets/8ec2b542-f560-428e-87db-20de9f8e9ad2" /> | <img width="200" height="400" alt="image" src="https://github.com/user-attachments/assets/0e4bacc1-8c1f-4592-8e90-3b92a6a315e0" /> |

### Settings

<img width="200" height="450" alt="image" src="https://github.com/user-attachments/assets/600a30bd-3c8a-4461-83f9-346fb4e95572" />


### Notifications

| Monitoring Active | Offline | Connection Issue |
|---|---|---|
| <img width="700" height="250" alt="image" src="https://github.com/user-attachments/assets/a5abf99a-5efb-46a3-9537-5c7f2cf4c70b" /> | <img width="350" height="350" alt="image" src="https://github.com/user-attachments/assets/59142e0e-1254-4b82-a40b-3f3704e79b00" /> | <img width="350" height="450" alt="image" src="https://github.com/user-attachments/assets/105b33c3-1ac3-48f4-bd29-4cc9602d023b" /> |

## Features

- Periodic status checks against the Twitch API
- Detects and distinguishes three states: **online**, **offline**, and **connection issue**
- Local push notification on every status change
- Simple setup — just plug in your Twitch API credentials and target channel
- Runs quietly in the background with minimal battery/network overhead

## How It Works

SP authenticates with Twitch's API using your app's Client ID and Client Secret, then periodically checks the configured channel's status. It distinguishes between the channel being offline and the check itself failing (e.g. network/API errors), so you get an accurate picture rather than a false "offline" reading. When the status changes, the app fires a local notification.

## Prerequisites

To connect to Twitch's API, you'll need your own app credentials:

1. Go to the [Twitch Developer Console](https://dev.twitch.tv/console/apps).
2. Register a new application (any redirect URL, e.g. `http://localhost`, works for this use case).
3. Copy the generated **Client ID** and **Client Secret**.
4. Note the **channel name** (Twitch username) you want to monitor.

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/wynnylwy/stream-pulse.git
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

## License

MIT
