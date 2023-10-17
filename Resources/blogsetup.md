---
title: Blog setup using GitHub pages
layout: single
author_profile: false
classes: wide
excerpt: How to setup GitHub pages for hosting a simple blog
---

### A. Setting Up a GitHub Account:

1. Visit [GitHub](https://github.com/).
2. Sign up if you don't have an account, or log in if you already do.

### B. Create a New Repository:

1. Once logged in, click the `+` icon at the top right corner and choose "New repository." 
2. Name your repository:
* Option A: Name the repository "*yourusername*.github.io" if you'd like this to be the main webpage for your profile.  For this option leave `baseurl` blank in step **[G-1](#g-edit-the-_config-file)** below.
* Option B: Otherwise, name the repository anything as per your preference (e.g., `my-blog`).  For this option, use the name of the repository as the `baseurl` in step **[G-1](#g-edit-the-_config-file)** below. 
3. Make your repository public.
4. Do not initialize with a Readme or .gitignore
5. Click “Create repository.”

### C. Choose a Jekyll Theme:

[Jekyll](https://jekyllrb.com/) is a popular static site generator, written in Ruby, that transforms plain text content written in Markdown (and other formats) into static websites or blogs. Jekyll is natively supported by GitHub Pages. This means you can easily host a Jekyll site on GitHub Pages without any extra configuration.

> *Note: For this class, you are required to have blog hosted on GitHub pages in your own GitHub account, but you can use any tools that you like to create the blog.  For example,  [Hugo](https://gohugo.io/) and [11ty](https://www.11ty.dev/) are other popular static site generators*

There are several "officially" [supported themes](https://pages.github.com/themes/) on GitHub pages, and hundreds of other [paid and free themes](https://jekyllrb.com/docs/themes/) that have been designed to work seamlessly on GitHub pages.  Two themes that I've personally used are [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) and [What A Theme](https://github.com/thedevslot/WhatATheme). 

 **This tutorial will use the [stat386-blog theme](https://github.com/esnt/stat386-blog-theme), a simple theme that I made for the Stat 386 class.** 

> *Students in Stat 386 are not required to use this theme. Similar steps can be followed for most Jekyll themes hosted on GitHub, although every theme will have its own unique layouts and variable.*

1. Visit the [stat386-blog theme's GitHub repository](https://github.com/esnt/stat386-blog-theme).
2. Click the green “Code” button and then select “Download ZIP.”
3. Extract the ZIP on your computer.

### D. Upload the Jekyll Theme to Your Repository:

1. Navigate to your repository on GitHub.
2. Find the area of the page that says "Quick setup"
3. Inside the "Quick setup" box, click on the link "upload an existing file."
4. Drag all the files from the extracted theme folder (from step C-3) into the GitHub interface to upload them.
5. Commit the changes by clicking the "Commit changes" button at the bottom of the page.

### E. Configure Repository for GitHub Pages:

1. Go to your repository on GitHub.
2. Click on the "Settings" tab.
3. Click on the "Pages" link on the left-hand side under "Code and automation".
4. Under the "Source" dropdown, make sure that  "Deploy from branch" is selected
5. Under the "Branch" dropdown, select the `main` branch.  Leave the folder dropdown as "\root". Press the "Save" button.
6. In a few minutes, your site will be accessible at `https://yourusername.github.io` or `https://yourusername.github.io/repo-name` (it always takes a few minutes for any changes to be reflected on GitHub pages). 

### F. Create a local version (optional)

While it is not required, I find that it is easier to do edits to my sites locally rather than directly on GitHub **as long as changes are always synced**.  Having a local copy is also necessary if you plan to try local rendering as described in **[Section I](#i-local-page-rendering-optional)** below. 

1. On GitHub, click on the green "Code" button a copy the appropriate clone url
2. Navigate to the location on your computer where you want to store your blog file.
3. Clone the blog repository by typing `git clone url` (where `url` should be replaced with what you copied in step 1.)
4. Remember to sync changes **anytime** you make a new commit
    * If changes are made directly on GitHub, pull those changes down locally 
    * If changes are made locally, push those changes up to GitHub
    * **You can get errors if you aren't careful to keep the local and remote copies synced.**


### G. Edit the `_config` file:

1. Edit all the fields in the `_config.yml` to have your own information:
* `title:` "Choose a sensible title for your blog"
* `email:` your_email@example.com
* `description:` "Write a brief description about your blog"
  > *Note: Quotes are not required but it is safer to wrap the title and description in quotes, especially if you use special characters, such as `:`*
* `url:` https://*yourusername*.github.io where *yourusername* is your GitHub user name 
* `baseurl:` repo_name that you chose in step **[B-2](#b-create-a-new-repository)** option B or leave blank if you used option A in step **[B-2](#b-create-a-new-repository)** 
* `image:` The internal or external link to your main blog image
* `author:` Your name
* `copyright:` Your initials or leave blank
* `footer_description:` Delete and optionally add your own.  This will appear in the footer on the right side of the page
* Social media users names as you like
2. Further customize your blog by adding information about yourself to the "About.md" file
3. Save and commit all changes.  Sync local and remote repositories if necessary. 
 
### H. Create a blog post

1. On GitHub, click on the “Add file” button and choose "Create new file".
2. Inside the bar that says "Name your file.." type `_posts/`. 
  * *GitHub will recognize that you are referencing a folder when you type the `/` and a new box will appear for the file name.  If you don't already have a `_posts` folder in the repo, it will be created for you.* 
3.  Inside the new box, type `2023-09-01-first-post.md` (You can always change this later).
4.  Add a header at the top:
```
---
layout: post
title:  "Post Name"
author: Your name
description: Short yet informative description
image: "/path/to/image" or "url_to_image"
--- 
```
> *Note: Other themes might have other header options or other layouts*

5. Below the header, add the text 
```
Hello World!
```
6.  Commit the changes.

> *For more details about creating blog posts see the [example post](https://esnt.github.io/stat386-blog-theme/2022/08/01/sample-post.html) included with the stat386-blog theme.*
  

### I. Local Page Rendering (optional)
Changes that you make to your GitHub pages site are not immediate.  It takes a few minutes for changes to be reflected, which makes it hard for realtime development.  You can install Jekyll on your computer which will allow you to render your site locally while making edits. 

* Follow [these instructions](https://jekyllrb.com/docs/installation/) to install Jekyll.  
* Once Jekyll is installed, navigate to your local GitHub pages repo.
* In the command line type the commands (*This only needs to be done once*):
```
> gem install bundler jekyll
> bundle add webrick
```
* Serve your website locally by typing the command
```
> bundle exec jekyll serve -l -o
```
* With the `-o`, the browser should open automatically.  If not, your website can be viewed locally at `http://localhost:4000` or `http://localhost:4000/repo-name`
* Changes will be reflected automatically upon saving, except for changes to the "_config" file.  The server will need to be stopped (by pressing CTRL-C) and served again to reflect "_config" file changes. 

> *Note: Ruby and Jekyll can be a little finicky to install.  I can try to help troubleshoot, but I am not an expert, especially on Windows.*

### J. Add Comments using [Utterances](https://github.com/utterance) (optional)

1. Install the utterances app on in your blog repository  
        a. Go to [https://github.com/apps/utterances](https://github.com/apps/utterances)   
        b. Click "Configure"  
        c. Choose the repository where you want to install utterances (your blog repo). 
            * Select your user name. 
            * Select "Only select repositories". 
            * Choose your blog repository. 
            * Click install. 

2. In your repository, go to settings and make sure that "Issues" are turned on.  You'll find "Issues" on the main settings page under "Features".  Check the box next to "Issues."

3.  Navigate to the "\_layouts" folder and open "post.html" file. 

    Find the following code in the file:
    ```
    <script src="https://utteranc.es/client.js"
        repo="your-user-name/blog-repo"
        issue-term="pathname"
        label="💬"
        theme="boxy-light"
        crossorigin="anonymous"
        async>
    </script>
     ```
4. Change "your-user-name" in the second line in the code block to your actual GitHub user name.  
5. Save and commit all changes.  After a few minutes check the bottom of the page of one of your blog posts to see if it worked (if it did, you should have the options for comments)

---

Your blog is now set up on GitHub Pages. Remember to commit any changes to reflect them on your live site. 


