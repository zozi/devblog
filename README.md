This is the source code to generate the [zozi dev blog](http://devblog.zozi.com).

It uses the awesome git-powered blog system [Jekyll](http://jekyllrb.com/). 

Following are instructions for creating new blog posts on your local machine (for the zozi dev team).

Getting Started
---------------

    cd ~/workspace   # or wherever you like
    git clone git@github.com:zozi/devblog.git
    cd devblog
    bundle install

Running a Local Server
----------------------

    jekyll --pygments --server 4000 --auto
    # or, if you have the latest dev_env, you can just type "jeks" for the same command

This will start a server running the blog on [localhost:4000](http://localhost:4000).

Creating a New Post
-------------------

Take a look at the existing post(s) in the _posts/ directory, and feel free to copy one as a template for a new post.

When you're done, git commit and git push -- you should now see your post [live](http://devblog.zozi.com).

Blogging like a hacker : )
