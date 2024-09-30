---
title: "TIL: AUR and Yay - The Hidden Treasures of Arch Linux"
description: "Discovering the magical world of AUR and yay while trying to install mutt-wizard"
slug: "til-aur-yay"
date: "09/25/2024"
draft: false
tags: ["TIL", "Linux", "AUR", "Yay", "EndeavourOS"]
---

Today, I embarked on a quest to install Luke Smith's mutt-wizard on my shiny new EndeavourOS setup. Little did I know, this simple task would lead me down a rabbit hole of Arch User Repository (AUR) goodness and introduce me to my new best friend.

yay!

## The Misadventure Begins

There I was, feeling like a Linux pro, ready to set up my email client with mutt-wizard. I confidently typed:

```bash
sudo pacman -S mutt-wizard
```

Expecting magic to happen, I instead got slapped with this error:

```
error: target not found: mutt-wizard
```

Cue the confused head-scratching. "But I thought pacman was the master of all packages!"

Little did I know.

## The Plot Thickens

Determined to understand what was going on, I tried searching for the package:

```bash
pacman -Ss mutt-wizard
```

Silence. No results. At this point, I was starting to question my sanity. Was I spelling it wrong? Had I dreamt up this whole mutt-wizard thing?

## Enter the Hero: Yay

Just when I was about to give up and resort to carrier pigeons for my email needs, I remembered hearing about something called "yay". With nothing to lose, I gave it a shot:

```bash
yay -Ss mutt-wizard
```

And suddenly, like magic, results appeared:

```
aur/mutt-wizard-git 3.2.1.r55.gc8bbef5-2 (+28 0.00) 
    Easily auto-configure neomutt and isync/mpop with safe passwords (IMAP/POP3/SMTP)
aur/mutt-wizard 3.3.1-1 (+9 0.02) 
    Easily auto-configure neomutt and isync/mpop with safe passwords (IMAP/POP3/SMTP)
```

"Yay!" I shouted, startling my cat. I quickly installed it:

```bash
yay -S mutt-wizard
```

And just like that, mutt-wizard was mine. Yay! (How many times can I say it?)

But what sorcery was this?

## The AUR Revelation

Turns out, I had stumbled upon the Arch User Repository (AUR), a community-driven wonderland of packages that aren't in the official Arch repositories; and yay, pacman's cool cousin that knows all the secret handshakes.

Here's what I learned, thanks to a kind Redditor named u/NotAName320:

1. **AUR is a DIY Paradise**: It's not a binary repository like the official ones. Instead, it's full of recipes (PKGBUILDs) that tell your system how to whip up the software you want.

2. **Two Flavors of AUR Packages**:
   - Some pull source code and build it from scratch. It's like getting a LEGO set and assembling it yourself.
   - Others grab pre-built binaries from elsewhere and plop them onto your system. Think of it as ordering a pre-assembled LEGO model.

3. **Yay is Your Personal Assistant**: It works with pacman to automate the whole process of fetching, reading, and building AUR packages. Like having a really efficient intern who knows all the cool software spots.

4. **AUR Packages are Part of the Family**: Once installed, pacman treats them like any other package. You can list them with `pacman -Qm` and remove them with `pacman -R`. Just remember, you can't install them directly with pacman - that's yay's job.

## The Moral of the Story

1. **Check Official Repos First**: Always start with `pacman -Ss`. It's like checking your local grocery store before driving to the specialty shop two towns over.

2. **AUR is Your Plan B**: If pacman comes up empty, that's when you unleash yay and dive into the AUR.

3. **Flatpak is Also a Thing**: Sometimes, the flatpak version of an app might be a better choice. It's like getting a pre-packed lunch instead of cooking from scratch.

## What I Learned from This Package Management Adventure

This little detour into the world of AUR and yay reminded me that there's always more to learn in the Linux universe. Just when you think you've got pacman figured out, yay comes along and opens up a whole new world of possibilities.

It's also a testament to the power of community-driven repositories. The AUR is like a potluck where everyone brings their favorite dish - sure, you might get a few weird casseroles, but you'll also discover some amazing recipes you never knew existed.

## My Trusty Resources

- The ever-patient terminal, which endured my confused commands without judgment.
- Reddit user NotAName320, who explained AUR and yay like I was five (which, in Arch years, I probably am).
- My newfound appreciation for yay, the unsung hero of the Arch package management world.

Remember, in the world of Arch Linux, when pacman says no, yay says "hold my beer". Next time someone asks me about installing obscure software on Arch, I'll be ready to yay my way to victory. 