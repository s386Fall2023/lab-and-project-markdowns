---
title: Adding SSH keys to your GitHub account
layout: single
author_profile: false
classes: wide
excerpt: How to add new ssh keys to your Github account for Stat 386
---


See this [GitHub documentation page](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh) for more information.

You can use the SSH protocol by setting up SSH keys to connect with GitHub without
needing to supply your username and access token.  SSH stands for Secure Shell
and it protocol for operating network services securely over an unsecured network.
You can read more about SSH [here](https://en.wikipedia.org/wiki/Secure_Shell).

## Check for existing SSH keys
1. Open the terminal (Mac) or Git Bash (Windows)
2. Enter ```ls -al ~/.ssh```
3. Check the directory listing to see if you have the file `id_ed25519.pub`
    * If the `id_ed25519.pub` is not listed or if you receive an error that `~/.ssh` doesn't exist, then you don't have the ssh keys that we will use.
    
[Go to GitHub documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)

## Generating New SSH Keys
*(If you already have the right SSH keys, skip to the next section.)*
1. Open the terminal (Mac) or Git Bash (Windows)
2. Type or paste the text below, substituting in your GitHub email address
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
3. When prompted to "Enter a file in which to save the key", press **ENTER** to accept the default location.
4. At the prompt to enter a passphrase, press **ENTER** for no passphrase (unless you want one)

[Go to GitHub documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

## Adding SSH Keys to your GitHub Account

1. Copy the SSH public key to the clipboard. 
    * There are several ways to do this:
        - In Git Bash (Windows), type ```clip < ~/.ssh/id_ed25519.pub```, which will copy the contents of the file to the clipboard
        - In the terminal (Mac), type ```pbcopy < ~/.ssh/id_ed25519.pub```, which will copy the contents of the file to the clipboard
        - In either, type ```cat ~/.ssh/id_ed25519.pub``` to print the contents of the file to the screen, then copy the contents using Ctrl-C (Windows) or Cmd-C (Mac)
2. Go to GitHub.  In the upper-right corner, click on your profile photo, then click **Settings**.  
3. In the user settings sidebar, click *SSH and GPG keys*
4. Click **New SSH key**
5. In the "Title" field, add a label for your key.  For example "Personal Computer"
6. Paste your key into the "Key" field.
7. Click **Add SSH key**.

[Go to GitHub documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

## Using SSH Keys
In GitHub, when cloning repositories, or setting up the remote repository, use the SSH link instead of the HTTP:

![screenshot]({{site.url}}/{{site.baseurl}}/assets/images/github-ssh.png)