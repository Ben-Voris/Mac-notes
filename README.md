# Mac usage notes

This is <https://github.com/Ben-Voris/Mac-notes.git>.

A prettier version is at <https://ben-voris.github.io/Mac-notes/>.

## Function keys

[How to use the function keys on your Mac](https://support.apple.com/en-us/102439)
either:

- Press and hold the Function (Fn)/Globe while pressing a function key.
- To change the default behavior of the keys
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
- `Command` + `Z`: Undo the previous command. You can then press `Shift`
   \+ `Command` + `Z` to Redo, reversing the undo command. In some apps, you
   can undo and redo multiple commands.
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

- `Delete`: Deletes the character to the left, i.e., Linux backspace.
- `Fn` + `Delete`: Delete the character to the right, i.e., Linux delete.

### Moving on the line and up an down lines

These key chords behave different in different apps.

In VS Code, they move both the display and where text is inserted. In some
documents, they seem to move based on document structure. For example, in this
Markdown document, `Control` + `down-arrow` can move to the last section and, in
that case, pressing these keys a second time move to the bottom of the document.

In Notes, they move what text is displayed but do not move where text is
inserted.

- `Fn` + `right-arrow`: In VS Code, this moves the cursor to the end of line but in
  the Notes app, this displays the end of line but does *not* change the text
  insertion point.
- `Fn` + `left-arrow`: Depends on the app, Moves the cursor to the beginning of the
  line.
- `Fn` + `down-arrow`: Moves to the bottom of the window or document or, in
  VS Code and Safari, Page Down
- `Fn` + `up-arrow`: Moves to the top of the window or document or, in VS Code
  and Safari, Page Up.

## Create a line break in apps where `Return` means Send

- `Shift` + `Return` Used in Signal and Messages

## MacBook Trackpad setup

`Settings` > `Trackpad`

Remember to use both hands. For example, for me, swiping from the left is easier
with the left hand. When selecting a large amount of text, it is possible to
start the "click drag" with one hand and extend it with the other.

### `Point & Click`

- Set `Click` to `Medium` or `Firm`.
- Enable `Force Click and haptic feedback`.
- Set `Look up & data detectors` to `Force Click with One Finger`.
- Set `Secondary click` (i.e., "right click") to `Click with Two Fingers`
- Disable `Tap to click`. If this is enabled, a light tap is registered as a
  click.

Force click is a longish hard press that, if haptic feedback is enabled, gives
a distinct "bump" as feedback.

An example of a "data detector" is a dictionary lookup that can appear when a
word is selected that is in the dictionary. See
[dictionary lookup](#dictionary-lookup).

### Scroll & Zoom

Enable

- `Natural scrolling` / `Contents track finger movement`
- `Zoom in or out` / `Pinch with two fingers`
- `Smart Zoom` / `Double tab with two fingers`
- `Rotate` / `Rotate with two fingers`

### More Gestures

- Set `Swipe between pages` to `Scroll Left or Right with Two Fingers`
- Set `Swipe between full-screen applications` to
  `Swipe Left or Right with Three fingers`
- Enable `Notification Center` /
  `Swipe left from the right edge with two fingers`
- Set `Mission Control` to `Swipe Up with Three Fingers`. This shows a set
  of small views of the currently running applications. Clicking on one
  brings that application to the foreground.
- Set `App Exposé` to `Swipe Down with Three Fingers` This exposes the files
  opened by the current foreground application. Swipe up with three fingers
  to hide this.
- Set `Launchpad` to `Pinch with thumb and three fingers`
- Set `Show Desktop` to `Spread with thumb and three fingers`

## Mouse command when editing text

- In most apps (not VS Code), click on the word then `Control` + Click to get
  suggestions.

## Mouse command when reading text

### Dictionary lookup

Dictionary lookup can be enabled by turning `System Settings` > `Trackpad`.

Sometimes this does not work, even for words that are in the dictionary. And
then it starts working.

Unfortunately, the mouse command is not consistent. All start with clicking on
a on a word to select it, then a "Force Click" but with a different number of
fingers.

- `Mail`, `Safari` and `Visual Studio`  - A three-finger "Force Click"
- `Visual Studio` and `Preview` - A one-finger "Force Click"
- `Preview` - A two-finger "Force Click" followed by scrolling to `Look Up`
  and then a single click

## Apple Mail app

- `Option` + `Delete` Deletes highlighted message without advancing to the next
  message.
- `Command` + `Shift` + `N`: Refresh mailbox.
- `Command` + `Shift` + `+`: Increase displayed size of message content (zoom
  in).
- `Command` + `Shift` + `-`: Decrease displayed size of message content (zoom
  out).
- Two-finger left or right swipe on a message header exposes actions, like
  delete, mark as unread, etc.

NB: Something is leaving deleted messages in the inbox. They are marked as read.
Wtf?

## Messages app

- `Control` + Click on a message: Displays options for tapback, edit message,
  delete, reply
- [Enter a line break](#create-a-line-break-in-apps-where-return-means-send).

## Safari

- `Control` + Click on a Link: Opens in a new tab
- Two finger right swipe in tab: Closes tab
- `Command` + `Z`: Undo close tab
- Long press on `+` (new tab) shows recently closed tabs. Clicking on one
  reopens it.
- Two finger swipe left and right on the trackpad are equivalent to the left
  and right arrows (`Show the previous page` and `Show the next page`).

## VS Code

[Keyboard shortcuts for macOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)

- `Option` + `Command` + `F`: Find and replace.
- `Shift` + `Command` + `\`: Jump to the matching bracket
- `Control` + `G`: Jump to line number
- `Command` + `K` + `S`: Open Keyboard Shortcuts
- `Fn` + `F1` or `Command` + `Shift` + `P`: Open Command
- `Control` + `P`: Previous line. Same as the up arrow key.
- `Control` + `N`: Next line. Same as the down arrow key.
- [Page up, page down](#moving-on-the-line-and-up-an-down-lines)

VS Code steals the default minimize `Command` + `M`. I found no shortcut that
uses only this, but some use it in conjunction with other keys, like `Command` +
`K` + `M` for "Change Language Mode" and `Shift` + `Command` + `M` for "Toggle
Problems".

### Opening a file in VS Code from shell

At the VS Code command prompt, type `shell` and select
`Install 'code' command in PATH`, then follow its prompt. You can then enter
commands like these:

```shell
code ./
code file-name
```

Contrary to what it says, on MacOS, this command dos not update PATH but creates
this:

`/usr/local/bin/code: symbolic link to /Applications/Visual Studio Code.app/Contents/Resources/app/bin/code`

Or use the `open(1)` command, as in this example:

```shell
open --new -a "Visual Studio Code" --args --new-window file-name
```

It is necessary to tell `open(1)` to open a new window (`--new`) *and* to tell
VS Code to create a new window with `--new-window`.

### Open a directory with VS Code from Finder

Use `Automator` to create a `Quick Action` for Files and Folders.

[Open a Folder in VS Code through Finder in MacOS](https://stackoverflow.com/questions/64040393/open-a-folder-in-vscode-through-finder-in-macos)

1. Start `Automator`
2. Click on `Quick Action`, Click on `Choose`
3. Set `Workflow receives current` to `Files or Folders` in `Finder`
4. Click on `Image` and `Choose`. This opens a Finder-type window
5. Click on `Application`
6. Click on `Visual Studio Code`, click on `Choose` Note that `Image` is now
   `Custom`
7. Find `Open Finder items` in the Library
8. Clock on `Open With`, then find `Visual Studio Code`
9. Click on `File` > `Save` (or `Command` + `S`) and enter something like "Open
   with Visual Studio Code".

To use what you just created:

1. `Control` + Click on the item
2. Click on `Quick Actions`
3. Click on the name you gave to the action.

## OCR

This depends upon displaying the photo in the `Preview` app and so does not work
for a photo that is in a shared album.

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

[Keyboard shortcuts and gestures in Photos on Mac](https://support.apple.com/guide/photos/keyboard-shortcuts-and-gestures-pht9b4411b24/mac)

This only works for a local photo and does not work for a photo in a shared
album.

- To add a title or subject, click on the `i` in the tool bar. A window will
  open. Click inside `Title` or `Caption` or `Keywords`, and type. Close the
  window.

## What to install

Some iOS apps, like Feedly, Netflix, Youtube, etc. are not available for Mac.
For these, visit the page, click on the `Share` (up arrow) and click on `Add to
Dock`. Links that are added to the dock also appear in the Apps folder.

### To install VS Code

<https://code.visualstudio.com/download>

Add these extensions

|                                                                                                      |                                  |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- |
| [Bash IDE](mads-hartmann.bash-ide-vscode)                                                            | `mads-hartmann.bash-ide-vscode`  |
| [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks)               | `alefragnani.Bookmarks`          |
| [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)                      | `ms-vscode.cpptools`             |
| [C/C++ Themes](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-themes)        | `ms-vscode.cpptools-themes`      |
| [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)   | `DavidAnson.vscode-markdownlint` |
| [Rewrap Revived](https://marketplace.visualstudio.com/items?itemName=dnut.rewrap-revived)            | `dnut.rewrap-revived`            |
| [Sort JSON objects](https://marketplace.visualstudio.com/items?itemName=richie5um2.vscode-sort-json) | `richie5um2.vscode-sort-json`    |
| [Sort lines](https://marketplace.visualstudio.com/items?itemName=Tyriar.sort-lines)                  | `Tyriar.sort-lines`              |
| [Spell Right](https://marketplace.visualstudio.com/items?itemName=ban.spellright)                    | `ban.spellright`                 |

Sign into GitHub.

### To install exiftool

[`exiftool`](https://exiftool.org)

macOS will display "Apple could not verify .... is free of malware ..." and
will offer to "Move to Trash". Click `Done` and follow the steps in
[Removing a file from quarantine](#removing-a-file-from-quarantine).

### To install SQLLite browser

Download at <https://download.sqlitebrowser.org>

See <https://github.com/sqlitebrowser/sqlitebrowser/>.

### To install Tor Browser

<https://www.torproject.org/download/>

### To install Signal

<https://signal.org/download/macos/>

Existing chats from other devices are not synchronized.

### To install Firefox

<https://www.mozilla.org/en-US/firefox/mac/>

- Add [Privacy Badger](https://addons.mozilla.org/en-US/firefox/addon/privacy-badger17/)
- Add [uBlock Origin](https://addons.mozilla.org/en-US/firefox/addon/ublock-origin/)
  - <https://github.com/gorhill/uBlock#ublock-origin>

### To install DigiKam

A photo cataloging tool I used on Linux

<https://www.digikam.org/download/>

Installing this requires
[removing the installer from quarantine](#removing-a-file-from-quarantine).

### GPSBabel

A GPS format converter.

<https://github.com/gpsbabel/gpsbabel>

Installing this requires
[removing the installer from quarantine](#removing-a-file-from-quarantine).

### OpenJDK (Java)

Download the tar from <https://jdk.java.net/23/>

Install in /usr/local with

```shell
sudo tar -xf ~/Downloads/toInstall/openjdk-23.0.2_macos-aarch64_bin.tar.gz -C /usr/local/bin/
```

Or put it in your home directory with

```shell
tar -xf ~/Downloads/toInstall/openjdk-23.0.2_macos-aarch64_bin.tar.gz -C ~/
```

Then add this to your `.bashrc` or similar:

```shell
export JAVA_HOME=/usr/local/bin/jdk-23.0.2.jdk/Contents/Home/
PATH="${PATH}:${JAVA_HOME}/bin:"
```

### Garmin programs

- Garmin Basecamp for Mac
- Garmin Express - Used this to update firmware on Alpha 100 GPS.
- inReach Sync - Updates firmware. Also, syncs contacts and messages set in
  <https://explore.garmin.com/Messages>

#### Installed but not sure if they're useful

- Garmin MapInstall
- Garmin MapManager
- Garmin WebUpdater for Mac - This should update the e-collars but gives a
  warning about running on a Mac.

### Install `osxphotos`

Requires [`Macports`](#macports).

[`osxphotos`](https://github.com/RhetTbull/osxphotos) gives information about
files stored in the photo database.

```shell
sudo port install osxphotos
```

### From Mac App store

- Amazon Prime Video
- Orbit
- Plain Paste
- Speedtest
- Strongbox
  - After installing it and Firefox, install its Firefox extension by opening
    <https://addons.mozilla.org/en-GB/firefox/addon/strongbox-autofill/> in
    Firefox.
  - `System Settings` > `Touch ID & Password` set
    `Use Touch ID for autofilling passwords` on.
  - `System Settings` > `Autofill from` > `AutoFill & Password`, turn `Passwords` off
    and `Strongbox` on, and list `Strongbox` in `Setup Code In`
  - Verify that Strongbox is listed under `Login Items & Extensions` >
    `Open at Login`
- Swift Playground
- Xcode

## Terminal app

Apple wants me to use zsh because it hooks into Apple thingies.

To avoid the annoying warning about zsh when starting bash, put this into
`~/.zshenv`:

```shell
# See https://support.apple.com/en-us/102360
export BASH_SILENCE_DEPRECATION_WARNING=1
```

Sometimes `Control` \+ `C` stops working and you'll hear a beep. When this
happens, try `Command` \+ `.`

When you exit the shell, `Terminal` will stay running. To prevent this, in the
`Terminal` settings `Profiles`, change "When the shell exits" to "Close if shell
exited cleanly".

### Terminal Keyboard shortcuts

[Keyboard shortcuts in Terminal on Mac](https://support.apple.com/guide/terminal/keyboard-shortcuts-trmlshtcts/mac)

Do *not* confuse `Command` with `Control`. For example, `Command` + `D` splits the terminal window
into two panes but `Control` + `D` is an end-of-file.

The keyboard shortcuts cannot be disabled. They can be assigned to a different chord.

 (`Shift` + `Command` + `D` undoes the split created by `Command` + `D`.)

### Copying file names from Finder to Terminal

First, [select a file or files in Finder](#selecting-files-in-finder), then drag
the files to a Terminal window using `Command` \+ Click, much like
[moving files in Finder](#moving-files-in-finder).

## Accessing the Photo Library

Try pointing [SQL Lite browser](#to-install-sqllite-browser) at
`database/Photos.sqlite`.

The picture files are in `"${HOME}/Pictures/Photos Library.photoslibrary/"`
The double quotes are necessary (that, or escape the space).

For one picture, with some edits, there are six files.
See [`exiftool` output for an example jpeg](exiftool-example-output.md).

`scopes/cloudsharing/data` contains at least some (all?) of the photos from
shared albums.

This command launches the Preview app from the zsh (not bash) command line:

```shell
open -a Preview -- "${HOME}/Pictures/Photos Library.photoslibrary/originals/0/0FB91698-EF23-48BF-96A9-F7902A77E118.jpeg
```

See [`osphotos`](#install-osxphotos)

If you have the full path to the photo, the terminal `open` command will open
the preview app.

### Things to check out for Photos

[iCloud Photo downloader](https://github.com/icloud-photos-downloader/icloud_photos_downloader)

To copy from iPhone to Mac or NAS
[PhotoSync – transfer photos on App store](https://apps.apple.com/us/app/photosync-transfer-photos/id415850124)
[Visit `photosync-app.com` for a complete feature list.](https://photosync-app.com)

#### Photo Exifer app

[Photo Exifer](https://www.fireebok.com/photo-exif-for-ios.html) claims to
import XMP data to the Photos app. See
[How to import XMP sidecars to Photos on Mac?](https://www.fireebok.com/resource/how-to-import-xmp-sidecars-to-photos-on-mac.html)

> Photo Exifer is compatible with extensible metadata files, supporting XMP
> files from Apple Photos and JSON files from Google Photos. It allows you to
> read photo metadata from XMP and JSON files and write it back to the
> corresponding photos

Photo Exifer likely cannot write files to a RAW file. It does not create an XMP file.

#### `mlds(1)`

`mdls` lists the metadata attributes for the specified file

It will display GPS info, etc. from a photo that has data.

Note that GPS data added to a photo using the Photos app is not written to the file.

## Controlling the dock

These use `defaults(1)` to "access the Mac OS X user defaults system".

### Prevent rearranging the dock

When using the trackpad, and the default configuration, I find it too easy to
accidentally rearrange the dock. Here's a command to prevent that.

```shell
defaults write com.apple.Dock contents-immutable -bool true && killall Dock
```

When this `contents-immutable` is set, apps cannot be drug into the dock.

### Allow rearranging the dock

```shell
defaults write com.apple.Dock contents-immutable -bool false && killall Dock
```

`defaults` can also be used to control whether one can change the docks's
position `com.apple.Dock position-immutable` and size
`com.apple.Dock size-immutable`.

### Example of using `defaults` to read a value

```shell
defaults read com.apple.Dock contents-immutable
```

## Homebrew vs. MacPorts

Homebrew and MacPorts are ways of getting open source tools running on a Mac.
Both are actively maintained.

Here are [Apple's ports](https://github.com/orgs/apple-oss-distributions/)

MacPorts and their [`mpstats`](https://ports.macports.org/port/mpstats/) tool
installed quickly but the first real package I installed,
[`shellcheck`](https://github.com/koalaman/shellcheck#user-content-installing),
took tens of minutes because it pulled so many dependencies - 465 packages per
`port echo rdepof:shellcheck` - some of which did not have prebuilt binaries.

[Thoughts on macOS Package Managers](https://saagarjha.com/blog/2019/04/26/thoughts-on-macos-package-managers/)
is in favor of MacPorts because it is more consistent with Linux and issues with
how the project is run. Notes that Homebrew is sometimes updated more quickly.
Though this is old, more recent pages link to it.

Responses to this
[Reddit](https://www.reddit.com/r/MacOS/comments/17e85da/homebrew_vs_macports/)
lean towards Homebrew because it usually carries over with less between MacOS
releases, though some note that can cause more problems than it fixes because
Homebrew depends on the MacOS libraries. Also notes that its refusal to share
`/usr/local` can cause problems.

### MacPorts

- [MacPorts install](https://www.macports.org/install.php)
- [Guide to MacPorts](https://guide.macports.org)
- [MacPorts GitHub](https://github.com/macports).

### Homebrew

- [Homebrew GitHub](https://github.com/Homebrew)
- [Homebrew Guide](https://brew.sh)

## List USB devices

```shell
system_profiler SPUSBDataType
```

Example output with Garmin e-collar attached:

```text
USB:

    USB 3.1 Bus:

      Host Controller Driver: AppleT8132USBXHCI

        Vendor-Specific Device:

          Product ID: 0x0003
          Vendor ID: 0x091e  (Garmin International)
          Version: 0.01
          Speed: Up to 12 Mb/s
          Location ID: 0x03100000 / 1
          Current Available (mA): 500
          Current Required (mA): 500
          Extra Operating Current (mA): 0

    USB 3.1 Bus:

      Host Controller Driver: AppleT8132USBXHCI

    USB 3.1 Bus:

      Host Controller Driver: AppleT8132USBXHCI
```

`ioreg -p IOUSB` lists information about the USB controllers but I can't get it
to display the attached device, as shown above.

## Recording the screen / Screen capture a problem

[How to record the screen on your Mac](https://support.apple.com/en-us/102618)

### Use the Screenshot app

1. Open the Screenshot app by pressing these three keys together: `Shift` +
   `Command` + `5`.
2. You should see an onscreen toolbar with three controls for capturing a still
   image of your screen, followed by these two controls for recording a video of
   the screen:
   - Record Entire Screen
   - Record Selected Portion. You can adjust the selected portion by dragging
     its borders with your mouse or trackpad.
3. Before starting your recording, you can click `Options` in the toolbar to
   change the recording settings:
    - To record your voice or other audio with the screen recording, choose a
      microphone.
    - To show a black circle around your pointer when you click, choose
      `Show Mouse Clicks`.
    - To set a recording timer, choose the number of seconds to wait before
      recording begins after you click `Record`.
    - To change where the recording will be saved after you stop recording,
      choose a different “Save to” location. By default, recordings are saved to
      your desktop.
4. To start recording, click the `Record` button in the Screenshot toolbar.
5. To stop recording, click the `Stop` button in the menu bar, or press
   `Command` + `Control` + `esc` (Escape).
6. When you see a thumbnail of the recording in the corner of your screen, click
   it to edit the recording. Or wait for the recording to save to your desktop.

[Learn more about using the Screenshot app](https://support.apple.com/guide/mac-help/mh26782/mac)

### Use QuickTime Player

1. Open QuickTime Player from your Applications folder.
2. From the menu bar, choose `File` > `New Screen Recording`. Or press
   `Control` + `Command` + `N`.
    - If you see the onscreen controls described above, screen recording on your
      Mac is performed by the Screenshot app. Follow the steps in the previous
      section.
    - If you see the Screen Recording window described below, screen recording
      on your Mac is performed by QuickTime Player. Continue to the next step.
3. Before starting your recording, you can click the arrow next to the `Record`
   button to change the recording settings:
    - To record your voice or other audio with the screen recording, choose a
      microphone. To monitor that audio during recording, adjust the volume
      slider. If you get audio feedback, lower the volume or use headphones with
      a microphone.
    - To show a black circle around your pointer when you click, choose
      `Show Mouse Clicks in Recording`.
4. To start recording, click the Record button and then
   take one of these actions:
    - Click anywhere on the screen to begin recording the entire screen.
    - Or drag to select an area to record, then click `Start Recording` within
      that area.
5. To stop recording, click the `Stop` button in the menu
   bar, or press `Command` + `Control` + `ecc` (Escape).
6. After you stop recording, QuickTime Player automatically opens the recording.
   You can now play, edit, or share the recording.

[Learn more about using QuickTime Player](https://support.apple.com/guide/quicktime-player/welcome/mac)

## Delete an app

`Finder` > `Applications`, click on the application, then press `Command` + `Delete`.

## External tips and tricks

[macOS Tips & Tricks](https://saurabhs.org/macos-tips)

## Removing a file from quarantine

If you try to open a file and get the message "Apple could not verify ... is
free of malware" and you're sure the file is safe, you can mark it as safe.

For an install programs

- macOS will display "Apple could not verify .... is free of malware ..." and
  will offer to "Move to Trash". Click `Done`.
- Open `System Settings` > `Privacy & Security`
- At the bottom, under `Security`, you should see the package you tried to
  install. Click on `Open Anyway` and the click on it again. Then enter your
  local password (not for the Apple account).
- A window should open that lets you install the app, including changing the
  directory.

Otherwise:

```shell
xattr -d com.apple.quarantine <file-name>
```

Or, enter this, with a trailing space.

```shell
xattr -d com.apple.quarantine
```

Then drag the file from `Finder` into the Terminal window. THe Terminal will
fill in the file path. Then press return.

If you accidentally issue `xattr -d` a second time for the same file, `xattr`
will print a message like this:

```text
xattr: <file>: No such xattr: com.apple.quarantine
```

## Finder

### Control what a new Finder window shows

`Finder` > `Settings` > `General`: Change the value of
`New Finder windows show`.

### Show path

To display the path as text, instead of a series of icons.

```shell
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true && killall Finder
```

### Finder copy path

- `Option` + Left-click (two fingers on track pad)
- While holding `Option`, select `Copy ... as Pathname`

### Finder directory navigation shortcuts

- `Command` + Up-Arrow to go up a directory level I.e., `cd ..`.
- `Command` + Down-Arrow to return to the previous directory. I.e., `cd -`.
- `Command` + `Shift` + `g` Opens a dialog that accepts a directory. This does
  not accept `..` or `../` but does accept `~`.
- `Command` + `Shift` + `h`. Jump to user's home directory. I.e., `cd ~`.

### Selecting files in Finder

Select a file by clicking on it. To select additional files, either `Command` \+
Click on each additional file or, to select a range of files, `Shift` \+ Click
on the last file in the range.

### Moving files in Finder

First [select a file or files](#selecting-files-in-finder). Next press `Command`
\+ Click on one of the selected files and drag the files to the desired
directory, which can be in the same Finder windows, another, Finder window or
the desktop. Once you start dragging, you can release the `Command` key.

To cancel the move, drop the selected file(s) back in their original location.

### Controlling what app opens a file

- `Control` \+ Click on a file
- Click on `Open With`
- If the desired app is listed, click on it, otherwise click on `Other...` and find the
  desired app.

To make this change permanent, even if the desired app is listed, do *not* pick
it from the list. Instead, click on `Other...`, find the desired app, check the
box `Always Open With`, then click on `Open`.

Though this change is registered somewhere and controls what app Finder uses to
open a file, it does not
[change the default app for the file type](#controlling-the-default-app-for-a-file-type).
(To be sure, I don't know all of the implications of the "default app".) It
might be that this only permanently changes the app that is used to open the
selected file (at least that's how I interpreted some discussion of a "resource
fork"). See the [ResForge](https://github.com/andrews05/ResForge) project, the
[Resource Fork](https://apple.fandom.com/wiki/Resource_fork) wiki, and
[File system formats available in Disk Utility on Mac](https://support.apple.com/guide/disk-utility/file-system-formats-dsku19ed921c/mac).

### Controlling the default app for a file type

- `Control` + Click on a file
- Click on `Get info`
- Expand `Open with`
- Click on the dropdown list of apps and select the desired app
- Click on `Change All...`
- This will display "Are you sure you want to change all similar documents to
  open with the application "*app-name*"? This change will apply to all
  documents with extension ".*extension*.". Click `Continue`.

## MacOS shell weirdnesses

See `/etc/bashrc` which leads to `/etc/bashrc_Apple_Terminal`.

## MacOS file system weirdness

- /etc: symbolic link to private/etc
- /tmp: symbolic link to private/tmp
- /var: symbolic link to private/var

Access to some directories where `ls(1)` shows the user should have access give
"Operation not permitted", even with root access.

```text
ls -ld -@ ~/Library/Safari
drwxr-xr-x@ 44 bvoris  staff  1408 Mar  9 16:38 /Users/bvoris/Library/Safari
  com.apple.quarantine  -1

: ls ~/Library/Safari
ls: Library/Safari: Operation not permitted

: sudo ls ~/Library/Safari
ls: Library/Safari: Operation not permitted
```

From `ls(1)`

> If the file or directory has extended attributes, the permissions field
> printed by the -l option is followed by a '@' character. Otherwise, if the
> file or directory has extended security information (such as an access control
> list), the permissions field printed by the -l option is followed by a '+'
> character.  If the -% option is given, a '%' character follows the permissions
> field for dataless files and directories, possibly replacing the '@' or '+'
> character.

Permission is granted in `System Settings` > `Privacy & Security`.

- `Photos`
- `Files and Folders`
- `Full Disk Access`

## MacOS network configuration

### DNS configuration

`/etc/resolv.conf`, which is a symbolic link to `/private/etc/resolv.conf`,
which is a symbolic link to `../var/run/resolv.conf` contains this:

```shell
#
# macOS Notice
#
# This file is not consulted for DNS hostname resolution, address
# resolution, or the DNS query routing mechanism used by most
# processes on this system.
#
# To view the DNS configuration used by this system, use:
#   scutil --dns
#
# SEE ALSO
#   dns-sd(1), scutil(8)
#
# This file is automatically generated.
```

The `nameserver` values listed in `resolv.conf` come from
`System Settings` > `Network` > `Details` (of current connection) > `DNS`

## Users and groups

MacOS does not use `/etc/passwd`.

To edit a user from `Settings` > `Control` + Click on the user name.
"Advanced Options..." should appear. Click on it.

From the command line, use `dscacheutil` and `dseditgroup` and maybe
`chsh` and `passwd`

### Change shell

```shell
sudo chpass -s /opt/local/bin/bash bvoris
```

Without `sudo`, this will fail with
`"chpass: /opt/local/bin/bash: non-standard shell"`

### Print information about a group

```shell
dscacheutil -q group -a name _developer
```

```shell
dscl . -read /Groups/_developer
```

### Print information about a user

```shell
dscacheutil -q user -a name bvoris
```

The output of this next command includes an encoded picture, so its very long.

```shell
dscl . -read /Users/bvoris
```

### members script

```shell
#!/bin/bash

# members -- list all members of a group
#
# SYNOPSIS
#   members groupname
#
# http://superuser.com/questions/279891/list-all-members-of-a-group-mac-os-x
#  by Arne
# Expected to work on Mac OS 10.5 and newer, tested on 10.6 and 10.7.
# It could be rewritten to work on 10.4 by using "dseditgroup -o checkmember"
# instead of "dsmemberutil checkmembership".
# By using dseditgroup, the script could also be extended to handle
# other Directory Service nodes than the default local node.
#

the_group="$1"
# Input check and usage
  if [[ $# != 1 || $1 == -* || $1 =~ [[:space:]] ]]; then
    echo "Usage: ${0##*/} groupname" >&2
    echo "Lists all members of the group." >&2
    exit 64
  elif (dsmemberutil checkmembership -U root -G "$the_group" 2>&1 \
    | grep "group .* cannot be found") >&2; then
    exit 1
  fi

# Check every user
exec dscl . -list /Users \
  | while read each_username
  do
    printf "$each_username "
    dsmemberutil checkmembership -U "$each_username" -G "$the_group"
  done \
    | grep "is a member" | cut -d " " -f 1
```

## man pages

Apples supports both `man` and `info` but `man -k` (search for a command) and
`whatis` always outputs "nothing appropriate".

Try `man makewhatis` and `man whatis`.

```shell
: echo $MANPATH
:/usr/share/man
```

```shell
 sudo /usr/libexec/makewhatis
```

fails with `"makewhatis: /usr/share/man/whatis.tmp: Read-only file system"`.

```text
/opt/local/bin/whatis cp
whatis: nothing appropriate
```

```shell
/usr/bin/whatis cp
```

gives lots of ugly output (`groff` errors?) but eventually shows `cp(1)`

### port man-db

```shell
sudo port install man-db
```

Outputs this:

```text
  found in man-db-2.13.0/config.log
--->  Building man-db
--->  Staging man-db into destroot
--->  Installing man-db @2.13.0_0
--->  Activating man-db @2.13.0_0
Error: Failed to activate man-db: The following ports have active files that conflict with man-db's:
mandoc @1.14.6_0
  /opt/local/bin/apropos
  /opt/local/bin/man
  /opt/local/bin/whatis
  (... 3 more not shown)
Image error: Conflicting file(s) present. Please deactivate the conflicting port(s) first, or use 'port -f activate man-db' to force the activation.
    while executing
"throw registry::image-error $msg"
    ("foreach" body line 35)
    invoked from within
"foreach file $imagefiles {
                incr progress_step
                _progress update $progress_step $progress_total_steps
                se..."
    invoked from within
"registry::write {
            foreach file $imagefiles {
                incr progress_step
                _progress update $progress_step $progress_..."
Error: See /opt/local/var/macports/logs/_opt_local_var_macports_sources_rsync.macports.org_macports_release_tarballs_ports_textproc_man-db/man-db/main.log for details.
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port man-db failed
```
