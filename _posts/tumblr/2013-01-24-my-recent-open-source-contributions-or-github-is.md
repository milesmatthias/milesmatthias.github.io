---
layout: post
title: My recent open source contributions (or github is awesome)
date: '2013-01-24T22:14:00-07:00'
tags:
- github
- javascript
- meteor
- git
- jshint
- nebraskaJS
tumblr_url: http://milesmatthias.tumblr.com/post/41421186305/my-recent-open-source-contributions-or-github-is
---
I love open source projects and I love github. The github platform for easily and efficiently working in a distributed group in an asynchronous manner is second to none. Lately I’ve found myself submitting more pull requests than I’ve ever done and I’ve found the experience really awesome.

The thing I’ve liked most about using pull requests is that I’m free to mess up. When contributing to an open source project that other people look at, I’m afraid of looking stupid to everyone else, especially if my code is immediately merged into the codebase. I don’t want to be the guy that breaks the application for everyone else. Pull requests give me a safety net for people to review my contribution, give me feedback, and give me a chance to make corrections or improvements. I’m eager to get feedback because it most likely means I’ll learn something that I didn’t know and I’ll be a better developer because of it. And worst case scenario - my code breaks everything - it was just as much the fault of the pull request reviewer as it was mine (which is no excuse to make the same mistake twice though), which allows me to not stress that everything needs to be absolutely perfect before submitting. That’s the great thing about open source code - someone can do the first 80% of the work and then someone else can swoop in and help with the last 20%.

So, with that little intro to my experience with github pull requests out of the way, here are the pull requests I’ve done recently:

Adding documentation explaining Collections in the Meteor docs This is the second time I’ve submitted a pull request to Meteor, the open source Javascript web platform, and both of them have been documentation related. I’m finding that one of the best ways to learn a new tool is to help write documentation for it. The project benefits from the view of a newbie and I get to have other people review my understanding of the tool. This one has yet to be merged, but I’m confident that it will, even if I need to make a few corrections/adjustments.
Allowing Project Specific Configurations for the JSHint Sublime Text 2 Package I use JSHint within Sublime Text 2 every single day. One day I was using it and I noticed that it was giving me errors and warnings that shouldn’t be there, since I had created a config file for that project to ignore certain errors and warnings. I got really suspicious and checked out the source code on github. I quickly found out that I wasn’t the only one with this issue, as users of the package were complaining through the offending previous pull request and a new issue. The code that ruined the package for everyone was a very simple change, so seeing it as an opportunity to get more experience with the github pull request workflow, I submitted a patch. A few days later the maintainer and original author of the package merged my pull request, thanked me, and apologized to everyone for pulling in the offending code. Also, packages in Sublime Text 2 are updated from their source repo every time ST2 is relaunched, so after my fix was merged with the main codebase, my code changes were sent to anyone in the entire world who uses that package and restarted Sublime Text 2. Pretty neat!
Compressed CSS for the NebraskaJS website This is the code for the website of the meetup for Javascript professionals in my adopted home town of Omaha. Browsing the social media profiles of a few friends, I stumbled upon their website (which I never knew existed), and noticed the code was on github. I also saw the maintainer had a “To Do” list in his README file, so I thought I’d help them out by knocking one off of the list since I live in Colorado now and can’t contribute much to their group meetings. This change has yet to be merged, but I learned a new git trick. When I was helping to compress the CSS files, I kept forgetting to do little things, like updating the CSS includes in the HTML and crossing the task off of the author’s “To Do” list, so I had to learn how to amend commits (make new changes, git add ., git commit --amend), merge commits with previous commits (git rebase -i, pick and squash), and force the remote branch to forget about that old commit I just did and accept the new version of that commit that I had locally (git push --force). So that was cool too.
So to sum this up: github, open source, and git are all incredibly awesome.