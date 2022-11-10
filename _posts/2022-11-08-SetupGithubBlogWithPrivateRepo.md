---
title: "Setting Up Github Blog with Private Repo"
date: 2022-11-08
---

- Setup a private repository with a _posts directory and all the posts. 
- Create a second directory in the same repository with _posts-private
- Setup and use the following action to Push _posts directory to another repository:
https://github.com/marketplace/actions/push-a-directory-to-another-repository
- Go to Settings > Developer Settings in your profile and Create a Personal access token (Use Classic)
- Create an Action in your original project and select Scope repo 
- Copy the Personal access token generated
-  Go into original repo's Settings tab >  Secrets > Actions > New Repository secret.
-  Paste Personal access token generated
-  Give it a name and copy the name
-  Paste the name into GITHUB_TOKEN in the yaml Action configuration file in the line secret.GITHUB_TOKEN
- Create posts into the _posts-private folder and when ready to make public push into posts folder
