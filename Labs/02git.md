---
title: "Lab 2: Git & GitHub"
layout: single
author_profile: false
classes: wide
excerpt: Practice git and GitHub skills
---
Objective:  Familiarize yourself with essential Git and GitHub commands and workflows. Get hands-on practice with creating repositories, making commits, working with branches, handling merge conflicts, and opening pull requests.

Instructions:  Go through each of the steps below and submit the final version of the GitHub repo to Gradescope. 

## Initial a new repository
1. Create an empty folder called `git_practice` in a sensible location on your computer. 
2. Navigate into the new folder
3. Initialize the folder as a git repository.  
    * *Remember that every project should be its own git repository.*
    * *Do NOT initialize root directories or parent folders relating to different projects*
4. Verify that the .git folder is now in the directory (in the terminal run `ls -la` and you should see the `.git` folder).

## Make your first commit
1. Check the git status 
2. Create a new file called `file_1.txt` 
    * Run `touch file_1.txt` in the terminal (mac) or git bash terminal (windows) to create an empty file called `file_1.txt`
3. Create another new file called `file_2.txt` 
4. Check the git status 
5. Add both files to the staging area
6. Check the git status
7. Commit the new files using the commit message "create new files"
8. Check the git status 
9. Check the git log 

## More git practice
 1. Open `file_1.txt` in a text editor.   Add the following to the file:
    ```
    This is my first file.
    ```
2. Open the the `file_2.txt` in a text editor.  Add the following to the file: 
    ```
    This is my second file.
    ```
3. Save the changes to both file.  Check the git status
4. Add and commit only the changes from the `file_1.txt` file.  Check the git status.
5. Make another commit with only the changes from the `file_2.txt` file.
6. Check the git log

## Create a Readme file
1. Create a file called `Readme.md``
2. Inside the Readme file, create a title (such as the name of the repo) and write a description of the repository
3. Add and commit the readme file.
    
## Create a `.gitignore`
1. Create a `.gitignore` file with the following text "api-keys.txt" 
2. Add and commit the `.gitignore` file
3. Create a file called "api-keys.txt" 
4. Check the status of the git repo
5. Add some text to the "api-keys.txt" file.  Save the changes and check the status. 

*IMPORTANT:  For best results, add all files that you want to ignore to the .gitignore file **before** any of the ignored files get committed. (Git will still track and push files that were committed before they were added to the .gitignore.)*  

## Create a branch
1. Make a new branch called "features"
2. Switch to the "features" branch
3. Look at the log and notice where HEAD is
4. Create a new file called `new_features.txt`
5. Add and commit the new file with the commit message "add empty file"
6. Open `new_features.txt` in a text editor.   Add the following to the file:
    ```
    This file will have some new features.
    ```
7. Commit the changes to the current ("features") branch

## Merge
1. Switch back to the main branch.  Notice the "new_features.txt" file is no longer in the directory. 
2. Open `file_1.txt` and add a line of text to the file (anything you want)  
3. Commit the changes.
4. Merge the main branch with the "features" branch.  
    * Your default editor should open to ask you for a commit message
    * Type a message and close the commit message file
5. Look at the git log.  You should see the git commit with the merge.

## Handle a Merge Conflict
 1. While on the main branch, open the `new_feature.txt` file and **replace** the old text with `No new features will be created.`  Save the changes. 
 2. Add and commit the changes.
 3. Switch back to the "features" branch.
 4. Open the "new_features.txt" file and **replace** the old text with `This file has some new text`. Save the file.
 5. Add and commit the changes on the features branch.
 6. Switch back to the main branch. 
 7. Merge the main branch with the "features" branch.
 8. You should get a merge conflict error and your default editor will open to have you resolve the conflict.
    * If your default editor doesn't open automatically:
        - Open `new_features.txt` manually in the text editor and edit the file by either accepting new changes, keeping old version, or a combination of both.
        - Save and commit the changes. 
        - *Tip*: VS Code might have a merge conflict resolver built in when you open the file. 
 9. Resolve the conflict and commit the merge.
    * *You already did this if you saved and committed changes in the previous step*.
10. Delete the `features` branch.
 
## Push to GitHub
1. Login to GitHub and create a blank repository  called "git-practice-*user_name*" (replace *user_name* with your GitHub username).  
    * Do not initialize it with a readme file, a .gitignore file, or license
2. Copy the SSH url (if you set up ssh keys).
3. In your local repository, set the remote branch by typing `git remote add origin <ssh url>` (replace `<ssh url>` with the copied repo url)
4. Push the local repo up to GitHub by typing `git push -u origin main`
5. Check that your GitHub repo was updated with your local work


## Collaborating and Making Pull Requests

**Find at least ONE other classmates to work with for this part**

### Make a Pull Request
1. Fork the repository of another student
2. Clone the forked repository to your local machine (outside your own repository that you've been working in).
3. Create a new branch called `feature-<your-name>`.  Replace `<your-name>` with your GitHub username
4. Make changes to the repository.  For example, you could create a new file or edit the text of an existing file
5. Commit all your changes
6. Push the changes to your fork by typing `git push origin feature-<your-name>`
7. Go to your forked repository on GitHub and create a pull request 
    * the base repository is your classmate's repository
    * the head repository is the feature branch in your forked repository
8. Fill in a descriptive title and a comment explaining your changes
9. If necessary, update the pull request to respond to suggestions
10. If you want more practice, repeat these steps with another student

(*Once your pull request has been accepted and merged, you can delete the local and remote forks if you want to*)

### Review and Merge a Pull Request
1. Have another student create a pull request in your repository by following the steps above. 
2. Review the pull request and leave constructive comments, such as suggestions to improve or questions about the pull request.  If you suggest any changes to the pull request then tell your partner to update the pull request
3. Once the pull request is finalized, merge the pull request into your repository
4. If you want more practice, repeat these steps with another student

## Pull from GitHub
1. Once all pull requests have been merged on GitHub, sync the remote changes to your local repository by running `git pull` (locally).
2. Verify that the changes are in your local repository. 

## Create Submission Files
1. Navigate to the repository that you've been working with (on your local machine)
2. Export the one-line git log to file called `gitlog.txt` by running the following in a terminal or git bash terminal. 
```
git log --oneline > gitlog.txt
```

3. Export your command line history with all the git commands you used to a file called `history.txt`:
    * Windows git bash terminal (or Mac bash shell)
    ```
    history | grep git > history.txt
    ```
    * Mac zsh shell (most new-ish Mac use zsh by default so unless you have specifically configured the terminal to use bash, most likely your Mac is using zsh)
    ```
    history 0 | grep git > history.txt
    ```
4. Add and commit these two files, then push the changes to GitHub

**IMPORTANT:  Be sure that your files are named `gitlog.txt` and `history.txt` *exactly***
## Gradescope Submission
1. On Gradescope, when you click on the "Lab 2: Git and GitHub" assignment, you will be asked to connect your GitHub account. 
2. Connect your GitHub account and then choose the repository that you've been working with for your submission.
3. The Gradescope autograder will do the following:
    * Check to make sure all files are present
    * Check that `gitlog.txt` has at least five commits
    * Check to makes sure that all the git commands the assignments ask for are present in `history.txt`


## Optional (for this week): Create a GitHub Pages site
1. Start setting up your blog site by following [these instructions]({{site.url}}/{{site.baseurl}}/resources/blogsetup)
2. Your blog doesn't need to be fully setup by the end of this week, but it is a good idea to get started on it. 

