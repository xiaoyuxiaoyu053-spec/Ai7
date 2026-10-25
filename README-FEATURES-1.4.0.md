# DeepLine 1.4.0 — GIF + Yandere

## GIF
- Open a chat, tap the `+` button, then choose `GIF 表情包`.
- Select a GIF from the system picker. The GIF is copied into app-private storage and added to the composer; tap send to send it.
- The chat bubble uses Coil GIF decoding to animate it. The message also includes a text hint for the AI. The current text-only DeepSeek request does not upload the GIF's actual frames to a vision model, so AI replies are context-based rather than guaranteed frame-by-frame visual recognition.

## Yandere
- Settings → Advanced Settings → Developer Mode · Yandere. Enter `Yandere`, then read and accept the warning.
- While a chat is open, if there is no interaction for two minutes, the selected persona adds a short in-character message and the app shows a black/red five-second overlay.
- Turn it off with the Settings switch or shake the phone three times.
- No Accessibility permission is requested. This mode stays inside DeepLine and cannot force-launch, block, or control other apps.

## Build
Upload the ZIP contents to GitHub and run the included Actions workflow. This package has not been built in an Android SDK environment here; use GitHub Actions to verify compilation.
