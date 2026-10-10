# Nova Chat

**An AI companion that lives in your Mac's menu bar.** Type to it, talk to it, or let it listen
along while a video or call plays. Its replies come from a model running on your own Mac, so your
chats stay on your Mac, it works offline, and you don't need an account. If you'd rather use a
cloud model, any OpenAI-compatible service plugs in.

**[⬇ Download Nova Chat for Apple silicon Macs](https://github.com/lester9080626/nova-chat-releases/releases/latest)**

## Highlights

- **Private by default.** Replies come from [llama.cpp](https://github.com/ggml-org/llama.cpp)
  running on your Mac. Once it's set up, Nova Chat needs no internet and your messages stay on the
  Mac. Prefer a cloud model? Switch to OpenAI, Anthropic (Claude), Google Gemini, OpenRouter, Groq,
  or any other service with an OpenAI-compatible API.
- **Talk instead of typing.** Speech recognition (Whisper) also runs on your Mac. It turns what's said
  into the microphone, or the sound playing on the Mac (a video, a podcast, a call), into messages.
  It understands English, Filipino, Spanish, Portuguese, French, German, Japanese, Korean, Chinese,
  Hindi and Indonesian, or works out the language by itself.
- **Always there, never in the way.** A see-through window that floats above every app, full-screen
  ones included. Tap **⌃ Control** to hide or show it. Tap **⌥ Option** to let your clicks pass
  through it to the app behind.
- **Left out of screen shares.** It's on by default: you see the window, but screen shares,
  screenshots and recordings don't.
- **Knows your documents.** Add PDF, Word, PowerPoint, Excel or text files as sources, and every
  reply draws on them.
- **Chain models together.** Send each message through up to 6 more models before the main one
  replies, for example to translate it first, sum it up, or rewrite it.
- **Your chats are kept.** Every chat is saved on the Mac, so you can pick one up again, rename it
  or delete it.
- **Make it yours.** Choose the font, text size, opacity, where the window and reply sit, and how
  the AI talks to you.
- **Easy updates.** Settings tells you when a new version is out and downloads it for you.

## Requirements

- A Mac with Apple silicon (M1 or later).
- macOS 14 Sonoma or later, including macOS 15 Sequoia. Listening to the sound playing on the Mac
  needs macOS 14.2 or later. The microphone works on any of them.
- About 5 GB of free space for the AI model, if replies come from your Mac. With an online API,
  none is needed.

## Installing

1. Download `NovaChat-<version>-arm64.dmg` from the
   [latest release](https://github.com/lester9080626/nova-chat-releases/releases/latest), or any
   version from the [Releases](https://github.com/lester9080626/nova-chat-releases/releases) page.
   The `arm64` disk image is the one for Apple silicon Macs, such as the MacBook Air (M1, 2020) on
   macOS 15 Sequoia.
2. Open it and drag **Nova Chat** onto **Applications**.
3. Open Nova Chat from Applications. It has no Dock icon: look in the menu bar for a purple chat
   bubble with three dots.

The app isn't notarized by Apple, so the first time you open it macOS says *"Nova Chat" Not Opened*.
Click **Done**, then open **System Settings → Privacy & Security**, scroll down to **Security**, click
**Open Anyway** next to the message about Nova Chat, and confirm with your password. You need to do
this once for each new version.

Or run this command in Terminal, which does the same:

```sh
xattr -dr com.apple.quarantine "/Applications/Nova Chat.app"
```

## Your first five minutes

1. **Set up the AI.** The first time you open Nova Chat, the **Welcome to Nova Chat** window offers
   to install what the AI needs. You only do this once:
   - **llama.cpp**, the engine that runs the model. It's installed with Homebrew if you have it
     (`brew install llama.cpp`), and otherwise downloaded from GitHub (about 30 MB).
   - **The AI model**, a Gemma 4 E4B model from Hugging Face (about 5 GB).

   Click **Install**. If the download stops, **Resume** carries on from where it left off. The other
   buttons:
   - **Use an online API...** skips the download. It opens Settings, where you choose a service,
     paste your API key and pick a model.
   - **I have the model...** uses a `.gguf` model file you already have.
   - **Not now** closes the window. Send a message later to open it again.
2. **Say hi.** Type in the box at the bottom and press **Return** to send. **Shift + Return**
   starts a new line.
3. **Hide it and bring it back.** Tap **⌃ Control** on its own, in any app. Tap **⌥ Option** to
   switch click-through on or off.
4. **Allow Input Monitoring.** These shortcuts need it to work while you're in other apps. When
   macOS asks, allow Nova Chat in **System Settings → Privacy & Security → Input Monitoring**.
   Until you do, the hint under the message box names the shortcuts that are waiting. They start
   working as soon as it's on, without opening Nova Chat again.
5. **Try speech.** Click the microphone button next to the message box. The first time, Nova Chat
   downloads the speech model (about 140 MB), and macOS asks you to allow system audio or the
   microphone. While it listens, what's said is sent as a message each time the speaker pauses.
   Click the button again to stop. **Settings → Input** chooses what it listens to: the sound
   playing on the Mac (the default) or a microphone.
6. **Make it yours.** Click the menu bar icon and choose **Settings…**:
   - **Instructions** tells the AI who it is and how to reply (by default, a warm diary companion)
     and holds your sources.
   - **Appearance** and **Layout** change how it looks and where it sits, live as you change them.
     **Save** keeps the changes.

## Using Nova Chat

### The menu bar icon

| Item | What it does |
| --- | --- |
| **Show Chat Window** | Takes the chat window off the screen and brings it back (⌃) |
| **New Chat** | Starts a new chat. The current one stays in **Chats** |
| **Chats** | Your 25 most recent chats, and **Manage Chats…** for all of them |
| **Always on Top** | Keeps the window above other apps, on every Space and over full-screen apps (on by default) |
| **Click-Through** | Sends clicks through the window to the apps behind it (⌥) |
| **Hide from Screen Sharing** | Leaves the window out of screen shares, screenshots and recordings (on by default) |
| **Format Replies as Markdown** | Shows headings, lists and code in replies, instead of plain text |
| **Listen to Mac Audio** / **Listen to Microphone** | Starts or stops speech input |
| **Settings…** | Opens Settings |
| **Quit Nova Chat** | Quits, and stops the model running on your Mac (⌘Q) |

### Showing and hiding the chat window

Tap **⌃ Control** on its own (press and release it, with no other key) in any app to take the chat
window off your screen, and tap it again to bring it back. **Show Chat Window** in the menu bar
icon's menu does the same: it is checked while the window is on screen. Replies and listening carry
on while the window is hidden.

Closing the chat window quits Nova Chat, so hide it instead.

This is separate from **Hide from Screen Sharing**, which keeps the window on your screen and only
leaves it out of screen shares, screenshots and recordings.

**Settings → Shortcut** changes the shortcut, as it does the click-through one (**⌥ Option** by
default). A shortcut can be a lone modifier, a key with Control, Option or Command such as ⌃⌥H, or a
function key; Delete turns it off. The two shortcuts have to be different. A Control-click (a
right-click) doesn't count as a tap.

### Click-through

Tap **⌥ Option**, or choose **Click-Through** in the menu, and your clicks go to the windows behind
the chat. That way it can sit over whatever you're working on. The hint under the message box says
so while it's on. Tap again to turn it off.

With **Settings → Layout → Window position mode** set to **Dynamic**, the window gets out of your
way while click-through is on. A click in the top half of the screen moves it to the bottom, and a
click in the bottom half moves it to the top. **Reply bubble position mode** does the same from side
to side. Both need Input Monitoring.

### Hide from Screen Sharing

The dot under the message box shows whether others can see the window:

- Green, **Hidden from screen sharing**: you see it, screen shares, screenshots and recordings don't.
- Red, **Visible in screen sharing**: **Hide from Screen Sharing** is off in the menu.
- Red, **Can’t hide from screen sharing**: it's on, but macOS didn't hide the window.

### Speech input

Speech recognition runs on your Mac with Whisper, so nothing said is sent anywhere to be turned
into text. In **Settings → Input**, choose **Speech** and then:

- **Listen to**: **Sound playing on this Mac**, which is what apps play through the speakers or
  headphones and opens no microphone, or **A microphone**.
- **Device**: all the sound playing on the Mac or only one output, or which microphone to use.
- **Language spoken**: **Detect automatically**, or one of the 11 languages.

The microphone button or **Listen to…** in the menu starts and stops listening. While it listens,
the message box gives way to a red **Listening...** label, and what's said is sent each time the
speaker pauses.

### Instructions and sources

**Settings → Instructions** tells the AI who it is and how to reply. Your instructions replace the
default ones. **Use the default instructions** brings those back.

Sources are files the AI reads with every message and uses as reference: PDF, Word, PowerPoint,
Excel, OpenDocument, and text files such as `.txt`, `.md`, `.csv`, `.json`, `.yaml`, `.xml`, `.html`
or `.log`. **Add files...** adds them. Up to 12,000 characters in total are used, and the page says
when your sources go over.

### Chats

Every chat you say something in is saved on your Mac, named after its first message. Nova Chat opens
on a new chat each time. **Chats** in the menu bar icon's menu lists the latest ones, and
**Manage Chats…** shows them all: **Open** carries on with one, **Rename** (or F2) renames it, and
**Delete** removes the ones you select.

### Model chain

**Settings → Chain** adds up to 6 more models, 7 with the base model on the **AI model** page. Your
message passes through them before the base model replies: it goes to the last model added first,
each reply goes to the model added before it, and the first one's reply goes to the base model,
which answers in the chat. Only the base model's reply is shown or kept in your chats.

- Each model is **On this Mac** (a server with an OpenAI-compatible API, such as Nova Chat's own
  llama-server at `http://127.0.0.1:8080/v1`, LM Studio or Ollama) or an **Online API**, with its
  base URL, an optional API key (saved with your settings), the model ID, and instructions of its
  own, such as *"Translate the message into English."* **Edit** and **Remove** change the list.
- **Chain flow** chooses what each model after the first is sent:
  - **Message + Previous Prompt**: your message and the reply of the model before it.
  - **Previous Prompt only**: only the reply of the model before it.
- The instructions on the **Instructions** page go only to the base model. Its sources go to every
  model in the chain as well.

Each model in the chain adds the time of one reply before the base model starts answering.

### Settings at a glance

| Page | What's on it |
| --- | --- |
| **AI model** | **On this Mac** or **Online API**: the model, its download, or the service, API key and model |
| **Appearance** | Text size, font, bold/italic/underline, and the opacity of the window, bubble and message box |
| **Layout** | Where the window and reply bubble sit, and whether they stay put or move out of the way |
| **Input** | **Typing** or **Speech**, what to listen to, and the language |
| **Shortcut** | The click-through and show/hide shortcuts |
| **Instructions** | How the AI should reply, and your sources |
| **Chain** | More models for each message to pass through |

The bottom of every page has **Update**, **Cancel** and **Save**.

## Privacy and your data

- With **On this Mac**, your messages, replies and sources go only to the model running on your Mac.
  Nova Chat uses the internet only to download llama.cpp and the models, and to check for a newer
  version when Settings is open.
- With an **Online API**, your messages, instructions and sources are sent to that service. The same
  goes for any online model in the chain.
- Speech is always turned into text on your Mac.

Everything Nova Chat keeps is in `~/Library/Application Support/NovaChat`:

| What | Where |
| --- | --- |
| Settings, including API keys (only your account can read it) | `usersettings.json` |
| Chats | `chats/` |
| The AI model, the speech model and the voice detector | `models/` |
| llama.cpp, when downloaded from GitHub | `llama.cpp/` |
| The local model's log | `~/Library/Logs/NovaChat/llama-server.log` |

Nova Chat doesn't use the Keychain, so macOS never asks to let it access your keychain, not even
after an update. Versions up to 1.1.2 kept the API keys in the Keychain instead: after updating from
one of those, enter the keys again in **Settings**. The old **Nova Chat** items can be deleted in
Keychain Access.

## Updating

From 1.2.0, the bottom of **Settings** shows whether a newer version is out. When one is, the label
says so and **Update** downloads its disk image and opens it: quit Nova Chat from the menu bar icon's
menu, then drag **Nova Chat** onto **Applications** to replace the old one. Otherwise the button is
off and the label says Nova Chat is up to date.

Versions up to 1.1.3 don't check for updates: download 1.2.0 once as in [Installing](#installing).

## Troubleshooting

**macOS says *"Nova Chat" Not Opened*.** That's expected the first time for each version. See
[Installing](#installing) for how to allow it.

**The shortcuts or the Dynamic modes stopped working after an update.** Each new version is signed
afresh, so macOS treats it as a different app: Input Monitoring can still show as on in System
Settings without applying to the new version. Reset the permission and open Nova Chat again, so it
asks afresh:

```sh
tccutil reset ListenEvent com.novachat.NovaChat
tccutil reset Accessibility com.novachat.NovaChat
```

Or, in **System Settings → Privacy & Security → Input Monitoring**, select Nova Chat, remove it with
**−**, and add `/Applications/Nova Chat.app` again with **+**.

**The chat says *"Setup isn’t finished yet, so I can’t reply."*** Send a message to open setup
again, or choose **Online API** in **Settings → AI model**.

**The status says *Local model offline*.** The model on your Mac didn't start. **Settings → AI model**
shows the model and llama.cpp it uses, and the log at `~/Library/Logs/NovaChat/llama-server.log`
says what went wrong.

**Listening to the sound on the Mac doesn't work.** It needs macOS 14.2 or later. On an older
version, listen to a microphone instead.

**The window is gone.** Closing it quits Nova Chat: open it again from Applications, and next time
tap **⌃ Control** to hide it.

## Uninstalling

Quit Nova Chat and drag **Nova Chat** from Applications to the Bin. To also remove your chats,
settings, API keys and the downloaded models, and reset its permissions:

```sh
rm -rf ~/Library/Application\ Support/NovaChat ~/Library/Logs/NovaChat
tccutil reset All com.novachat.NovaChat
```

If llama.cpp was installed with Homebrew, `brew uninstall llama.cpp` removes it.
