---
title: "TIL: Ed25519 - The Cool New Kid in SSH Key Cryptography"
description: "A dive into the world of elliptic curve cryptography and why your SSH keys just got a whole lot sexier"
slug: "til-ed25519-ecdsa"
date: "09/24/2024"
draft: false
tags: ["TIL", "Cryptography", "SSH", "GitHub"]
---

Today, I learned about ed25519 and ECDSA when generating a new SSH key for my shiny new machine to connect to GitHub. Let me tell you, discovering a cooler, faster, and more secure way to do something you've been doing for years is quite the mind-blower.

## My Cryptographic Awakening

There I was, feeling all tech-savvy and ready to set up my new computer with GitHub. I confidently typed `ssh-keygen`, fully expecting to use the good ol' RSA encryption I've known and loved. But wait - apparently, the cool kids are using something called Ed25519 now? Color me intrigued.

## The Mystery Unfolds

I'll be honest, my first thought was, "Great, another acronym to add to the ever-growing list of tech jargon I need to keep up with." But as I dug deeper, I realized this wasn't just some arbitrary change – Ed25519 is revolutionizing the world of cryptography.

## What's the Big Deal with Ed25519?

Okay, let's break this down for those of us who don't speak fluent cryptography (myself included):

1. **It's an Elliptic Curve Digital Signature Algorithm (ECDSA)**: 
   Fancy words, I know. ECDSA uses some seriously cool math to create super secure signatures with smaller keys. Imagine cramming a whole buffet of security into a bite-sized snack.

2. **Smaller Keys, Big Security**: 
   Ed25519 uses 256-bit keys. Compared to the massive skeleton key of an old castle (aka RSA), Ed25519 offers a tiny house key with fort knox-level security.

3. **Speed Demon**: 
   Blink and you'll miss it - that's how fast Ed25519 operates. It signs and verifies signatures quicker than you can say "RSA is so last decade."

4. **Resistant to Shenanigans**: 
   Ed25519 comes prepared, having gone through cybersecurity boot camp. It flexes its muscles against various sneaky attacks that might trip up other algorithms.

## Why Should You Care?

1. **Future-Proof Security**: 
   As we venture further into the digital age, robust security becomes crucial. Ed25519 installs a state-of-the-art security system for your online identity.

2. **Efficiency is King**: 
   In our constant quest for speed and performance, Ed25519 delivers. This cryptographic sports car doubles as an impenetrable tank.

3. **Simplicity**: 
   Say goodbye to head-scratching over key lengths. Ed25519 brings the "one size fits all" approach to SSH keys, offering security and speed in a neat package.

## How to Jump on the Ed25519 Bandwagon

Ready to join the cool kids? Generate your very own Ed25519 key with this simple command:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

Replace "your_email@example.com" with your actual email, and voilà! You're now the proud owner of a shiny new Ed25519 key.

## What I Learned from This Cryptographic Adventure

This little journey into the world of Ed25519 and ECDSA reminded me that the tech world never stops evolving. Just when you think you've got it all figured out, something comes along to shake things up – in a good way.

It's also a testament to how clever mathematics can solve real-world problems. Ed25519 isn't just a new standard; it's proof that the most secure solutions can also be the most elegant.

## My Trusty Resources

- The ever-helpful ChatGPT, who patiently explained cryptography to me like I was five (which, in crypto years, I probably am).
- [GitHub's SSH key documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- My newfound appreciation for elliptic curves (in cryptography, that is – my appreciation for actual curves remains unchanged)

Next time someone asks me about SSH keys, I'll be ready to dazzle them with my knowledge of elliptic curve cryptography. Or at least, I'll know enough to nod sagely and say, "Ed25519 is the way to go, my friend."

Remember, in the world of cryptography, it's hip to be square – or in this case, elliptic.