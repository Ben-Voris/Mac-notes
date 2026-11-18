# CLAUDE.md

This repo is Ben's collection of macOS usage notes: tips, keyboard shortcuts,
app settings, install notes, and write-ups of problems and how they were fixed.
It is published at <https://github.com/Ben-Voris/Mac-notes.git> and rendered at
<https://ben-voris.github.io/Mac-notes/>.

## Layout

- `README.md` holds most of the notes, organized by `##` sections per topic or
  app (Apple Mail app, Finder, Terminal app, What to install, and so on).
- A longer topic gets its own file with a descriptive, hyphenated name (for
  example, `Mac-Photos-Issue-after-Consolidate.md`) and is linked from the
  README with a relative link.
- Screenshots go in `Pics/` and are referenced with relative links and alt text.

## Conventions

- Put a new note in the existing README section it belongs to. Add a `###`
  subsection for a troubleshooting write-up.
- Troubleshooting notes record the symptom, what was tried and didn't work, the
  fix that did, and the date or macOS/app version it applied to.
- Wrap prose at about 80 columns. The files are linted with markdownlint.
- Use backticks for app names, menu items, settings, keys, commands, and paths.
- Write menu paths with `→`, for example `Mailbox` → `Rebuild`.
- Write keyboard shortcuts in the standard form: keys in backticks joined by
  `\+`, followed by the symbols in parentheses, for example
  `Shift` \+ `Command` \+ `N` (`⇧⌘N`).
- Use Chicago-style em-dashes with no spaces around them (word—word).
- For package installs, use MacPorts (`port`), not Homebrew.
- Ben's preferred CLI editor is vim.

## Working with Ben

- Ben writes these notes himself. Catch errors, broken links, and ambiguities,
  and flag them rather than rewriting his prose freely.
- Don't commit or push unless asked. Commit messages are short and imperative,
  for example "Add note about hidden (`dot`) files in Finder".
