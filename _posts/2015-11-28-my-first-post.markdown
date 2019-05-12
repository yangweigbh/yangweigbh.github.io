---
layout: default
title:  "How to build blog using jekyll and GithubPages"
date:   2015-11-28 20:18:09 +0800
categories: IT
---

#How to build blog using jekyll and GithubPages

This is my first blog built upon jekyll and host on github pages, and i want to share how to create personal blog using jekyll and Github Pages

- First, create a new repo in github, with name `yourusername.github.io`
- git clone the new creatd repo into your local directory `git clone https://github.com/username/username.github.io`
- install jekyll, refer to [here](http://jekyllrb.com/docs/installation/) to see how to install jekyll
- change directory into your local repo directory and execute command `jekyll new .` and this command will create a bunch of jekyll project files into your dirctory 

   ![](/assets/1128_jekyll_project_structure.png)

- with the bunch of files, the simplest blog template has been created, execute command `jekyll server`, this command will set up a server and visit `http://127.0.0.1:4000/`, you will see the template, but the info on the blog are template generated, let's replace it with custom one.
- open the _config.yml under the root, and modify the `title`, `email`...etc to your own info, and refresh the website, you will the change immediately 
- the main page is actually index.html under the root, it will render the files in `_post`, put your posts in `_post`, and it will be automatically added in main page
- write your first post, make your commit and upload your change back to github repo `git push origin master`
- go to "yourusername.github.io" to see your first post!

For more info about jekyll, refer [here](http://jekyllrb.com/docs/home/)
