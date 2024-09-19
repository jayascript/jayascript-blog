---
title: "TIL: Supercharging My Terminal with LLM Integration"
description: "Quick summary of things I learned today."
slug: "til-llm"
date: "09/19/2024"
draft: false
tags: ["TIL"]
---
        
Today, I embarked on a journey that completely transformed my terminal experience. I dove headfirst into setting up the `llm` package on my local machine, and let me tell you, it's been a game-changer. This clever little tool has opened up a whole new world of possibilities, allowing me to chat with AI models right from my command line. While the process was mostly smooth sailing, I did hit a few bumps along the way that I think are worth sharing.

## My Setup Adventure

### 1. The pipx Foundation

First things first, I needed to get `pipx` up and running. If you've read my [previous post](til-pipx), you know I'm a big fan of this tool. It's like a magic wand for installing Python packages - global access, no dependency drama. Here's how I set it up:

```bash
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

That second command was crucial - it made sure I could actually use the tools I installed with `pipx` from anywhere in my system. No more PATH headaches!

### 2. Installing the Star of the Show: `llm`

With `pipx` at my disposal, getting `llm` installed was a breeze:

```bash
pipx install llm
```

Simple, clean, and isolated. Just the way I like it.

### 3. Bringing OpenRouter into the Mix

Now, here's where things got really exciting. To tap into the power of Claude 3.5 Sonnet (my AI assistant of choice), I needed to connect `llm` with OpenRouter. It felt a bit like introducing two friends I knew would hit it off:

```bash
llm install llm-openrouter
```

Of course, I had to share my OpenRouter API key to make the magic happen:

```bash
llm keys set openrouter
```

A quick `llm models` check, and I was thrilled to see all the new AI playmates at my disposal.

### 4. My Shortcut to Claude

To streamline my workflow (because who doesn't love efficiency?), I set up a quick alias for Claude:

```bash
llm aliases set claude openrouter/anthropic/claude-3.5-sonnet
```

Now, chatting with Claude is as easy as:

```bash
llm claude "What's the meaning of life, the universe, and everything?"
```

(Spoiler alert: It's not always 42!)

## My New AI-Powered CLI Toolkit

As I've been playing around with `llm`, I've discovered some really handy commands:

- `llm -c <prompt>`: Perfect for those times when I want to continue a thought-provoking conversation.
- `llm models default <model>`: When I'm in a committed relationship with a specific AI model.
- `llm -m <model> <prompt>`: For those moments when I want to flirt with different AI personalities.
- `llm <prompt> > file.txt`: Because sometimes I want to save those AI pearls of wisdom for posterity.
- `llm logs path`: A trip down memory lane, revisiting all our past conversations.
- `datasette "$(llm logs path)"`: When I'm feeling nostalgic and want to [browse through my chat history](til-datasette) in style.

## The Aftermath: My Terminal, The AI Playground

I have to say, I'm still buzzing with excitement over this setup. My terminal has transformed into this incredible AI playground. I can now bounce ideas off Claude 3.5 Sonnet (or any other model) without even leaving my command line. It's streamlined my workflow in ways I hadn't even imagined.

This journey has reminded me why I love diving into new tools and technologies. There's always something out there ready to solve a problem you've been battling, often in ways you hadn't even considered.

For my fellow CLI enthusiasts out there, I can't recommend this setup enough. It's changed my interaction with AI models for the better, and I have a feeling it'll be a staple in my development toolkit for a long time to come.

## My Go-To Resources

As I continue to explore the possibilities with `llm`, I'm keeping these resources close at hand:

- [LLM on PyPI](https://pypi.org/project/llm/)
- [LLM-OpenRouter on GitHub](https://github.com/simonw/llm-openrouter)
- [OpenRouter Documentation](https://openrouter.ai/docs)

Here's to many more AI-assisted adventures in the terminal!
