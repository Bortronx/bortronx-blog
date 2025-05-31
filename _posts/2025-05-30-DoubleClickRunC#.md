---
title: "Double Click To Execute C# using Batch"
date: 2025-05-30
---

# Intro
.NET 1O preview introduced the ability to run C# from the commandline with the .NET Runtime Installed

All you need to do is install either the SDK (Runtime included) or the Runtime (alone)
See https://dotnet.microsoft.com/en-us/download/dotnet/10.0

This introduces new possibilities and while it does not change windows to allow running C# by doubleclicking it make it possible to do using batch files

I wrote the following file with accomplis this:
```
@echo off
powershell -Command "Get-Content '%~f0' | Select-Object -Skip 8 | Set-Content commandfile8917.cs"
echo commandfile8917.cs has been created.
dotnet run commandfile8917.cs
del commandfile8917.cs
exit /b 0  

:: ==== Everything below this line will go into commandfile8917.cs ==== ::
```

If you add this at the beginning of any C# file you will bea able to rename the file to .bat and execute it 

For example:

```
@echo off
powershell -Command "Get-Content '%~f0' | Select-Object -Skip 8 | Set-Content commandfile8917.cs"
echo commandfile8917.cs has been created.
dotnet run commandfile8917.cs
del commandfile8917.cs
exit /b 0  

:: ==== Everything below this line will go into commandfile8917.cs ==== ::

Console.WriteLine("Hello, World!"); // Prints "Hello, World!" to the console.
Console.ReadKey();
```

Renam this .cs file into a .bat file and double click to run.

The file uses the file name ``commandfile8917.cs`` for the temporary name to avoid conflict as is highly unlikely that there would be another file name this exact same way. But the file name will need to be changed if there is.

# Advantages
This allows you to now write all scripts using C# instead of powershell or batch commands
