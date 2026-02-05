# iTerm2 Configuration Backup

This directory contains iTerm2 preferences and settings for easy restoration on a new machine.

## Files Included

- `com.googlecode.iterm2.plist` - Binary plist containing all iTerm2 settings (native format)
- `com.googlecode.iterm2.xml` - XML version of the same settings (human-readable)

## What's Included in This Configuration

### Profile Settings
- **Font**: Monaco 12pt
- **Terminal Type**: xterm-256color
- **Background**: Light mode (0.98 gray)
- **Unlimited Scrollback**: Enabled
- **Prompt Before Closing**: Disabled
- **Visual Bell**: Enabled (silent)

### Color Scheme
Custom color palette with both light and dark mode support:
- Separate colors for Light and Dark Mode enabled
- Custom ANSI colors configured

### Keyboard Shortcuts
- Custom key bindings for navigation
- Option+Left Arrow: Move word backward
- Option+Right Arrow: Move word forward
- Cmd+Left Arrow: Beginning of line
- Cmd+Right Arrow: End of line
- Option+Backspace: Delete word
- Cmd+Backspace: Delete line

### Mouse/Trackpad Gestures
- Three-finger swipe left: Previous tab
- Three-finger swipe right: Next tab
- Three-finger swipe up: Next window
- Three-finger swipe down: Previous window
- Middle click: Paste from clipboard
- Right click: Context menu

## Installation on a New Machine

### Prerequisites
1. Install iTerm2 on your new machine:
   ```bash
   # Using Homebrew
   brew install --cask iterm2
   ```

### Method 1: Direct Restore (Recommended)

1. **Quit iTerm2** if it's running:
   ```bash
   osascript -e 'quit app "iTerm"'
   ```

2. **Copy the plist file** to the preferences directory:
   ```bash
   cp com.googlecode.iterm2.plist ~/Library/Preferences/
   ```

3. **Clear the preferences cache** (important!):
   ```bash
   defaults read com.googlecode.iterm2
   ```

4. **Launch iTerm2** - your settings should be restored.

### Method 2: Using defaults import

1. **Quit iTerm2** if it's running.

2. **Import the settings**:
   ```bash
   defaults import com.googlecode.iterm2 com.googlecode.iterm2.plist
   ```

3. **Launch iTerm2**.

### Method 3: Using iTerm2's Built-in Import (GUI)

1. Open iTerm2
2. Go to **iTerm2 > Preferences** (or press `Cmd+,`)
3. Click on **General** tab
4. Under **Preferences**, check "Load preferences from a custom folder or URL"
5. Browse to this directory and select it
6. Restart iTerm2

## Verifying Installation

After installation, verify your settings are loaded:

1. Check that your font is Monaco 12pt (Preferences > Profiles > Text)
2. Verify color scheme (Preferences > Profiles > Colors)
3. Test keyboard shortcuts (Option+Arrow keys for word navigation)
4. Test trackpad gestures if available

## Updating This Backup

To update this backup with current iTerm2 settings:

```bash
# Copy current settings
cp ~/Library/Preferences/com.googlecode.iterm2.plist /path/to/this/directory/

# Generate readable XML version
plutil -convert xml1 com.googlecode.iterm2.plist -o com.googlecode.iterm2.xml
```

## Troubleshooting

### Settings not loading?
1. Make sure iTerm2 is completely quit before copying the plist
2. Try clearing the cache: `killall cfprefsd`
3. Restart your Mac if settings still don't apply

### Keyboard shortcuts not working?
- Some shortcuts may conflict with system shortcuts
- Check System Preferences > Keyboard > Shortcuts
- Verify in iTerm2: Preferences > Keys

### Colors look different?
- Ensure "Use separate colors for Light and Dark Mode" matches your preference
- Check your system appearance (Light/Dark mode)

## Included Key Mappings Summary

| Shortcut | Action |
|----------|--------|
| Ctrl+2 | Send NULL |
| Ctrl+3 | Send ESC |
| Ctrl+4 | Send ^\ |
| Ctrl+5 | Send ^] |
| Ctrl+6 | Send ^^ |
| Ctrl+7 | Send ^_ |
| Ctrl+8 | Send DEL |
| Ctrl+- | Send ^_ |
| Shift+Up | Send [1;2A |
| Shift+Down | Send [1;2B |
| Shift+Left | Send [1;2D |
| Shift+Right | Send [1;2C |
| Option+Left | Move word backward |
| Option+Right | Move word forward |
| Cmd+Left | Beginning of line |
| Cmd+Right | End of line |
| Option+Backspace | Delete word backward |
| Cmd+Backspace | Delete to beginning of line |

---

*Last updated: February 5, 2026*
*iTerm2 version: 3.6.6*
