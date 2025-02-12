# Mac usage notes

## Function keys

[How to use the function keys on your Mac](https://support.apple.com/en-us/102439)
either:

- Press and hold the Function (Fn)/Globe keyNo alt supplied for Image while
  pressing a function key.
- Change the default behavior of the keys
    1. Choose Apple menu  > System Settings.
    2. Click Keyboard in the sidebar.
    3. Click the Keyboard Shortcuts button on the right.
    4. Click Function Keys in the sidebar.
    5. Turn on “Use F1, F2, etc. keys as standard function keys”.

## Keyboard shortcuts

### Cut, copy, paste, and other common shortcuts

Much of this is from
[Mac keyboard shortcuts](https://support.apple.com/en-us/102650)

- `Command` + `X`: Cut the selected item and copy it to the Clipboard.
- `Command` + `C`: Copy the selected item to the Clipboard. This also works for files
  in the Finder.
- `Command` + `V`: Paste the contents of the Clipboard into the current document or
  app. This also works for files in the Finder.
- `Command` + `Z`: Undo the previous command. You can then press Shift-`Command` + Z to
  Redo, reversing the undo command. In some apps, you can undo and redo multiple
  commands.
- `Command` + `A`: Select All items.
- `Command` + `F`: Find items in a document or open a Find window.
- `Command` + `G`: Find Again: Find the next occurrence of the item previously found.
  To find the previous occurrence, press Shift-`Command` + `G`.
- `Command` + `H`: Hide the windows of the front app. To view the front app but hide
  all other apps, press `Option` + `Command` + `H`.
- `Command` + `M`: Minimize the front window to the Dock. To minimize all windows of
  the front app, press `Option` + `Command` + `M`.
- `Command` + `O`: Open the selected item, or open a dialog to select a file to open.
- `Command` + `P`: Open a print dialog so that you can print the current document.
- `Command` + `S`: Save the current document.
- `Command` + `T`: Open a new tab.
- `Command` + `W`: Close the front window. To close all windows of the app, press
  `Option` + `Command` + `W`.
- `Option` + `Command` + `Esc`: Force quit an app.
- `Command` + `Space bar`: Show or hide the Spotlight search field. To perform a
  Spotlight search from a Finder window, press `Command` + `Option` + `Space bar`. (If you
  use multiple input sources to type in different languages, these shortcuts
  change input sources instead of showing Spotlight.
  ([Learn how to change a conflicting keyboard shortcut](https://support.apple.com/guide/mac-help/change-a-conflicting-keyboard-shortcut-on-mac-mchlp2864/mac).)
- `Control`+ `Command` + `Space bar` or `Fn` + `E`: Show the Character Viewer,
  from which you can choose emoji and other symbols.
- `Control`+ `Command` + `F`: Use or stop using the app in full screen, if supported by
  the app.
- `Space bar`: Use Quick Look to preview the selected item.
- `Command` + `Tab`: Switch to the next most recently used app among your open apps.
<!-- Need to escape the grave accent and format it. Using html is the most reliable way to do that. -->
<!-- markdownlint-disable-next-line MD033 -->
- `Command` + <code>`</code> (Grave accent): Switch between the windows of the app you're using.
- Screen shots [Learn more about screenshots](https://support.apple.com/en-us/102646).
  - `Shift` + `Command` + `5`: In macOS Mojave or later, take a screenshot or make a screen
      recording.
  - `Shift` + `Command` + `3`: Captures the entire screen and saves it to the desktop.
  - `Shift` + `Command` + `4`: Captures a selection and saves it to the desktop.
- `Shift` + `Command` + `N`: Create a new empty folder in the Finder.
- `Control`+ `Command` + `N`: Create a new folder that contains the currently selected
  items.
- `Command` + `,` (Comma): Open settings (preferences) for the front app.

### More text editing keys

- `delete`: Deletes the character to the left, i.e., Linux backspace.
- `Fn` + `delete`: Delete the character to the right, i.e., Linux delete.

### Moving on the line and up an down lines

These key chords behave different in different apps.

In VS Code, they move both the display and where text is inserted. In some
documents, they seem to move based on document structure. For example, in this
Markdown document, `Control`+ down-arrow can move to the last section and, in
that case, pressing these keys a second time move to the bottom of the document.

In Notes, they move what text is displayed but do not move where text is
inserted.

- `Fn` + `right-arrow`: In VS Code, this moves the cursor to the end of line but in
  the Notes app, this displays the end of line but does *not* change the text
  insertion point.
- `Fn` + `left-arrow`: Depends on the app, Moves the cursor to the beginning of the
  line.
- `Fn` + `down-arrow`: Moves to the bottom of the window or document.
- `Fn` + `up-arrow`: Moves to the top of the window or document.

## Enter line break in apps where `Return` means Send

- `Shift` + `Return` Used in Signal and Messages

## Mouse command when editing text

- In most apps (not VS Code), click on the word then `Control` + click to get
  suggestions.

## Apple Mail app

- `option` + `delete` Deletes highlighted message without advancing to the next
  message.
- `Command` + `Shift` + `N`: Refresh mailbox.
- Two-finger left or right swipe on a message header exposes actions, like
  delete, mark as unread, etc.

## Messages app

- `Control` + Click on a message: Displays options for tapback, edit message,
  delete, reply
- [Line break](#enter-line-break-in-apps-where-return-means-send).

## Safari

- `Control` + Click on a Link: Opens in a new tab
- Two finger right swipe in tab: Closes tab
- `Command` + `Z`: Undo close tab

## VS Code

[Keyboard shortcuts for macOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)

- `Option` + `Command` + `F`: Find and replace.
- `Shift` + `Command` + `\`: Jump to matching bracket
- `Control` + `G`: Jump to line number
- `Command` + `K` + `S`: Open Keyboard Shortcuts
- `Fn` + `F1` or `Command` + `Shift` + `P`: Open Command

VS Code steals the default minimize `Command` + `M`. I found no shortcut that
uses only this, but some use it in conjunction with other keys, like `Command` +
`K` + `M` for "Change Language Mode" and `Shift` + `Command` + `M` for "Toggle
Problems".

## OCR

This depends upon displaying the photo in the `Preview` app and so do not work
for a photo in a shared album.

[Interact with text in a photo using Live Text in Preview on Mac](https://support.apple.com/guide/preview/interact-with-text-in-a-photo-prvw625a5b2c/mac)

### From email

Double click on the picture to open the Preview app.

### From Photos

- `Control` + Click on the photo
- Click on `Edit With`
- Click on `Preview` (NB: you'll see a shortcut `Command` + `Return`. It doesn't
  work.)

### Once in Previews

- `Tools` > `Text Selection`
- Use "drag" to select the desired text
- Copy, e.g., with `Command` + `C`

## Photo App

This only works for a local photo and does not work for a photo in a shared
album.

- To add a title or subject, click on the `i` in the tool bar. A window will
  open. Click inside `Title` or `Caption` or `Keywords`, and type. Close the
  window.

[Keyboard shortcuts and gestures in Photos on Mac](https://support.apple.com/guide/photos/keyboard-shortcuts-and-gestures-pht9b4411b24/mac)

## Installed

### Install VS Code

### `exiftool`

[`exiftool`](https://exiftool.org)

- macOS will display "Apple could not verify .... is free of malware ..." and
  will offer to "Move to Trash". Click `Done`.
- Open `System Settins` > `Privacy & Security`
- At the bottom, under `Security`, you should see the package you tried to
  install. Click on `Open Anyway` and the click on it again. Then enter your
  local password (not for the Apple account).
- A window should open that lets you install the app, including changing the
  directory.

## Terminal app

Apple wants me to use zsh because it hooks into Apple thingies.

To avoid the annoying warning about zsh when starting bash, put this into
`~/.zshenv`:

```shell
# See https://support.apple.com/en-us/102360
export BASH_SILENCE_DEPRECATION_WARNING=1
```

Sometimes `Control` + `C` stops working and you'll hear a beep. When this
happens, try `Command` + `.`

When you exit the shell, `Terminal` will stay running. To prevent this, in the
`Terminal` settings `Profiles`, change "When the shell exits" to "Close if shell
exited cleanly".

## Photos in Photos app

The picture files are in `"${HOME}/Pictures/Photos Library.photoslibrary/"`
The double quotes are necessary (that, or escape the space).

For one picture, there are at least six files:

1. ./resources/renders/0/0FB91698-EF23-48BF-96A9-F7902A77E118_1_201_a.jpeg
2. ./resources/renders/0/0FB91698-EF23-48BF-96A9-F7902A77E118.plist
3. ./resources/derivatives/0/0FB91698-EF23-48BF-96A9-F7902A77E118_1_105_c.jpeg
4. ./resources/derivatives/masters/0/0FB91698-EF23-48BF-96A9-F7902A77E118_4_5005_c.jpeg
5. ./resources/caches/compute/0/0FB91698-EF23-48BF-96A9-F7902A77E118_5_5_c_14.dat
6. ./originals/0/0FB91698-EF23-48BF-96A9-F7902A77E118.jpeg

-----

1. A version of \#6 but cropped as the Photo app displays it
2. "renders" plist is a XML document. It contains a date and an encoded data
   block. Don't know what it is, but it's still gibberish when decoded with
   base64.
3. A smaller version of \#1
4. A smaller version of \#3
5. The `.dat` file has the title embedded in it.
6. The original picture without edits. If the picture has GPS data, at least for
   `.jpeg` files, it is here.

./scopes/cloudsharing/data contains some (all?) of the photos in shared albums.

Launching the Preview app from the zsh command line (not bash):

```shell
open -a Preview -- ./originals/0/0FB91698-EF23-48BF-96A9-F7902A77E118.jpeg
```

### Things to check out

[iCloud Photo downloader](https://github.com/icloud-photos-downloader/icloud_photos_downloader)

To copy from iPhone to Mac or NAS
[PhotoSync – transfer photos on App store](https://apps.apple.com/us/app/photosync-transfer-photos/id415850124)
[Visit photosync-app.com for a complete feature list.](https://photosync-app.com)
