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

### Fixing/Removing Installation on the engine
While facing the following issue:


https://www.reddit.com/r/unrealengine/comments/11urtgn/help_i_cannot_seem_to_install_my_rider_plugin/

 I did not find a solution right away and the post was archived. My solution was deleting the plugin from the engine by going to `UNREAL_ENGINE_INSTALL\Engine\Plugins\Developer\RiderSourceCode` and deleting the folder. I believe the following suggestion from the archive post should also work.

>What worked for me is pressing the Unreal button (top middle, next to the build button) -> "RiderLink Installation Settings" -->
>
>"Extract RiderLink in Game". It works fine except for occasional error when closing the UE, but it doesn't mess with the code or anything.


