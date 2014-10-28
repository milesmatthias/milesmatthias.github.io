---
layout: post
title: Unix Aliases Are Pretty Handy
date: '2012-06-01T12:31:49-06:00'
tags: []
tumblr_url: http://milesmatthias.tumblr.com/post/24205506861/unix-aliases-are-pretty-handy
---
If you’re using Unix (you are if you’re using Mac OS X by the way) and you do a lot of work in the terminal, you should know about aliases. They’re really handy.

Basically, an alias is a shortcut for a command. You type in your shortcut and press return just like you would any other command, but the shell knows (by you defining the alias at some earlier time) that when you give it the short cut, you really want to execute some other command.

One of the first aliases that I always have set up is to list files in a directory the way I usually want to see them. As you probably know, when you do ls, you just see a boring file list like this:


  [milesmatthias]$ ls
  
  Desktop                Dropbox             Movies              Projects            lib
  Documents          IA_Projects         Music               Public
  Downloads          Library             Pictures
  TitaniumDefaultWorkspace


It doesn’t give you a whole lot of information about the files it lists (like file size, type, etc) and it doesn’t show you any hidden files that might be in that directory. So I usually set up an alias.

In your home directory, you want to edit (or create if it’s not already there) a hidden file named .bashrc. We define our aliases in that file like this:


  alias ll=’ls -ahl’


That syntax defines an alias with the shortcut command ll that correlates to the command ls -ahl, which allows me to see every file in a directory (hidden or not) and lists several attributes for each file in a human readable format.

Now if you try to use your alias right after saving your .bashrc file, it won’t work. The shell hasn’t gotten a chance to process that new alias definition and remember it. So you either need to log out of the shell and open a new shell, or you can stay in your existing shell and just tell the shell about it with this command:


  . ./.bashrc


Then try out your new alias and watch your command life be simplified!

Want to take it a step further? You can put anything in the extended command part of the alias definition that you would write on the command line. So use command chaining! I frequently use && to write long aliases that otherwise I’d have to do manually. For instance, every day I write some code, build the production version, and then deploy it to a sever. So my alias command for all of that looks like:


  alias buildproject=''cd web/webroot && ./build_prod.sh && cd ../.. && git add . && git commit -m "Built production version." && git pull && git push && ssh admin@dev''


The && operator is awesome because the shell will only move onto the next command if the previous command was successful. So if for some reason one of the commands in the chain fails, none of the following commands will execute and nothing else would go wrong. You’d just fix whatever failed and then execute the rest of the commands yourself.

Aliases make my life easier every day so hopefully they’ll help you too!

