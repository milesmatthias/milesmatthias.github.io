---
layout: post
title: Automatically Back Up Projects with Dropbox
date: '2012-07-11'
tags: []
tumblr_url: http://milesmatthias.tumblr.com/post/26962760896/automatically-back-up-projects-with-dropbox
---
I nearly just paid an unnecessary $7/mo to Github just to make a backup of my project’s code. I averted this terrible crisis with a symbolic link and Dropbox.

I keep all of my projects in a local folder because my Dropbox account isn’t big enough to hold all of the projects I’ve ever done. I want to backup the one that I’m currently working on though, so I moved that project’s directory to my Dropbox folder to have it backed up in the cloud for free.

But to not break my work flow at all, I made a symbolic link where my project directory used to be. To create the symbolic link, I used the following command:

ln -s ~/Dropbox/Projects/project_name project_name


Now, I, and all of my development apps, can still go to my local folder project_name and work as usual like nothing happened. However, I can rest easy knowing that my free Dropbox account has my back.
