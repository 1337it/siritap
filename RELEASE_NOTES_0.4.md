Control your Mac by voice, select with a triple tap, and a fix for clicks after a swipe.

**Website:** https://siritap.leet.ae

**Download:** `Siritap-0.4.dmg` below. Open it and drag Siritap into Applications, replacing the old copy. Signed and notarized by Apple. macOS 14 or later, Apple silicon and Intel.

### New: Control the Mac by voice
Choose **Control the Mac (hold to talk)** for any button in Settings → Buttons (dictation stays available as its own action). Hold the button and say what you want:
- "open safari and go to github.com", "new tab then search for flights to london", "open notes and type buy milk"
- "louder", "next song", "pause", "mute", "next tab", "go back", "reload", "zoom in", "scroll down three pages", "dark mode"
- "click sign in", "press command shift T", "find invoice on this page", "run my morning routine shortcut", "lock the screen"

It acts **while you are still speaking**: commands that can't go on any further, such as "louder" or "next tab", run the moment you say them, and "louder… louder… again" turns it up three times. A command that takes a name or text runs at the next "and…" or a short pause. Locking, quitting and closing always wait for the pause, so a half-heard sentence can't set them off. The words and each action appear in a small pill on screen.

Siritap understands around 50 kinds of command by itself, instantly. On Macs with Apple Intelligence turned on (macOS 26 or later), wording it doesn't know goes to Apple's on-device model. Only requests that start like a command ("open…", "crank…", "grab…") reach the model, and only names you actually said can be used, so a remark like "the lock on my bike is broken" does nothing. Everything happens on your Mac.

### New: Triple tap to select
Tap the middle of the touch surface three times quickly (or press the click three times): the mouse button stays held, so moving selects files or text, and you can lift and touch again to keep going. Tap once to let go. On by default; turn it off with **Triple-press to select** on the Pointer page.

### Fixed
- **Clicking after a swipe.** If a swipe began near an edge of the touch surface, a click in the middle could press that edge's arrow key instead of clicking. A click now always clicks after the pointer has moved.

### After updating
macOS may ask for Accessibility, the microphone or Speech Recognition again. Asking for dark mode by voice asks once for permission to control System Events.

### Known limits
- "Click <name>" needs apps that describe their buttons to macOS Accessibility.
- Web searches open Google in your browser.
- With triple tap, the first two taps are a double-click: start on empty space or in text, not on a file you don't want to open.
- Apple's model is used only when Apple Intelligence is on; without it, Siritap's own commands still work.

**SHA-256:** `e55fb24f5e8ccbe847646ef5aa117526c1ef9a7ce30008efe0b35cff6a9ccebb`
