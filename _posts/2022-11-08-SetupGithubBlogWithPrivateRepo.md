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

``` 
# This is a basic workflow to help you get started with Actions

name: Push File

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the "main" branch
  push:
    branches: [ "main" ]
    paths:
      - '_posts/**'
  pull_request:
    branches: [ "main" ]
    paths:
      - '_posts/**'

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  copy-file:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - name: Checkout
        uses: actions/checkout@v3

      # Runs a single command using the runners shell
      - name: Push a directory to another repository
        uses: datalbry/copy_folder_to_another_repo_action@1.0.1
        env:
         API_TOKEN_GITHUB: ${{ secrets.[USER_SECRET] }}
        with:
          source_folder: '_posts'
          destination_repo: 'Username/myrepo'
          destination_branch: 'main'
          destination_folder: '_posts'
          user_email: 'example@email.com'
          user_name: 'username'
          commit_msg: '[GHA] Update the posts.'
```
- In the script above replace the email, usernmae and repo path with your particular information.
- Copy the Personal access token generated in your account under Settings > DeveloperSettings > PersonalAccessTokens > Tokens ( I did a classic token as my website's token should not expire in a long time as I do not want to keep coming back to renew it) 
-  Copy the secret generated when creating the token. 
-  Go into original repo's Settings tab >  Secrets and variables > Actions > New Repository secret.
-  Paste Personal access token generated
-  Give it a name and copy the name
-  Paste the name into USER_SECRET in the yaml Action configuration file in the line secret.USER_SECRET
- Create posts into the _posts-private folder and when ready to make public change the path of the file into the posts folder
