---
title: "Hard Crashes with AMD CPU"
date: 2023-04-29
---

# Issue
I have been facing problems with the computer crashing straight to black whenever the CPU has some load higher than idle.
Crashes feel like they happen randomly but the happen frequently and at least one crash can be expected almost every day.

# Troubleshooting
I ran windows memory diagnostic and all test passed.
This leads me to belive that there is no problem with the Memory

I am able to run intesive GPU tasks like video games and even benchmarks without crash.

Next I'm testing the CPU by using Prime.
Using prime seems to consistently cause a crash. I tried to isolate it with just the memory test and it crashed the computer in less than 5 minutes


Next is the CPU only test. I ran CPU only test using Prime. It also crash very fast in less than 5 minutes.

Next is a GPU test once again. The test ran for 45 minutes with no crash.

Next I ran Prime95 again to ensure that these 45 minutes are not a result of something else.

The Computer crashed in less than 10 seconds.

With this information we can isolate the problem to the Motherboard, Hard Drive, CPU, or Memory. With CPU being the most likely culprit.

Next I will update BIOS drivers.

I installed the Asrock Auto Driver. This updated the Chipset Driver, the VGA Driver and the HD Audio drive. The installer prompted to Setul Auto driver installer in the BIOS 

Tested with s different power supply and received the same error.

This last test reduces the problem to either the CPU, the drive windows installation.
