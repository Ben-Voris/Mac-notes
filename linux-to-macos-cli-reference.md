# Linux CLI → macOS Quick Reference

*Assumes MacPorts (`port`) for package management, not Homebrew.*

| Linux | macOS | Notes |
| ----- | ----- | ----- |
| `apt install` | `port install` | MacPorts |
| `systemctl` / `service` | `launchctl` | launchd is macOS's init/service manager; jobs are XML plists in `~/Library/LaunchAgents` or `/Library/LaunchDaemons` |
| `crontab -e` | still works, but `launchd` preferred | cron is deprecated on macOS in favor of launchd |
| `ldd` | `otool -L` | Shows dynamic library dependencies |
| `strace` | `dtruss` (needs `sudo`, often blocked by SIP) or `dtrace` | SIP makes tracing Apple binaries hard |
| `free -h` | `vm_stat` | Different format, no direct equivalent |
| `lsblk` / `fdisk -l` | `diskutil list` | |
| `cat /etc/os-release` | `sw_vers` | |
| `xdg-open` | `open` | `open .` opens current dir in Finder; `open -a AppName file` opens with a specific app |
| `xclip` / `xsel` | `pbcopy` / `pbpaste` | |
| `useradd` / `usermod` | `sysadminctl` or `dscl` | dscl is the raw directory service tool, much more verbose |
| `ip a` / `ifconfig` | `ifconfig` (still works) or `networksetup` | `networksetup -listallhardwareports` for interface names |
| `ps aux` | `ps aux` | Works, but it's BSD ps — some flags differ from GNU ps |
| `top` | `top` | Different default columns/keys; `port install htop` gets the familiar one |
| `.bashrc` / `.zshrc` | `.zshrc` | zsh is default shell since Catalina |
| `man` | `man` | Same |
| `lsof -i` | `lsof -i` | Same, works fine |
| `killall` | `killall` | Same, works |
| screenshot tools | `screencapture` (CLI) or Cmd+Shift+4 / Cmd+Shift+5 | |

## GNU vs BSD userland

Most core POSIX utilities (`grep`, `sed`, `awk`, `find`) exist on macOS but are **BSD variants**, not GNU — flag behavior differs in small, annoying ways (e.g., `sed -i` needs an explicit backup-suffix argument on BSD, optional on GNU).

If this causes friction:

```shell
port install coreutils findutils gnu-sed gawk grep
```

GNU versions are typically installed with a `g` prefix (`gsed`, `gfind`, `gawk`, `ggrep`) to avoid clobbering the BSD originals, unless you adjust your `PATH` to prefer them.
