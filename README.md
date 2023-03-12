# Simple script to prepare Kali Linux VM for a clean snapshot (for my personal usage)

My personal usage is that I have snapshot of Kali that is clean (no project specific files or history) that I can easily use as a base for whatever project I'm working on.

When I want to update my clean snapshot with new programs and configurations I've made while working on a project (assuming they're not project specific), I run this script to create a new clean base to take a snapshot of. Note that I don't put anything project specific in folders aside from `/home/kali/Downloads` and `/home/kali/tmp`.

## Overview of Script
1. Perform setup
    1. Create `/home/kali/tmp` and `/home/kali/srv` if not already created
    1. Symlink `/usr/share/wordlists` to `/home/kali/wordlists` for convenience
1. Update system
1. Update searchsploit database
1. Update quick server files (stored in `/home/kali/srv`)
    1. Replace peass-ng with latest version
    1. Currently nothing else
1. Delete contents of `/home/kali/Downloads`, `/home/kali/Desktop`, and `/home/kali/tmp` (`/home/kali/Documents` is preserved)
1. Clear zsh history of `root` and `kali` user

Note that running the script requires root.

## File Structure of Clean Snapshot
```
├── Documents
├── Downloads
├── wordlists -> /usr/share/wordlists
├── serv
│   └── peass-ng
│       ├── linpeas.sh
│       ├── winPEASany.exe
│       └── winPEAS.bat
├── update_snapshot
├── Desktop
└── tmp
```
