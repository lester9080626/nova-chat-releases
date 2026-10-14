# Changelog

All notable changes to Nova Chat are documented here, newest version first.

## [Unreleased]

## [1.4.2] — Microphone Toggle

### Added

- **Speech only input mode.** **Settings → Input → Speech only** never shows the message box, only
  the microphone button, which turns listening on and off.
- **Microphone shortcut.** Tap **⌘ Command** on its own in any app to turn the microphone on and
  off. It can be changed or turned off in **Settings → Shortcut**.

### Changed

- **The microphone button turns listening on and off without changing the input mode.** In
  **Speech**, the message box shows while the microphone is off. Whether it was on is remembered
  for the next launch.
- **Typing hides the microphone button.** Choose **Speech** or **Speech only** in **Settings →
  Input** to listen.

## [1.4.1] — Refreshed Dark Theme

### Changed

- **Refreshed dark theme.** Nova Chat's dark palette has refined contrast, more surface and text
  shades, and new warning, success and accent colours, applied consistently across the chat
  window, Manage Chats, Settings, the setup window and message dialogs.

## [1.3.0] — Reply Scrolling and Chat Bubble Fixes

### Added

- **Reply-by-reply scrolling.** Left (**←**) and right (**→**) arrows appear beside each reply so
  you can step back to an earlier reply and forward again without leaving the window. Only the
  current reply is fully visible; the others collapse out of the way.
- **Keyboard shortcuts for scrolling.** **Shift+Up** and **Shift+Down** step to the previous and
  next reply from any app once Input Monitoring is allowed. The shortcuts are configurable in
  **Settings → Shortcut** alongside the show/hide and click-through shortcuts.

### Fixed

- **Prompter's bubble collapse.** Sent messages now collapse correctly when the view scrolls to a
  different reply; previously they could remain expanded.
- **Prompter's chat alignment.** The user's sent messages now align consistently with the AI's
  reply bubble side setting.
- **Prompter's bubble appearance.** Visual polish — padding, border radius and colour of the
  user's message bubble corrected.
- **Responder's bubble appearance.** Visual polish — the AI's reply bubble padding and layout
  corrected.

## [1.2.1] — Error Message Improvements

### Fixed

- **Model name in error messages.** When llama-server or an online API fails to reply, the error
  message now includes the name of the model that was being reached, making it easier to identify
  which provider or model file caused the problem.

## [1.2.0] — In-App Update Checker

### Added

- **In-app update checker.** The bottom of every Settings page shows the current version and
  checks whether a newer release is available on GitHub. When one is found, the label says so and
  an **Update** button downloads its disk image and opens it in Finder, ready to drag onto
  Applications. When Nova Chat is already up to date, the button is disabled and the label
  confirms it.

## [1.1.3] — Remove Keychain Dependency

### Changed

- **API keys moved from Keychain to `usersettings.json`.** Nova Chat no longer uses the macOS
  Keychain to store API keys. Keys are now written to `usersettings.json` in
  `~/Library/Application Support/NovaChat`, which is readable only by the current user. macOS
  will never prompt to allow keychain access for Nova Chat, including after updates. Users
  upgrading from 1.1.2 or earlier need to re-enter their API keys in **Settings → AI model**;
  the old **Nova Chat** keychain items can be deleted in Keychain Access.

## [1.1.2] — Shortcut Permission Fix

### Fixed

- **Shortcut key bugs.** The click-through shortcut (⌥ Option) and the show/hide shortcut
  (⌃ Control, added in 1.1.1) could misfire or fail to register correctly in certain conditions.
  Both shortcuts now behave reliably.

## [1.1.1] — Show/Hide Window Shortcut

### Added

- **Show/hide window shortcut.** Tap **⌃ Control** on its own from any app to hide the chat
  window, and tap it again to bring it back. Replies and speech recognition continue while the
  window is hidden. The shortcut is configurable in **Settings → Shortcut** (a lone modifier, a
  key with Control/Option/Command, or a function key; Delete turns it off).
- **Show Chat Window menu item.** The menu bar icon's menu now has a **Show Chat Window** item,
  checked while the window is on screen. Clicking it toggles the same as the shortcut.

## [1.1.0] — Model Chain

### Added

- **Model chain.** **Settings → Chain** (a new settings page) lets you add up to 6 models
  through which each message passes before the base model replies. Messages travel from the last
  model added to the first, with each reply handed on to the next, and the first model's output
  goes to the base model that answers in the chat. Only the base model's reply is shown or saved.
- **Chain model configuration.** Each chain model is either **On this Mac** (any
  OpenAI-compatible local server such as llama-server, LM Studio or Ollama) or an **Online API**,
  with its own base URL, optional API key, model ID, and system instructions (for example
  *"Translate this message into English."*). API keys for chain models are stored in
  `usersettings.json`.
- **Chain flow option.** **Message + Previous Prompt** sends the user's original message together
  with the previous chain model's reply to the next model. **Previous Prompt only** (the default)
  sends only the previous reply, so each model works on a progressively transformed version.
- **Chain status display.** While chain models are processing, the status line reads *"Chain model
  N is working…"*, and an error from any chain model is shown in the chat bubble instead of
  proceeding to the base model.
- **Sources shared with the chain.** Source files attached on **Settings → Instructions** are
  sent to every model in the chain as well as the base model; the system instructions on that page
  go only to the base model.

## [1.0.1] — Input Monitoring Prompt, Font Settings and Layout Controls

### Added

