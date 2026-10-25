# DeepLine — Local Personal Android App

DeepLine is a local-first LINE-inspired AI companion app. It has no account system, no invite codes, no administrator panel, no Render backend, and no cloud database.

## Included in this source package

- GIF picker from the device, GIF animation rendering in chat bubbles, and GIF message storage inside the app
- Developer settings unlock code `Yandere` for an opt-in in-app yandere persona mode
- Yandere mode includes a black/red dramatic overlay, an in-app proactive message after 2 minutes of inactivity while a chat is open, a five-second full-screen effect, manual off switch, and shake-three-times off gesture
- No accessibility permission is requested; the mode does not control, block, or launch other apps

## Included in this source package

- LINE-inspired chat list and rounded bottom navigation (Chat / Feed / Settings)
- Personal display name, bio, and photo-library avatar selection
- Up to 10 AI personas, each with its own profile, personality, gender, relationship, likes, dislikes, hobbies, API key, and separate conversation history
- API key required to create an AI persona
- DeepSeek Chat Completions API integration
- Local chat history and local feed posts
- Feed posts with text and selected image, likes, comments, and replies
- Theme accent presets and photo-library background selection for chat/feed surfaces
- Optional AI auto-post / proactive chat-note loop (disabled by default; can consume API quota while the app is running)
- GitHub Actions workflow to build a debug APK

## Build APK with GitHub Actions

1. Upload the contents of this ZIP to a GitHub repository.
2. Open **Actions** and run **Build DeepLine APK** (or push a commit to trigger it).
3. Download the `DeepLine-debug-apk` artifact from the completed workflow.

## API key and privacy

API keys are entered inside the app and stored locally in the app's private preferences. Do not commit API keys to GitHub or share screenshots/backups that expose them. API requests go directly from the device to the configured DeepSeek endpoint. Provider availability, quota, and fees depend on the provider/account.

Local data can be lost if the app is uninstalled or its data is cleared. Photo access uses Android's system photo picker/content URI.

## Technical notes

- Kotlin + Jetpack Compose
- Minimum Android API: 26
- App version: 1.0.0

This package is source code, not a prebuilt APK. It has not been compiled or device-tested in this environment, so run the GitHub Actions build and test the resulting APK on your phone before relying on it. The auto-post feature runs only while the app process is active; Android may suspend background work.

## DeepLine 1.1.0 UI redesign

- Refreshes chat, persona, and feed LazyColumn item keys whenever local data is persisted so changed JSON content is rendered immediately.
- Redesigned cards, gradient persona rows, animated page transitions, avatar frames, optional glass-style cards, and customizable chat bubble color/shape/background image.
- Settings now include theme color (HEX), global font family preset, custom home title, custom chat input hint, sound effects, background image opacity, and glass UI toggle.
- Long-press a message for Copy / Quote / Delete. Long-press or use the menu on an AI card to Edit AI or Delete AI. Editing leaves existing messages and keeps the saved API key if the key field is left blank.
- Added on-device ML Kit image labeling. Use the image icon in the chat composer to select a photo; recognized labels are inserted into the composer so you can send them to the AI for explanation. This is label-based image recognition, not full visual reasoning.
- All persona, message, feed, theme, and image data remain local to the app. API calls are still sent to the configured AI provider.

Build with `gradle assembleDebug` using Android SDK 35 and Java 17. This source ZIP was checked for archive integrity and Kotlin syntax parsing, but was not built with the Android Gradle toolchain or tested on a physical device in this environment.


## DeepLine UI Redesign 1.3.0

This revision includes a more compact chat header/composer, plain avatars without frames, message-name labels under avatars, read-time labels, brighter blue-violet accent colors, a profile-first settings screen with advanced options behind the top-right gear, color palettes for bubble/text colors, TTF import for global typography, global background blur control on Android 12+, simulated in-app red-packet/transfer prompts, configurable multi-replies, and a memory-history length control.

Red-packet and transfer actions are simulated chat interactions only; they do not move real money. Build validation was not run in this environment.
