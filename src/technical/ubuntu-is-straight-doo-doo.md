---
layout: post.njk
title: "Ubuntu Is Straight Doo Doo"
date: 2025-12-01
section: technical
---

## Introduction

Got a new laptop for work -ASUS TUF F15 with an RTX 4070. I wiped Windows and threw Arch on it immediately. Biggest beef steak!

This resulted in two days of random freezes, black screens, and Xorg issues due to NVIDIA driver incompatibility. I got tired of fixing it and decided to install the distro that's 'certified' for this laptop and 'just works': 
Pop Exclamation Mark Underscore OS 22.04.
That was an even bigger beef steak!

## “Developer-friendly” – Bomboclat Wallahi
I needed Hugo to preview my site. I ran `sudo apt install hugo`, then `hugo server`, and immediately got:

```This does not appear to be a Hugo site.```

Turns out the Ubuntu repo version is so ancient it doesn't even support Go modules. So I had to delete it, go to GitHub, download the latest binary, and dump it in `/usr/local/bin`.

And Hugo wasn't the only one. Same issue with:

- Node.js (still on 18 while the rest of the planet is on 22)
- Docker (outdated asf)
- Neovim (missing half the Lua API)
- Even bat was an ancient version that didn’t support syntax highlighting for some languages.

You install something on Arch, and it's there. You try to install something on Ubuntu, and it's a completely miserable experience.

## Package Management is a Joke

Here's the situation if you want to install software on Ubuntu in 2025:

- `apt`: Everything is outdated.
- `PPAs`: Random repos you have to add that break your dependencies later.
- `Snap`: Canonical's bloatware that takes too much to launch and completely fucks up `lsblk` with loop devices.
- `Flatpak`: Ignores your system GTK themes and fonts.
- Random `.deb` files from the internet: Because the official repos don't have what you need.

Firefox as a snap by default is actually infuriating. It takes longer to launch the browser than it does to boot the laptop.

## "Stability"

People defend Ubuntu by saying it's stable. It's stable because nothing ever updates.
I tried installing a basic Python tool.
`pip install` → needs Python 3.11.
System Python → 3.10.
`apt install python3.11` → not in the repo.
So you're forced to add another random PPA just to get a modern version of a programming language.

## Bloat

I opened `htop` and saw about 30 snap processes eating RAM just because I installed Spotify, VS Code, and Bitwarden.

## Verdict

I wiped Pop!_OS and I'm reinstalling Arch. Ironically, the NVIDIA drivers work better on Arch than they ever did on the distro that was "certified" for this laptop.

Back to one package manager, up-to-date software, and no snaps. Ubuntu might be fine for regular users, but for development, it's straight doo-doo.