- **Input Monitoring permission prompt.** When the click-through or show/hide shortcut watcher is
  denied by macOS, the status hint under the message box now names the affected shortcuts and
  directs you to **System Settings → Privacy & Security → Input Monitoring** to allow Nova Chat.
  The shortcuts start working as soon as permission is granted, without restarting the app.
- **Font settings.** **Settings → Appearance** now includes a font family picker and bold, italic,
  and underline toggles. Text was always bold before this release; bold stays on by default. Font
  size was already adjustable.
- **Markdown / plain text toggle.** A **Markdown / Plain text** switch appears above the AI's
  reply so you can switch between formatted Markdown (headings, lists, code blocks) and plain text
  without opening Settings. The same choice is mirrored in the menu bar icon's menu as **Format
  Replies as Markdown**.
- **Adjustable reply bubble width.** **Settings → Appearance** adds a **Bubble width** slider
  that controls how wide the AI's reply bubble can grow as a percentage of the window's inner
  width (50–100%).
- **Dynamic window position mode.** **Settings → Layout → Window position mode** can be set to
  **Dynamic**: while click-through is on, the window moves to whichever half of the screen (top
  or bottom) is away from the click, so it stays out of your way as you work in the app behind it.
- **Dynamic reply bubble position mode.** **Settings → Layout → Reply bubble position mode** can
  be set to **Dynamic**: while click-through is on, the bubble moves to whichever side of the
  window (left or right) is away from the click.
- **Reply bubble alignment.** **Settings → Layout** adds a **Reply bubble alignment** option
  (Left, Center, Right) so you can pin the bubble to a fixed side independent of Dynamic mode.

### Fixed

- **Screen sharing bug.** The window's hide-from-screen-sharing state is now applied correctly on
  launch and after settings changes.
- **Chat bubble width.** The AI's reply bubble now expands to the full available width when no
  explicit width limit is set.
- **Microphone mode disabling input box.** The text input box now correctly becomes read-only
  while speech input is active, and becomes editable again when speech is stopped.
- **Listening label while mic is on.** The "Listening…" label under the message box now shows and
  hides correctly when the microphone starts and stops.

## [1.0.0] — Initial Release

### Added

- **Menu bar icon.** Nova Chat lives in the macOS menu bar as a purple chat bubble with three
  dots. There is no Dock icon. Clicking the icon opens its menu; the chat window appears
  automatically on launch.
- **Floating chat window.** A semi-transparent window that sits above every app, including
  full-screen ones. Opacity is adjustable in **Settings → Appearance**.
- **Always on Top.** The window stays above all other apps and on every Space by default. Toggle
  it from the menu bar icon's menu.
- **Click-through mode.** Tap **⌥ Option** (configurable) to let your clicks pass through the
  chat window to whatever is behind it. Tap again to turn it off. A hint under the message box
  says when it is on. The shortcut is configurable in **Settings → Shortcut**.
- **Hide from Screen Sharing.** The chat window is left out of screen shares, screenshots and
  recordings by default. A green or red dot under the message box shows the current state. Toggle
  it from the menu bar icon's menu.
- **Local AI via llama.cpp.** The first-run **Welcome to Nova Chat** setup window offers to
  download and install llama.cpp (via Homebrew if available, otherwise from GitHub, ~30 MB) and a
  Gemma 4 E4B model from Hugging Face (~5 GB). Downloads can be paused and resumed. Replying from
  a local model needs no internet after setup.
- **Online API support.** Switch to any OpenAI-compatible service — OpenAI, Anthropic (Claude),
  Google Gemini, OpenRouter, Groq, or any other — by entering a base URL, API key, and model ID
  in **Settings → AI model**. Local servers such as LM Studio or Ollama work the same way.
- **Speech input.** Whisper speech recognition runs on-device, so nothing said is sent anywhere
  to be turned into text. Choose **Sound playing on this Mac** (Mac audio — apps, videos, calls;
  requires macOS 14.2 or later) or **A microphone** in **Settings → Input**. Eleven languages are
  supported (English, Filipino, Spanish, Portuguese, French, German, Japanese, Korean, Chinese,
  Hindi, Indonesian) plus automatic language detection. What is said is transcribed and sent each
  time the speaker pauses. The speech model (~140 MB) is downloaded the first time speech is
  started.
- **Instructions and sources.** **Settings → Instructions** holds a custom system prompt that
  tells the AI who it is and how to reply (replacing the default warm diary companion). Add PDF,
  Word (.docx), PowerPoint (.pptx), Excel (.xlsx), OpenDocument, and text files (`.txt`, `.md`,
  `.csv`, `.json`, `.yaml`, `.xml`, `.html`, `.log`) as sources; up to 12,000 characters of
  source content are sent with every message.
- **Saved chats.** Every conversation is saved locally in `chats/` the moment you send a message,
  named after the first message. **Chats** in the menu bar icon's menu lists the 25 most recent.
  **Manage Chats…** shows all of them with Open, Rename (or F2), and Delete.
- **New Chat** in the menu bar icon's menu starts a fresh conversation while keeping previous ones
  accessible.
- **Settings window** with six pages: **AI model** (local model or online API), **Appearance**
  (text size, font size, opacity), **Layout** (window and bubble position), **Input** (Typing or
  Speech, audio device, language), **Shortcut** (click-through key), and **Instructions** (system
  prompt and sources).
- **API keys in Keychain.** API keys entered in Settings are stored in the macOS Keychain.
  (Moved to `usersettings.json` in 1.1.3.)
