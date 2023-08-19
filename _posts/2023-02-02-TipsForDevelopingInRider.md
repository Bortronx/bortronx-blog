---
title: "Tips For Developing in Rider"
date: 2023-02-02
---

# Some tips for Developing in Rider (Mainly using C++ for Unreal)

### See Debug variables Instead of ALREADY PREPROCESSED

In rider change from ```Development Editor | Win64``` to ```DebugGame Editor | Win64```. See the image below.

<img width="167" alt="image" src="https://onedrive.live.com/embed?resid=E87B3A3E0BB00F13%21115742&authkey=%21ADd-qwY6agdXf24&width=333&height=42">


### Soft Wrap every file in Rider:

- Go to File > Settings > Editor > General
- Under Soft Wraps set Soft-wrap these files to be checkmarked
- Add the following pattern: `*.*` 

### Use TODO and TODO Patterns

Use a custom TODO pattern like *MY TODO:* when working on top of other projects or extending existing code. Often times you will find that existing code contains TODOs.

TODOs allow you to pick up where you left off much faster.

