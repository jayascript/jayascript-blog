---
title: "Qtile Check: No Module Named 'config'"
description: "How I solved a mysterious 'No module named config' error when testing my Qtile installation"
slug: "error-qtile-check-no-module"
date: "09/24/2024"
draft: false
tags: ["Error", "Troubleshooting", "EndeavourOS", "Qtile", "Python"]
---

Today, fresh off my Qtile installation adventure, I ran into another hiccup that left me scratching my head. Here's the tale of how I tackled it:

## The Error That Had Me Going "Huh?"

So there I was, feeling pretty good about successfully installing Qtile. Naturally, I wanted to test the installation to make sure everything had executed properly. The command for this is `qtile check`, which I ran, fully expecting a nice, reassuring "All good!" message.

Instead, I was promptly greeted with this error:

```
Checking Qtile config at: /home/jayascript/.config/qtile/config.py
Checking if config is valid python...
Traceback (most recent call last):
  File "/usr/lib/python3.12/site-packages/libqtile/scripts/check.py", line 122, in check_config
    config.load()
  File "/usr/lib/python3.12/site-packages/libqtile/confreader.py", line 134, in load
    config = importlib.import_module(name)
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
    return _bootstrap._gcd_import(name[level:], package, level)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "<frozen importlib._bootstrap>", line 1387, in _gcd_import
  File "<frozen importlib._bootstrap>", line 1360, in _find_and_load
  File "<frozen importlib._bootstrap>", line 1324, in _find_and_load_unlocked
ModuleNotFoundError: No module named 'config'

Errors found in config. Exiting check.
```

What do you mean no module named "config"?

## The Mystery Unfolds

I wasn't sure how to solve this one at all. My first thought was, "Great, something's wrong with Python. This is gonna be a pain to debug." But I figured I'd better do some digging before I started pulling my hair out.

## My Troubleshooting Adventure

1. **First Attempt**: Google to the rescue!
   
   I searched online and came across this github issue, which solved my problem: https://github.com/qtile/qtile/issues/1273

2. **The Breakthrough**: A helpful comment
   
   Here's the specific comment that helped, by user @zordsdavini:

   ```
   In Arch 1st time started Qtile it does not copy default config to home
   right location. You should do that manually. ~/.config/qtile/config.py
   ```

3. **The Aha Moment**: There's no config file!

   In other words, there WAS no config file to check against. The "module" that didn't exist was MY Python module, `config.py`. 

## What I Learned from This Error

This error was confusing because I still don't have a great understanding of what a Python "module" is. I assumed it meant something wrong with one of the built-in Python packages, and was immediately discouraged thinking I'd need to do some heavy debugging.

But, here's the kicker: my Python script is technically a "module" in and of itself, one that is called by qtile and run as a program. So that's an interesting thing to keep in mind, and should help me debug errors like this much more quickly in the future.

## How to Reproduce (and Solve) the Error

If you find yourself in a similar situation, here's what's probably happening:

1. You've just installed Qtile on a fresh system (like Arch or EndeavourOS).
2. You run `qtile check` without creating a config file first.
3. You see the "No module named 'config'" error.

To solve it:
1. Create the directory: `mkdir -p ~/.config/qtile`
2. Create a config file: `touch ~/.config/qtile/config.py`
3. Copy the default config or create your own in this file.
4. Run `qtile check` again.

## My Trusty Resources

- The error message itself (even if it was a bit misleading at first)
- The GitHub issue I found: https://github.com/qtile/qtile/issues/1273
- My newfound understanding of Python modules (thanks, confusing error!)

Next time I encounter a "module not found" error, I'll be sure to check if the module it's complaining about is actually one of my own files before I start panicking about Python packages.

And remember, folks: sometimes the module you're looking for is the one you haven't written yet.