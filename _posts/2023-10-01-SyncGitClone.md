---
title: "Sync a Git Clone with the source repository"
date: 2023-10-01
---

I used the following script to keep a clone repository updated

```
#!/bin/bash

# Get the current path
current_path=$(pwd)

# Get the remote origin URL
remote_url=$(git config --get remote.origin.url)

# Go to the remote origin URL
cd "$remote_url"

# Add and commit the changes
git add .
git commit -m "Update Files"

# Go back to the original path
cd $current_path

# Reset and pull the changes
git reset
git pull


# Pause the script and wait for user input
read -p "Press any key to continue..."

```

Saved this as a .sh file.
I run it whenever I need to update the clone.
