---
title: "TIL: Pass and GPG - A Tale of Two Keys and One Very Confused Developer"
description: "Dive into the cryptographic comedy of errors as I navigate the world of password management with Pass and GPG"
slug: "til-pass-gpg-adventure"
date: "2024-09-30"
draft: false
tags: ["TIL", "Cybersecurity", "Pass", "GPG", "Password Management"]
---

Today, I embarked on what I thought would be a simple task of transferring my password store from one machine to another. Little did I know, I was about to star in my own cryptographic comedy of errors. Let me tell you about the wild ride that is password management with Pass and GPG.

## My Pass-GPG Pandemonium

Picture this: There I was, feeling like a digital Indiana Jones, ready to unearth my password treasures from my trusty 'envy' machine and transport them to the promised land of 'endeavour'. Armed with my trusty Pass command and a vague recollection of GPG keys, I set off on my quest. What could possibly go wrong?

Oh, sweet summer child...

## Why I'm Both Excited and Slightly Terrified About Pass and GPG

1. **Fort Knox for Your Passwords**: Pass turns your passwords into an impenetrable fortress... that sometimes even you can't break into!
2. **GPG: The Gatekeeper**: It's like having a super-secure lock, assuming you can remember where you put the key.
3. **Git Integration**: Because why have one complex system when you can have three working in perfect chaos?

## My Pass-GPG Setup Adventure

Getting started with Pass and GPG was like trying to solve a Rubik's cube blindfolded. Here's a glimpse into my journey:

### 1. The Great Key Hunt
   First, I had to figure out which GPG key I used. 
   Spoiler alert: I didn't remember.
   ```bash
   gpg --list-secret-keys --keyid-format LONG
   # Stare at screen, questioning life choices
   ```

### 2. The Rememberance
   As soon as I tried to push my pass changes to GitHub, I was greeted with the following error message: "Enter password to unlock private key."
   Unfortunately, I had no idea which password it was asking for.
   Of course, me being the stuck up idiot that I am, had never written down any password anywhere for my GPG key on my envy machine. So, I was pretty much SOL.
   I spent the next fifteen minutes sparring with Claude back and forth about how to transfer over my password files without the GPG key to decrypt them. I imagined a future of painstakingly copying over every single password from my old computer to my new one... I was about to slam the lid shut and call it a night. (Or a morning. It was technically the next day at this point.)
   (Also, is it pronounced "pain-stakingly" or "pains-takingly"? Like, are you staking the pain or taking it?)   
   Just when I thought all hope was lost, I remembered my GPG password on the envy machine. Cue triumphant music!
   ```bash
   gpg --export-secret-keys --armor > private-key.asc
   # Feel like a hacker in a '90s movie
   ```
   All I needed was the right kind of prompt: a familiar box to pop up in the right context, and the right neurons fired in just the right order so that I kind of just went, "Aha!"

### 3. The New Key on the Block
   Plot twist: I'd already created a new GPG key on endeavour. Same name, same email, different encryption. Because why make things easy?
   ```bash
   gpg --import private-key.asc
   # Watch in horror as GPG juggle two identities
   ```
   Thankfully, after a bit more prompting from Claude, it was relatively easy to update the trust level for the new key and reencrypt the password store.

## Cryptographic Chaos is Fun!

After the dust settled, I found myself with a password store accessible by two different GPG keys - one RSA, one ECC. It's like having two keys to your house, but one's a medieval skeleton key and the other's a futuristic biometric scanner.

## Looking Ahead

Now that I've survived this cryptographic rollercoaster, I'm actually excited about the possibilities. Having multiple keys for my password store feels like I've leveled up in the world of digital security. Plus, I now have a great party trick: "Want to see me decrypt a password with two different algorithms?"

## My Pass-GPG Toolkit

As I continue my journey into the heart of password management darkness, I'm keeping these resources close:

- The Pass man page (my new bedtime reading)
- GPG documentation (for when I need to induce confusion)
- A notepad to draw my "key family tree"

Remember, in the world of password management, it's not about the destination; it's about the friends (and GPG keys) you make along the way. Now, if you'll excuse me, I need to go label my keys before I forget which is which... again.
