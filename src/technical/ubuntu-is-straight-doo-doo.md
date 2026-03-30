---
layout: post.njk
title: "Ubuntu Is Straight Doo Doo"
date: 2025-12-01
section: technical
---

## Introduction

New job, new laptop. They handed me a brand-new ASUS TUF Gaming F15 with an RTX 4070 shoved up its ass. Looks sick, right?
I immediately wiped Windows and slapped Arch on it because that’s what I use Arch btw.
Two days of random freezes, black screens, fans sounding like a jet engine taking off in my lap, and Xorg segfaulting every time I sneezed. NVIDIA being NVIDIA, basically.
Fine. Whatever. I’ll do the responsible adult thing. I’ll install the distro that “just works” and is “certified” for this exact laptop.
Hello, Pop!_OS 22.04. At least it doesn’t come with that hideous Unity/GNOME disaster Canonical calls a desktop these days.
Spoiler: I now understand why some people kick puppies.

## “Developer-friendly” – My Actual Ass
I needed Hugo to preview my site. One command, right?

```shell
sudo apt install hugo
```
Installed. Run hugo server on a completely normal Hugo project.

```This does not appear to be a Hugo site.```

Turns out the version in the repo is so old it predates modules, predates Go modules, probably predates the invention of fire.
So I do the dance every Ubuntu user knows by heart: delete that garbage, go to GitHub, grab the newest binary, throw it in ```/usr/local/bin```, and cross my fingers that ```apt``` doesn’t overwrite it next week.
And Hugo was just the opening act. Same story with:

- Node.js (still on 18 while the rest of the planet is on 22)
- Docker (old enough to collect Social Security)
- Neovim (missing half the Lua API)
- Rustup (lol good luck)
- Even bat was an ancient version that didn’t support syntax highlighting for half the languages I use

Someone once said: “On Arch you install a thing and it’s installed. On Ubuntu you install a thing… and then the suffering begins.”
He’s not wrong. I wanted to punch my monitor every time.

## The Twelve Gates of Package Hell

Let’s list the ways you can install software on this “developer-friendly” distro in 2025:

1. ```apt``` → guaranteed to be older than your parents’ marriage
2. Some random PPA that dies the day you need it most
3. ```Snap``` → brought to you by Canonical, now with extra 20-second startup lag and secret mounted loop devices shitting up lsblk
4. ```Flatpak``` → works fine until you realize themes and fonts live in an alternate dimension
5. ```AppImage``` → a 300 MB executable that still can’t find your GTK theme
6. ```Random .deb from the internet``` (malware roulette)
7. ```curl | sudo bash``` because security is for cowards
8. Compile from source and find out you’re missing seventeen build dependencies and one of them is only in “universe” which is disabled by default

Firefox as a snap is a war crime. It takes longer to start than booting the entire OS. Every snap feels like it’s running in a container shipped overnight from Saturn.

## Don’t Even Talk to Me About Stability

“It’s stable!” they scream, while I’m manually downloading .deb files like it’s 2009.
Stable like a corpse, maybe. Nothing moves, nothing updates, nothing works with anything released after COVID started.
I tried installing a simple Python tool the other day.
```pip install``` → needs Python 3.11
System Python → 3.10
```apt install python3.11``` → not in repo
Deadlines → who needs ’em, just add another PPA and sell your soul


## The Final Straw
I opened ```htop``` and saw thirty snap processes eating RAM because I dared to install Spotify, VS Code, and Bitwarden the “easy” way.
Thirty. Individual. Processes. For three apps.
I wanted to throw the laptop out the window, but it’s company property and I like getting paid.

## Verdict
Pop!_OS/Ubuntu isn’t a Linux distribution.
It’s a practical joke that lasted fifteen years and somehow convinced corporations it’s “enterprise ready.”
If you’re a developer and you willingly choose this, I’m sorry, but you hate yourself.
If your company forces it on you, start polishing that résumé.
I’m currently reinstalling Arch while writing this. The NVIDIA drivers already work better than they ever did on Pop.
Everything is new. One package manager. No snaps. No crying.
Ubuntu isn’t Linux for human beings.
It’s Linux for people who enjoy pain and have given up on joy.
Never again.
Straight doo-doo. Every last byte of it.