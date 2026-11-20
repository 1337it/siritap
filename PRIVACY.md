# Privacy

Siritap runs entirely on your Mac.

- **No network.** Siritap makes no internet connections: no analytics, no crash reporting, no update checks, no accounts.
- **No data collection.** Nothing about you, your Mac or how you use the remote is recorded or sent anywhere.
- **Settings** are stored on your Mac only, in `~/.config/siritap/config` and in the app's preferences (`ae.leet.siritap`).

## Permissions

| Permission | Why |
|---|---|
| Accessibility | To move the pointer, click, scroll and press keys for the remote. With Button mode on, also to find where buttons, links and fields are in the apps on screen. |
| Microphone | Only for voice typing with the Mac's microphone. Siritap listens only while you hold the dictate button. |
| Speech Recognition | To turn what you say into text. |
| Background helper (optional) | Only for voice typing with the 2nd-generation remote's own microphone. See below. |

## Button mode

When Button mode is on, Siritap asks macOS Accessibility where the buttons, links, text fields, files and Dock icons on screen are, so the pointer can settle on them and you can swipe between them. It reads their type, position and size only: not their labels, not what you type, not page content. The list is kept in memory for a few seconds and never saved or sent anywhere. Some apps (Chrome, and apps built like it) only describe their buttons once an assistive tool asks, so Siritap asks them to. With Button mode off, none of this happens.

## Speech

Siritap uses Apple's speech recognition and asks it to work on your Mac. For languages your Mac can't recognise offline, macOS may send the audio to Apple, the same as macOS dictation; see Apple's [Siri and dictation privacy](https://www.apple.com/legal/privacy/data/en/ask-siri-dictation/) page. Siritap doesn't keep audio or text after typing it.

## The background helper

Using the remote's own microphone needs a small helper that runs with administrator rights, because macOS only exposes that audio through its Bluetooth diagnostic log.

- It runs only after you approve it in **System Settings → General → Login Items**, and you can turn it off there at any time.
- It turns Bluetooth logging on only while Siritap is open and connected to it, and turns it off again afterwards. If the setting was already on before, it leaves it alone.
- From the log it keeps only the remote's voice packets, passes them to Siritap, and keeps nothing. It writes only short status lines (such as "trace started") to `/var/log/siritap-voicehelper.log`, never audio or text.
- Only the Siritap app, signed by its developer, can connect to it. Other apps are refused.
