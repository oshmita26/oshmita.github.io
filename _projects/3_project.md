---
layout: page
title: Bullying the bully
description: Anti-bullying discord chatbot
img: assets/img/cyberbullying.jpg
importance: 3
category: fun
giscus_comments: false
---

## Overview

**Bullying-The-Bully** is an anti-cyberbullying project built to protect social-media
users from online harassment and trolling. Cyberbullying is a serious and growing
problem — studies have ranked India among the countries most affected, with a large
share of young people reporting that they have experienced it. The project is a small
initiative toward addressing this: an NLP model that classifies messages as offensive
or non-offensive, deployed as a Discord bot that moderates servers automatically.

## How it works

The bot reads recent messages on a Discord server and runs each one through an
NLP-based classifier that predicts whether the text is offensive. When a message is
flagged as offensive, the bot:

1. Deletes the offending message.
2. Creates a poll to ban the user who sent it.
3. Bans the user automatically if the number of votes reaches a set threshold.

The classifier was trained on the
[Malignant Comment Classification dataset](https://www.kaggle.com/surekharamireddy/malignant-comment-classification)
from Kaggle.

## Technologies

- **`discord.py`** — Discord bot framework and server integration
- **`scikit-learn`** — training the NLP offensive-comment classifier
- **Replit + UptimeRobot** — hosting the bot so it runs 24/7

## Usage

Add the bot to a Discord server via its OAuth2 invite link and grant it Administrator
access; once added, it runs continuously and moderates messages automatically.

Source code: [Pratyush-exe/antibullying-discord-bot](https://github.com/Pratyush-exe/antibullying-discord-bot)
